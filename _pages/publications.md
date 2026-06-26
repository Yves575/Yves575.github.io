---
layout: page
permalink: /publications/
title: publications
description: "total: 4"
nav: true
nav_order: 2
_styles: |
  .post .post-description {
    margin-bottom: 2rem;
  }

  .publications {
    margin-top: 2rem;
  }

  .publications h2.bibliography {
    margin-top: 2rem;
    padding-top: 1rem;
    font-size: 2rem;
  }

  .publications ol.bibliography li {
    margin-bottom: 2rem;
  }

  .publications ol.bibliography li > .row {
    display: grid;
    grid-template-columns: 200px minmax(0, 1fr);
    column-gap: 2rem;
    align-items: start;
    margin-right: 0;
    margin-left: 0;
  }

  .publications ol.bibliography li .abbr {
    position: relative;
    width: 200px;
    max-width: 200px;
    margin-bottom: 0;
    padding: 0;
  }

  .publications ol.bibliography li .abbr figure {
    margin: 0;
  }

  .publications ol.bibliography li .preview {
    display: block;
    width: 200px;
    height: 120px;
    object-fit: cover;
    object-position: top left;
    border-radius: 4px;
  }

  .publications ol.bibliography li .abbr abbr {
    position: absolute;
    right: 6px;
    bottom: 6px;
    z-index: 1;
    width: auto !important;
    margin-bottom: 0;
    padding: 0.18rem 0.35rem;
    border-radius: 3px;
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.25);
    color: #fff !important;
    font-size: 0.65rem;
    letter-spacing: 0;
  }

  .publications ol.bibliography li .abbr abbr div,
  .publications ol.bibliography li .abbr abbr a {
    color: #fff !important;
  }

  .publications ol.bibliography li [id] {
    width: auto;
    max-width: none;
    padding: 0;
  }

  .publications ol.bibliography li .links {
    margin-top: 0.75rem;
  }

  .publications ol.bibliography li .links .btn {
    margin: 0 0.75rem 0.25rem 0;
    border-color: var(--global-divider-color);
    color: var(--global-text-color);
    text-transform: uppercase;
  }

  @media (max-width: 575.98px) {
    .publications ol.bibliography li > .row {
      grid-template-columns: 1fr;
      row-gap: 1rem;
    }

    .publications ol.bibliography li .abbr,
    .publications ol.bibliography li .preview {
      width: 100%;
      max-width: 280px;
    }

    .publications ol.bibliography li .preview {
      height: 168px;
    }
  }
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>

<script>
  document.querySelectorAll(".publications .links").forEach((links) => {
    const buttons = Array.from(links.querySelectorAll(".btn"));
    const paperButton = buttons.find((button) => button.textContent.trim() === "PDF");
    const doiButton = buttons.find((button) => button.textContent.trim() === "DOI");

    if (paperButton) {
      paperButton.textContent = "PAPER";
      doiButton?.remove();
    } else if (doiButton) {
      doiButton.textContent = "PAPER";
    }
  });
</script>
