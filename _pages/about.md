---
layout: about
title: about
permalink: /
subtitle: PhD student at University of Québec in Montréal (UQAM)

profile:
  align: right
  image: pic7.png
  image_circular: false # crops the image to make it circular
  # more_info: >
  #   <p>555 your office number</p>
  #   <p>123 your address street</p>
  #   <p>Your City, State 12345</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

### about me

I am continuing my studies at the University of Quebec in Montreal (UQAM), moving from an M.Sc. to a PhD after working on NLP methods for detecting signs of mental health conditions.

I started my PhD with a research exchange at Simon Fraser University (SFU), where I studied linguistics and worked on a project about the evaluation of literary machine translation.

### research interests

My main research interests are multilingual NLP and machine translation, with a particular focus on how translations are evaluated by readers. I am currently working on literary machine translation, where small choices in wording, style,
and structure can strongly affect the reading experience.

I am also always willing to explore other domains, in NLP or beyond, and to work on new problems that connect language, data, and human interpretation.

<style>
  .publications ol.bibliography li .title {
    display: block;
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

  .selected-publication-title-text {
    display: inline;
  }

  .publications ol.bibliography li .abbr abbr.abbr-arxiv {
    border-color: #8f1515 !important;
    background: #b31b1b !important;
  }

  .selected-publication-new {
    display: inline-flex;
    align-items: center;
    margin-right: 0.5rem;
    padding: 0.12rem 0.4rem;
    border-radius: 0.25rem;
    border: 1px solid #d6a400;
    background: #ffe08a;
    color: #4d3500;
    font-size: 0.72rem;
    font-weight: 700;
    line-height: 1.2;
    text-transform: uppercase;
    vertical-align: middle;
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
</style>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    document.querySelectorAll('a[href$="/publications/"]').forEach((link) => {
      if (link.textContent.trim().toLowerCase() === "selected publications") {
        link.textContent = "selected publication";
      }
    });

    document.querySelectorAll(".publications ol.bibliography li .abbr abbr").forEach((abbr) => {
      if (abbr.textContent.trim().toLowerCase() === "arxiv") {
        abbr.classList.add("abbr-arxiv");
      }
    });

    document.querySelectorAll(".publications .links").forEach((links) => {
      const buttons = Array.from(links.querySelectorAll(".btn"));
      const paperButton = buttons.find((button) => button.textContent.trim().toLowerCase() === "pdf");
      const doiButton = buttons.find((button) => button.textContent.trim().toLowerCase() === "doi");

      if (paperButton) {
        paperButton.textContent = "PAPER";
        doiButton?.remove();
      } else if (doiButton) {
        doiButton.textContent = "PAPER";
      }

      buttons.forEach((button) => {
        const label = button.textContent.trim().toLowerCase();

        if (label === "code") {
          button.textContent = "GITHUB";
        } else if (label === "website") {
          button.textContent = "WEBSITE";
        }
      });
    });

    document.querySelectorAll(".publications ol.bibliography li .title").forEach((title) => {
      let titleText = title.querySelector(".selected-publication-title-text");

      if (!titleText) {
        titleText = document.createElement("span");
        titleText.className = "selected-publication-title-text";

        while (title.firstChild) {
          titleText.appendChild(title.firstChild);
        }

        title.appendChild(titleText);
      }

      if (!title.querySelector(".selected-publication-new")) {
        const badge = document.createElement("span");
        badge.className = "selected-publication-new";
        badge.textContent = "New";
        title.insertBefore(badge, titleText);
      }
    });
  });
</script>
