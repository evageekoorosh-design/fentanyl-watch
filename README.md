# Fentanyl Drug Supply Watch

A public-health dashboard about what's in the U.S. illicit drug supply: how dangerous counterfeit pills are, which new substances are being mixed into fentanyl, what's happening with overdose deaths, trafficking and policy, and how few people get treatment.

**Live site:** `https://<your-username>.github.io/fentanyl-watch/` *(update after publishing)*

![Dashboard preview](preview.png)

---

## The problem

Most overdose deaths today aren't from a drug people chose to take. They come from what's hidden in it: fentanyl pressed into pills that look like oxycodone or Xanax, or veterinary sedatives and stronger opioids cut into powder. The data that could warn people is scattered across CDC releases, DEA lab reports, research papers and the news, and it's written for officials rather than for the people at risk.

## What I built

A single-page dashboard that pulls those sources together for a general audience, especially anyone getting drugs from unregulated sources, with a harm-reduction tone.

- **Overdose safety box** at the top: what to do in an overdose and how to lower risk.
- **Supply snapshot:** headline numbers plus two charts. Predicted overdose deaths fell from 77,306 to 66,478 in a year (CDC provisional data). The share of DEA-tested fentanyl pills with a potentially lethal dose fell to 29% in fiscal 2025, down from 70% in 2023.
- **What to watch for:** cards on counterfeit pills, xylazine, medetomidine, nitazenes, carfentanil and fentanyl in stimulants. Each card says what the substance is, where it shows up, whether naloxone works on it, and the latest figure. A chart tracks medetomidine lab reports, which went from 247 in 2023 to 8,233 in 2025.
- **News feed** you can filter by topic: precursor chemicals and trade with China, India and Mexico, the border, laws, pharma settlements and treatment policy.
- **Treatment gap:** only 16% of people who needed substance use treatment got it in 2025, and only 15.7% of people with opioid use disorder got medication (SAMHSA NSDUH).
- **Get help:** crisis lines, treatment locators, and where to get naloxone and test strips.

## Data sources

- **CDC / NCHS:** provisional drug overdose death counts, the medetomidine situation summary, and MMWR reports on carfentanil.
- **DEA:** lab testing of fentanyl pills and xylazine prevalence.
- **ONDCP / CDC:** April 2026 health advisory on medetomidine.
- **SAMHSA:** 2025 National Survey on Drug Use and Health.
- **Peer-reviewed research:** a drug-checking study of fentanyl in methamphetamine and cocaine (*Drug and Alcohol Dependence*, 2023).
- **News coverage** of trafficking, precursors, policy and pharma: AP, Axios, the Congressional Research Service and others.

Every figure links back to its source in the **Sources** section at the bottom of the page. The data is a snapshot current to November 10, 2026.

## Design choices

- **Plain language for the people at risk.** Each substance card answers the practical questions first: where it shows up, and whether naloxone will help.
- **Honest about uncertainty.** Notes flag that provisional CDC counts get revised, that seizure data shows only what police found, and that lower pill purity doesn't mean pills are safe.
- **Safety first.** The overdose response box sits above every chart.
- **Accessible and responsive.** It works from phone to desktop, follows the system's light or dark mode, and gives every chart a screen-reader label. Tooltips show exact values on hover.

## Tech

- One self-contained `index.html` file, with no build step and no server.
- Charts are drawn with [D3.js](https://d3js.org) v7, loaded from a CDN.
- The data is embedded as JSON in the page (`window.DASH_DATA`), so you can update figures by editing that block.
- It was first prototyped as an interactive dashboard in Claude, then exported to this standalone page.

## Run it locally

Download `index.html` and open it in any browser.

## Publish on GitHub Pages

1. Create a new public repository, for example `fentanyl-watch`.
2. Upload `index.html`, `README.md` and `preview.png`.
3. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then click **Save**.
4. After a minute or two, the site is live at `https://<your-username>.github.io/fentanyl-watch/`. Put that link at the top of this README.

## Add it to a Notion portfolio

Choose one of these:

- **Embed the live page:** on your Notion page, type `/embed`, paste the GitHub Pages link, and drag the block's edges to resize it.
- **Project card:** add `preview.png` as an image, a short summary, and two links, **Live site** and **Code** (the repo).

## Disclaimer

This page is for education and public-health awareness, not medical advice. If someone may be overdosing, call 911 and give naloxone.
