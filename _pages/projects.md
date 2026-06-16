---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 3
---

<style>
.proj-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; margin-top: 1rem; }
@media (max-width: 576px) { .proj-grid { grid-template-columns: 1fr; } }
.proj-card { position: relative; cursor: pointer; border-radius: 10px; overflow: hidden; background: #000;
  box-shadow: 0 2px 10px rgba(0,0,0,.18); transition: transform .2s ease, box-shadow .2s ease; }
.proj-card:hover { transform: translateY(-3px); box-shadow: 0 8px 22px rgba(0,0,0,.30); }
.proj-card video { width: 100%; display: block; }
.proj-card .proj-caption { position: absolute; left: 0; right: 0; bottom: 0; padding: .55rem .75rem;
  color: #fff; font-size: .9rem; background: linear-gradient(transparent, rgba(0,0,0,.78)); }
.proj-card .play-badge { position: absolute; top: 50%; left: 50%; transform: translate(-50%,-50%);
  width: 56px; height: 56px; border-radius: 50%; background: rgba(0,0,0,.55); pointer-events: none;
  display: flex; align-items: center; justify-content: center; transition: background .2s ease; }
.proj-card:hover .play-badge { background: var(--global-theme-color); }
.proj-card .play-badge::after { content: ""; margin-left: 4px;
  border-left: 18px solid #fff; border-top: 11px solid transparent; border-bottom: 11px solid transparent; }

.proj-lightbox { position: fixed; inset: 0; z-index: 1000; background: rgba(0,0,0,.85);
  display: none; align-items: center; justify-content: center; opacity: 0; transition: opacity .25s ease; }
.proj-lightbox.open { display: flex; opacity: 1; }
.proj-lightbox video { width: min(90vw, 1100px); max-height: 85vh; border-radius: 8px; background: #000;
  transform: scale(.85); transition: transform .25s ease; box-shadow: 0 12px 44px rgba(0,0,0,.55); }
.proj-lightbox.open video { transform: scale(1); }
.proj-lightbox .close-btn { position: absolute; top: 16px; right: 26px; color: #fff;
  font-size: 2.2rem; line-height: 1; cursor: pointer; }
</style>

<div class="proj-grid">
  <div class="proj-card" data-video="{{ '/assets/videos/iros.mp4' | relative_url }}">
    <video src="{{ '/assets/videos/iros.mp4' | relative_url }}#t=0.1" muted preload="metadata" playsinline></video>
    <div class="play-badge"></div>
    <div class="proj-caption">IROS 2026 — SMAT: Co-Adaptive Exoskeleton Control</div>
  </div>
  <div class="proj-card" data-video="{{ '/assets/videos/biorob.mp4' | relative_url }}">
    <video src="{{ '/assets/videos/biorob.mp4' | relative_url }}#t=0.1" muted preload="metadata" playsinline></video>
    <div class="play-badge"></div>
    <div class="proj-caption">BioRob 2026 — Ankle Assistance for Gait Symmetry</div>
  </div>
</div>

<div class="proj-lightbox" id="projLightbox">
  <span class="close-btn" id="projClose">&times;</span>
  <video id="projPlayer" controls playsinline></video>
</div>

<script>
  (function () {
    var lb = document.getElementById('projLightbox');
    var player = document.getElementById('projPlayer');
    var closeBtn = document.getElementById('projClose');
    function openVideo(src) {
      player.src = src;
      lb.classList.add('open');
      player.play().catch(function () {});
    }
    function closeVideo() {
      lb.classList.remove('open');
      player.pause();
      player.removeAttribute('src');
      player.load();
    }
    document.querySelectorAll('.proj-card').forEach(function (card) {
      card.addEventListener('click', function () { openVideo(card.getAttribute('data-video')); });
    });
    closeBtn.addEventListener('click', closeVideo);
    lb.addEventListener('click', function (e) { if (e.target === lb) closeVideo(); });
    document.addEventListener('keydown', function (e) { if (e.key === 'Escape') closeVideo(); });
  })();
</script>
