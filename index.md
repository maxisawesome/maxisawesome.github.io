---
layout: default
Title: Home
---
<div class="lo-wrap">
  <div id="lo-board" class="lo-board" role="grid" aria-label="Lights Out puzzle"></div>
  <div class="lo-min">
    <div>puzzle minimum: <strong id="lo-start-min">0</strong></div>
    <div>minimum from here: <strong id="lo-min-count">0</strong></div>
    <div>your clicks: <strong id="lo-clicks">0</strong></div>
  </div>
</div>

<style>
  .lo-wrap {
    float: right;
    margin: .4rem 0 1rem 1.4rem;
    display: flex;
    align-items: center;
    gap: .9rem;
  }
  .lo-board {
    flex: 0 0 auto;
    width: 150px;
    height: 150px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 7px;
    -webkit-user-select: none;
    user-select: none;
  }
  .lo-cell {
    border: none;
    border-radius: 8px;
    background: #dfe3ee;
    cursor: pointer;
    box-shadow: inset 0 -3px 0 rgba(0,0,0,.08);
    transition: background .12s, box-shadow .12s, transform .05s;
  }
  .lo-cell:hover { transform: scale(0.95); }
  .lo-cell.on {
    background: #16213e;
    box-shadow: inset 0 -3px 0 rgba(0,0,0,.25), 0 0 12px rgba(22,33,62,.45);
  }
  .lo-cell:focus-visible { outline: 2px solid #e94560; outline-offset: 2px; }
  .lo-board.lo-won .lo-cell { box-shadow: 0 0 14px rgba(233,69,96,.6); }
  .lo-min {
    font-size: .8rem;
    line-height: 1.6;
    text-align: left;
    color: #16213e;
    white-space: nowrap;
  }
  @media (max-width: 30em) {
    .lo-wrap { float: none; margin: 1rem auto; }
  }
</style>

<script>
(function () {
  var SIZE = 4;
  var N = SIZE * SIZE;
  var board = document.getElementById("lo-board");
  var minEl = document.getElementById("lo-min-count");
  var startMinEl = document.getElementById("lo-start-min");
  var clicksEl = document.getElementById("lo-clicks");
  var cells = [];
  var state = [];
  var clicks = 0;
  var locked = false;

  function idx(r, c) { return r * SIZE + c; }

  // Precompute the toggle matrix: toggleMat[i] is a bitmask of cells flipped by clicking i.
  var toggleMat = [];
  for (var i = 0; i < N; i++) {
    var mask = 0;
    var mr = Math.floor(i / SIZE), mc = i % SIZE;
    [[0, 0], [0, 1], [0, -1], [1, 0], [-1, 0]].forEach(function (d) {
      var nr = mr + d[0], nc = mc + d[1];
      if (nr >= 0 && nr < SIZE && nc >= 0 && nc < SIZE) mask |= 1 << (nr * SIZE + nc);
    });
    toggleMat.push(mask);
  }

  // Minimum clicks to solve the given board, via Gaussian elimination over GF(2).
  // For 4x4 the matrix is invertible, so the unique solution's bit-count IS the minimum.
  function minMoves() {
    var b = 0;
    for (var k = 0; k < N; k++) if (state[k]) b |= 1 << k;
    var M = toggleMat.map(function (row, r) { return row | (((b >> r) & 1) << N); });
    for (var col = 0; col < N; col++) {
      var piv = -1;
      for (var r = col; r < N; r++) { if ((M[r] >> col) & 1) { piv = r; break; } }
      if (piv === -1) continue;
      var tmp = M[col]; M[col] = M[piv]; M[piv] = tmp;
      for (var r2 = 0; r2 < N; r2++) {
        if (r2 !== col && ((M[r2] >> col) & 1)) M[r2] ^= M[col];
      }
    }
    var count = 0;
    for (var s = 0; s < N; s++) count += (M[s] >> N) & 1;
    return count;
  }

  function render() {
    for (var i = 0; i < state.length; i++) {
      cells[i].classList.toggle("on", state[i]);
      cells[i].setAttribute("aria-pressed", state[i] ? "true" : "false");
    }
    minEl.textContent = minMoves();
    clicksEl.textContent = clicks;
  }

  function isSolved() {
    return state.every(function (v) { return !v; });
  }

  function press(r, c) {
    var deltas = [[0, 0], [-1, 0], [1, 0], [0, -1], [0, 1]];
    for (var k = 0; k < deltas.length; k++) {
      var nr = r + deltas[k][0], nc = c + deltas[k][1];
      if (nr >= 0 && nr < SIZE && nc >= 0 && nc < SIZE) {
        state[idx(nr, nc)] = !state[idx(nr, nc)];
      }
    }
  }

  function newPuzzle() {
    var scrambles = 5 + Math.floor(Math.random() * (SIZE * SIZE - 5));
    do {
      state = new Array(SIZE * SIZE).fill(false);
      for (var n = 0; n < scrambles; n++) {
        press(Math.floor(Math.random() * SIZE), Math.floor(Math.random() * SIZE));
      }
    } while (isSolved());
    clicks = 0;
    startMinEl.textContent = minMoves();
    render();
  }

  function onClick(r, c) {
    if (locked) return;
    press(r, c);
    clicks++;
    render();
    if (isSolved()) {
      locked = true;
      board.classList.add("lo-won");
      setTimeout(function () {
        board.classList.remove("lo-won");
        newPuzzle();
        locked = false;
      }, 650);
    }
  }

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

  newPuzzle();
})();
</script>

## Howdy
This is the personal website of Max Marion. I'm a Machine Learning Researcher currently at [Tacit Labs](tacitlabs.co). Before that I was at [MosaicML / Databricks](https://www.databricks.com/research/mosaic), a Research Scholar at [cohere labs](https://cohere.com/research), and earlier an MLE at [KUNGFU.AI](https://kungfu.ai). I was a main contibutor to [LifeSciBench](https://cdn.openai.com/pdf/b4299379-0a97-4ffa-8b9b-c3fbb299caa9/lifescibench_preprint.pdf) and have published work on [data pruning](https://openreview.net/pdf?id=XUIYn3jo5T) (the longer pre-print [here](https://arxiv.org/abs/2309.04564)) for LLM pretraining. My reearch has been in LLM evaluations, faithfulness, but has reached into computer vision, audio, and more.

My motion based hobbies include surfing, backpacking where I can forget about the anthropocene, lifting, and playing ultimate frisbee. My more stationary hobbies include puzzle games, rougelikes, and reading. In Austin I played frisbee on [Riverside](https://www.riversideultimate.org/) and loved hanging out in my backyard with [my cat, Callie](../cat). I grew up in Austin, went to school in [Los Angeles](https://www.oxy.edu/), moved back home, and as of October 2023 live in San Francisco. 

my poor attempts at professionalism are [here](https://www.linkedin.com/in/max-marion/)

my worst takes are [here](https://twitter.com/maxisawesome538)

research only is [here](https://twitter.com/maxdoesresearch)

my code is [here](https://github.com/maxisawesome)

my str8 up email (remove the hightech captcha): m m a r i o n 5 3 8 @ < r o b o t s  g o  a w a y > @ g m a i l 

I was recently briefly featured in [this Scientific American](https://www.scientificamerican.com/article/the-god-chatbots-changing-religious-inquiry/) article on LLMs and their possibilities for religious applications and [this Wall Street Journal](https://www.wsj.com/sports/olympics/noah-lyles-olympics-100m-ecab1749?st=i9sza7f1tc1b5us&reflink=desktopwebshare_permalink) article on Noah Lyles and the "rise of nerds."

Here's a list of the cooler projects I've worked on, during which my role always fell under "make the neural network work":

* Evals for SOTA LLMs 
* Hallucination detection and correction 
* Efficacy of LLMAsAJudge
* My paper exploring various methods of judging language data as low or high quality ([paper link](https://arxiv.org/abs/2309.04564))
* An algorithm to judge the price of collectibles like Pokemon cards, baseball cards, or rare coins
* A computer vision project identifying and pricing exterior damage on cars from cell phone photos
* A model for processing ambient rainforest noise to find gunshots, chainsaws, and vehicles indicating poaching and logging
* A system to scan insurance corpora to extract helpful sentences like "drug X is covered by plan Y under situation Z, but not situation A"
* A CTR (Click Through Rate) predictor for *crowd groaning noises* ads
* A FOD detector for runway radar scans (detects debris on your runway that'd destroy your fancy plane engines)
* A number of "information extractors" for large datastores of pdfs 
* The algorithm that judges SXSW speaker applications alongside human judges
* and more! that are either less interesting or I'm not allowed to tell you about


