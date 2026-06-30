---
layout: default
title: Lights Out
---

## Lights Out

Click a cell to toggle it and its four orthogonal neighbors. Get every light **off** to win.

<div class="lo-game">
  <div class="lo-bar">
    <span class="lo-moves">Moves: <strong id="lo-move-count">0</strong></span>
    <button id="lo-new" type="button">New puzzle</button>
    <button id="lo-reset" type="button">Reset</button>
  </div>
  <div id="lo-board" class="lo-board" role="grid" aria-label="Lights Out board"></div>
  <p id="lo-status" class="lo-status" aria-live="polite">&nbsp;</p>
</div>

<style>
  .lo-game {
    max-width: 360px;
    margin: 1.5rem 0;
    -webkit-user-select: none;
    user-select: none;
  }
  .lo-bar {
    display: flex;
    align-items: center;
    gap: .75rem;
    margin-bottom: .75rem;
    flex-wrap: wrap;
  }
  .lo-moves { margin-right: auto; }
  .lo-bar button {
    font: inherit;
    cursor: pointer;
    padding: .35rem .8rem;
    border: 1px solid #16213e;
    border-radius: 6px;
    background: #fff;
    color: #16213e;
    transition: background .12s, color .12s;
  }
  .lo-bar button:hover { background: #16213e; color: #fff; }
  .lo-board {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 8px;
    aspect-ratio: 1 / 1;
  }
  .lo-cell {
    border: none;
    border-radius: 8px;
    background: #dfe3ee;
    cursor: pointer;
    box-shadow: inset 0 -3px 0 rgba(0,0,0,.08);
    transition: background .12s, box-shadow .12s, transform .05s;
  }
  .lo-cell:hover { transform: scale(0.97); }
  .lo-cell.on {
    background: #16213e;
    box-shadow: inset 0 -3px 0 rgba(0,0,0,.25), 0 0 12px rgba(22,33,62,.45);
  }
  .lo-cell:focus-visible { outline: 2px solid #e94560; outline-offset: 2px; }
  .lo-status { min-height: 1.4em; font-weight: bold; color: #16213e; }
</style>

<script>
(function () {
  var SIZE = 4;
  var board = document.getElementById("lo-board");
  var moveCountEl = document.getElementById("lo-move-count");
  var statusEl = document.getElementById("lo-status");
  var cells = [];
  var state = [];          // current lit/off state
  var startState = [];     // snapshot for Reset
  var moves = 0;
  var won = false;

  function idx(r, c) { return r * SIZE + c; }

  function render() {
    for (var i = 0; i < state.length; i++) {
      cells[i].classList.toggle("on", state[i]);
      cells[i].setAttribute("aria-pressed", state[i] ? "true" : "false");
    }
  }

  function isSolved() {
    return state.every(function (v) { return !v; });
  }

  function press(r, c, countMove) {
    var deltas = [[0, 0], [-1, 0], [1, 0], [0, -1], [0, 1]];
    for (var k = 0; k < deltas.length; k++) {
      var nr = r + deltas[k][0], nc = c + deltas[k][1];
      if (nr >= 0 && nr < SIZE && nc >= 0 && nc < SIZE) {
        state[idx(nr, nc)] = !state[idx(nr, nc)];
      }
    }
    if (countMove) {
      moves++;
      moveCountEl.textContent = moves;
    }
  }

  function onClick(r, c) {
    if (won) return;
    press(r, c, true);
    render();
    if (isSolved()) {
      won = true;
      statusEl.textContent = "Lights out! Solved in " + moves + (moves === 1 ? " move." : " moves.");
    }
  }

  function newPuzzle() {
    // Build a guaranteed-solvable board by applying random presses to a solved board.
    state = new Array(SIZE * SIZE).fill(false);
    var scrambles = 5 + Math.floor(Math.random() * (SIZE * SIZE - 5));
    do {
      state = new Array(SIZE * SIZE).fill(false);
      for (var n = 0; n < scrambles; n++) {
        press(Math.floor(Math.random() * SIZE), Math.floor(Math.random() * SIZE), false);
      }
    } while (isSolved()); // never start already solved
    startState = state.slice();
    moves = 0;
    moveCountEl.textContent = "0";
    won = false;
    statusEl.innerHTML = "&nbsp;";
    render();
  }

  function reset() {
    state = startState.slice();
    moves = 0;
    moveCountEl.textContent = "0";
    won = false;
    statusEl.innerHTML = "&nbsp;";
    render();
  }

  // Build grid
  for (var r = 0; r < SIZE; r++) {
    for (var c = 0; c < SIZE; c++) {
      (function (r, c) {
        var btn = document.createElement("button");
        btn.type = "button";
        btn.className = "lo-cell";
        btn.setAttribute("role", "gridcell");
        btn.setAttribute("aria-label", "Row " + (r + 1) + ", column " + (c + 1));
        btn.addEventListener("click", function () { onClick(r, c); });
        board.appendChild(btn);
        cells.push(btn);
      })(r, c);
    }
  }

  document.getElementById("lo-new").addEventListener("click", newPuzzle);
  document.getElementById("lo-reset").addEventListener("click", reset);

  newPuzzle();
})();
</script>
