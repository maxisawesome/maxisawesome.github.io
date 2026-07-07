---
layout: page
title: Cat
---

<style>
  .cat-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 0.5rem;
    margin-bottom: 1.5rem;
  }
  .cat-gallery a { display: block; }
  .cat-gallery img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 5px;
    margin: 0;
    cursor: zoom-in;
    display: block;
  }
  /* JS-free lightbox: an overlay shows only when its id is the :target */
  .cat-lightbox {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0, 0, 0, 0.85);
    z-index: 1000;
    padding: 2rem;
    cursor: zoom-out;
    align-items: center;
    justify-content: center;
  }
  .cat-lightbox:target { display: flex; }
  .cat-lightbox img {
    max-width: 95%;
    max-height: 95vh;
    width: auto;
    height: auto;
    margin: 0;
    border-radius: 5px;
  }
</style>

<!-- To add a photo: run it through sips into assets/cat/web/{thumb,full}/
     then add a matching tile below and a lightbox overlay at the bottom. -->

<div class="cat-gallery">
  <a href="#cat-1"><img loading="lazy" src="/assets/cat/web/thumb/PXL_20220405_224627224.MP.jpg" alt="Callie the cat"></a>
  <a href="#cat-2"><img loading="lazy" src="/assets/cat/web/thumb/PXL_20211208_010255698.jpg" alt="Callie the cat"></a>
  <a href="#cat-3"><img loading="lazy" src="/assets/cat/web/thumb/IMG_20200908_124257.jpg" alt="Callie the cat"></a>
  <a href="#cat-4"><img loading="lazy" src="/assets/cat/web/thumb/PXL_20220102_165449697.jpg" alt="Callie the cat"></a>
  <a href="#cat-5"><img loading="lazy" src="/assets/cat/web/thumb/PXL_20220313_160143252.MP.jpg" alt="Callie the cat"></a>
  <a href="#cat-6"><img loading="lazy" src="/assets/cat/web/thumb/PXL_20210126_203601179.jpg" alt="Callie the cat"></a>
</div>

<a href="#_" class="cat-lightbox" id="cat-1"><img loading="lazy" src="/assets/cat/web/full/PXL_20220405_224627224.MP.jpg" alt="Callie the cat"></a>
<a href="#_" class="cat-lightbox" id="cat-2"><img loading="lazy" src="/assets/cat/web/full/PXL_20211208_010255698.jpg" alt="Callie the cat"></a>
<a href="#_" class="cat-lightbox" id="cat-3"><img loading="lazy" src="/assets/cat/web/full/IMG_20200908_124257.jpg" alt="Callie the cat"></a>
<a href="#_" class="cat-lightbox" id="cat-4"><img loading="lazy" src="/assets/cat/web/full/PXL_20220102_165449697.jpg" alt="Callie the cat"></a>
<a href="#_" class="cat-lightbox" id="cat-5"><img loading="lazy" src="/assets/cat/web/full/PXL_20220313_160143252.MP.jpg" alt="Callie the cat"></a>
<a href="#_" class="cat-lightbox" id="cat-6"><img loading="lazy" src="/assets/cat/web/full/PXL_20210126_203601179.jpg" alt="Callie the cat"></a>

its catnip lol
i love her

Sweet Callie died in May 2023. I wrote an obituary post [here](https://www.instagram.com/p/Ct7KyaNPZ-6/?igshid=MmU2YjMzNjRlOQ==) featuring some of my favorite moments with her.
