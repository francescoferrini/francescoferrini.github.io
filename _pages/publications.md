---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed publications and preprints by Francesco Ferrini, in reverse chronological order. Topics include Graph Neural Networks (GNNs), link prediction, missing node features, heterogeneous graphs, meta-path learning, self-explainable models, and TinyML.
keywords: Francesco Ferrini publications, Graph Neural Networks, GNN, link prediction, missing features, missingness, heterogeneous graphs, meta-path learning, self-explainable GNN, relational deep learning
years: [2026, 2025, 2024, 2021]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">
{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f {{ site.scholar.bibliography }} -q @*[year={{y}}]* %}
{% endfor %}
</div>