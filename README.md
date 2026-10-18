# Orbyt Laptops: Website Behaviour Tracker

A laptop buying guide (8 real models, filters, comparison, shortlist, buy links) with a built-in behaviour tracker. It records how a visitor clicks, moves, and scrolls, and shows the results on top of the page and in a side panel. It is a single HTML file with no dependencies and no server, so no data leaves your browser.

## Features

- **Click heatmap**: hot spots drawn over the page where clicks cluster
- **Click dots**: numbered markers in click order, with rage clicks in red
- **Mouse path**: the cursor trail across the whole page
- **Scatter map**: every click plotted on a full-page minimap, coloured by order, with a box showing the current viewport
- **Scroll depth**: deepest point reached, plus scroll event count
- **Section dwell time**: seconds each page section was actually in view (paused while the tab is hidden)
- **Element visibility**: live indicator of which sections are on screen (IntersectionObserver)
- **Rage click detection**: three fast clicks in the same spot
- **Event log**: timestamped clicks, scroll milestones, section enter/leave, tab hidden/visible
- **Undo, reset, and JSON export**

## How to run

1. Download `index.html`.
2. Open it in any modern browser (double-click it).
3. Click the **Tracker** button (bottom right) and press **Start tracking**.
4. Browse the store: filter laptops, open FAQs, scroll, click around.
5. Switch on **Heatmap**, **Click dots**, or **Mouse path**, check the **Scatter** and **Log** tabs, then **Export JSON**.

Clicks inside the tracker panel are never recorded. Press `Esc` to close the panel.

## The demo store

- Filter by category, search, and sort by price, battery or weight
- Details window with specs and pros for each laptop
- Shortlist (saved in your browser) with total and a copy-list button
- "Buy" buttons open Amazon, AliExpress or eBay search results for the exact model, so links never break
- Laptop pictures are inline SVG illustrations. To use real photos, add an `img` URL to a product in the `P` array and swap it into the `pic()` function
- Prices and specs are indicative. Edit the `P` array in the script to update them
- The price-alert form only saves on the current device; connect a form service to send real emails

## Exported data

`tracking-data.json` contains: page title, viewport size, page height, tracked seconds, max scroll depth, scroll events, seconds the tab was hidden, rage click count, seconds in view per section, every click (`x`, `y`, time, element, section), sampled mouse moves, and the event log.

## Customising

- Change the store content in the `<main>` markup. Any element with a `data-sec="Name"` attribute becomes a tracked section.
- Colours and fonts are CSS variables at the top of the `<style>` block. Dark mode follows the system setting.
- Mouse sampling (every 60 ms, last 4,000 points) is set in the `mousemove` handler.

## Built with

HTML, CSS, and vanilla JavaScript (Canvas API, IntersectionObserver).
