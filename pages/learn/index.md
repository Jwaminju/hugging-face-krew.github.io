---
layout: learn
title: Learn
permalink: "/learn/"
eyebrow: "Learn Hub"
description: "Hugging Face KREW의 문서형 프로젝트 목록입니다."
learn_toc:
  - id: projects
    title: 프로젝트 목록
---

<section id="projects" class="learn-section">
  <h2>프로젝트 목록</h2>
  <div class="learn-list-table">
    {% for project in site.data.learn.projects %}
    {% assign project_meta = project[1] %}
    {% assign intro_url = project_meta.sections[0].items[0].url %}
    {% assign intro_page = site.pages | where: "permalink", intro_url | first %}
    <a class="learn-list-row" href="{{ intro_url }}">
      <span class="learn-list-row__title">{{ intro_page.title | default: project_meta.title }}</span>
      <span class="learn-list-row__meta">{{ intro_page.description | default: project_meta.title }}</span>
    </a>
    {% endfor %}
  </div>
</section>
