---
layout: page
permalink: /talks/
title: talks
description: Invited talks, tutorials, and conference presentations by Francesco Ferrini on Graph Neural Networks, link prediction, missing features, and heterogeneous graphs.
keywords: Francesco Ferrini talks, NeurIPS 2025, Learning on Graphs, LoG conference, Alan Turing Institute, Heterogeneous Graph Learning tutorial, GNN talks
nav: true
nav_order: 2
---

<style>
  .talks-list {
    margin-top: 1rem;
  }
  .talk-card {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    padding: 1rem 0;
    border-bottom: 1px solid #eee;
  }
  .talk-card:last-child { border-bottom: none; }
  .talk-thumb {
    flex: 0 0 200px;
    max-width: 200px;
  }
  .talk-thumb img {
    width: 100%;
    height: auto;
    border-radius: 4px;
    border: 1px solid #ddd;
    display: block;
  }
  .talk-body {
    flex: 1;
    min-width: 0;
  }
  .talk-title {
    margin: 0 0 .35rem 0;
    font-size: 1.05rem;
    font-weight: 600;
    line-height: 1.3;
  }
  .talk-title a { color: inherit; }
  .talk-meta {
    font-size: .85rem;
    color: #777;
    margin: 0 0 .5rem 0;
  }
  .talk-meta .badge {
    display: inline-block;
    font-size: .7rem;
    padding: 1px 6px;
    border-radius: 3px;
    background: #e8e8e8;
    color: #444;
    margin-right: .35rem;
    text-transform: uppercase;
    letter-spacing: .03em;
  }
  .talk-meta .badge.oral { background: #ffe6cc; color: #b25400; }
  .talk-desc {
    font-size: .9rem;
    line-height: 1.5;
    color: #444;
    margin: 0 0 .5rem 0;
  }
  .talk-links {
    font-size: .85rem;
  }
  .talk-links a {
    margin-right: .8rem;
  }
  @media (max-width: 600px) {
    .talk-card { flex-direction: column; }
    .talk-thumb { flex: none; max-width: 100%; }
  }
</style>

<div class="talks-list">

  <!-- NeurIPS 2025 Workshop Oral -->
  <div class="talk-card">
    <div class="talk-thumb">
      <a href="https://neurips.cc/virtual/2025/loc/san-diego/127678" target="_blank" rel="noopener">
        <img src="/assets/img/neurips_logo.png" alt="NeurIPS 2025 Workshop Oral">
      </a>
    </div>
    <div class="talk-body">
      <h3 class="talk-title">
        <a href="https://neurips.cc/virtual/2025/loc/san-diego/127678" target="_blank" rel="noopener">
          Beyond Sparse Benchmarks: Evaluating GNNs with Realistic Missing Features
        </a>
      </h3>
      <p class="talk-meta">
        <span class="badge oral">Oral</span>
        NeurIPS 2025 Workshop on New Perspectives in Graph Machine Learning &middot; San Diego, USA
      </p>
      <p class="talk-desc">
        Re-evaluating progress on Graph Neural Networks under missing node features:
        why current sparse-feature benchmarks make every method look robust, and what changes when
        we move to dense, semantically meaningful features and realistic missingness mechanisms.
      </p>
      <p class="talk-links">
        <a href="https://neurips.cc/virtual/2025/loc/san-diego/127678" target="_blank" rel="noopener">NeurIPS page</a>
        <a href="https://openreview.net/forum?id=GfU8DhOzae" target="_blank" rel="noopener">Paper</a>
      </p>
    </div>
  </div>

  <!-- LoG 2023 Oral -->
  <div class="talk-card">
    <div class="talk-thumb">
      <a href="https://www.youtube.com/watch?v=9ddZ15dZ-lQ&t=1m21s" target="_blank" rel="noopener">
        <img src="https://i3.ytimg.com/vi/9ddZ15dZ-lQ/maxresdefault.jpg" alt="LoG 2023 Oral">
      </a>
    </div>
    <div class="talk-body">
      <h3 class="talk-title">
        <a href="https://www.youtube.com/watch?v=9ddZ15dZ-lQ&t=1m21s" target="_blank" rel="noopener">
          Meta-Path Learning for Multi-Relational Graph Neural Networks
        </a>
      </h3>
      <p class="talk-meta">
        <span class="badge oral">Oral</span>
        Learning on Graphs Conference (LoG) 2023 &middot; Virtual
      </p>
      <p class="talk-desc">
        Learning informative meta-paths in multi-relational GNNs, without handcrafted relational chains and
        without the scalability issues of brute-force relation weighting. A scoring function drives an
        incremental construction that finds the right meta-path even with many relations (e.g., knowledge graphs).
      </p>
      <p class="talk-links">
        <a href="https://www.youtube.com/watch?v=9ddZ15dZ-lQ&t=1m21s" target="_blank" rel="noopener">Watch on YouTube</a>
        <a href="https://proceedings.mlr.press/v231/ferrini24a.html" target="_blank" rel="noopener">Paper (PMLR)</a>
        <a href="https://arxiv.org/abs/2309.17113" target="_blank" rel="noopener">arXiv</a>
      </p>
    </div>
  </div>

  <!-- Alan Turing Institute Tutorial -->
  <div class="talk-card">
    <div class="talk-thumb">
      <a href="https://www.youtube.com/watch?v=mh_oCB9O4rA" target="_blank" rel="noopener">
        <img src="https://i3.ytimg.com/vi/mh_oCB9O4rA/maxresdefault.jpg" alt="Heterogeneous Graph Learning tutorial">
      </a>
    </div>
    <div class="talk-body">
      <h3 class="talk-title">
        <a href="https://www.youtube.com/watch?v=mh_oCB9O4rA" target="_blank" rel="noopener">
          Heterogeneous Graph Learning &mdash; Hands-on Tutorial
        </a>
      </h3>
      <p class="talk-meta">
        <span class="badge">Tutorial</span>
        Alan Turing Institute &middot; with Steve Azzolin and Antonio Longa
      </p>
      <p class="talk-desc">
        Hands-on tutorial introducing heterogeneous graph learning: data structures, message passing
        on multi-relational graphs, and practical PyTorch Geometric examples for node and link prediction.
      </p>
      <p class="talk-links">
        <a href="https://www.youtube.com/watch?v=mh_oCB9O4rA" target="_blank" rel="noopener">Watch on YouTube</a>
        <a href="https://github.com/steveazzolin/gdl_tutorial_turinginst" target="_blank" rel="noopener">Slides &amp; code</a>
      </p>
    </div>
  </div>

</div>
