---
layout: about
title: About
permalink: /
subtitle: Ph.D. Candidate · <strong>BioDynamics Lab</strong>

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p style="white-space: nowrap;">Biomedical Engineering</p>
    <p style="white-space: nowrap;">NJIT &amp; Rutgers, Newark, NJ</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 6 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<style>
/* Make the full name bold, not just the first name */
.post-title { font-weight: 700; }
/* Capitalize the section headings (News, Selected Publications) */
.post > article > h2 { text-transform: capitalize; }
/* Align the photo's top with the subtitle line; small gap on its left */
.profile.float-right { margin-left: 1.5rem; transform: translateX(8px); }
/* Make the photo a bit larger on desktop (default is 30%) */
@media (min-width: 576px) { .profile.float-right { width: 34%; } }
/* Fist-bump widget */
#fistbump-wrap { margin-top: 1.6rem; margin-bottom: 2.75rem; display: flex; align-items: center; gap: 0.85rem; flex-wrap: wrap; }
#fistbump-btn { background: var(--global-theme-color); color: #fff; border: none; border-radius: 24px;
  padding: 0.5rem 1.15rem; font-size: 1rem; cursor: pointer; transition: transform .12s ease, opacity .15s ease; }
#fistbump-btn:hover:not(:disabled) { transform: scale(1.05); }
#fistbump-btn:disabled { opacity: 0.55; cursor: default; }
/* Publication links (arXiv/PDF/...) trail the title inline instead of taking their own line */
.publications ol.bibliography li .title { display: inline; }
.publications ol.bibliography li .links { display: inline; margin-left: 0.35rem; }
.publications ol.bibliography li .links a.btn {
  padding: 0.05rem 0.5rem;
  font-size: 0.72rem;
  line-height: 1.5;
  vertical-align: 0.08em;
  margin-right: 0.15rem;
}
</style>

Hi, I'm **Yifei Yuan (袁一飞)**, a Ph.D. student in the **Joint Biomedical Engineering PhD Program** at NJIT & Rutgers. My research sits at the intersection of **reinforcement learning, robotics, biomechanics, and human movement in simulation**, with a focus on **rehabilitation exoskeletons**.

I am especially interested in *learning control policies in simulation* and transferring them to real-world wearable robots that can assist and restore human movement.

I'm always happy to connect with people who share these interests. Feel free to reach out at **[yy72@njit.edu](mailto:yy72@njit.edu)**, connect with me on <strong><a href="https://www.linkedin.com/in/yifei-yuan-b4a161252" target="_blank" rel="noopener">LinkedIn <i class="fa-brands fa-linkedin"></i></a></strong>, or check out my work on <strong><a href="https://scholar.google.com/citations?user=kJuCg-gAAAAJ&amp;hl=en" target="_blank" rel="noopener">Google Scholar <i class="ai ai-google-scholar"></i></a></strong>.

I'm currently **open to internship and research collaboration opportunities**. If you're working on something related, I'd love to hear from you.

<div id="fistbump-wrap">
  <button id="fistbump-btn" type="button">🤜🤛 Fist bump</button>
</div>

<script>
  (function () {
    var BASE = 'https://api.counterapi.dev/v1/fitzyuanhomepage/bumps';
    var btn = document.getElementById('fistbump-btn');
    if (!btn) return;
    function bumpedAlready() { try { return localStorage.getItem('fistbumped') === '1'; } catch (e) { return false; } }
    function markBumped() { try { localStorage.setItem('fistbumped', '1'); } catch (e) {} }
    function disable() { btn.disabled = true; btn.textContent = '🤜🤛 Bumped!'; }
    if (bumpedAlready()) disable();
    btn.addEventListener('click', function () {
      if (bumpedAlready()) return;
      markBumped();
      disable();
      fetch(BASE + '/up').catch(function () {});
    });
  })();
</script>
