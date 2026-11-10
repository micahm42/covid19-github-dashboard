# COVID-19 Across America — GitHub Pages Starter

A responsive dark analytics dashboard for a COVID-19 data visualization assignment.
It embeds Tableau Public views and includes a CSV copy of the supplied `US_Covid.xlsx`
workbook for the dashboard summary figures.

## Project contents

```text
covid19-github-dashboard/
├── index.html
├── README.md
├── .nojekyll
├── assets/
│   ├── css/
│   │   └── styles.css
│   └── js/
│       └── dashboard.js
└── data/
    └── us_covid.csv
```

## Current status

- Visualization 1: connected to the published Tableau Public view:
  `Manuel_Lollipop / Sheet1`
- Visualizations 2–5: styled placeholders. Add each chart's Tableau URL in
  `assets/js/dashboard.js` when those charts are published.
- Summary metrics: calculated from the six selected states in `data/us_covid.csv`.
- The supplied workbook does not include a reporting date/date range. Confirm that
  information from the original source before adding a date claim to the site.

## Suggested five-chart plan

The five chart slots are currently set up with five distinct chart types from the
assignment's approved list:

1. Dot plot / lollipop — total cases across six selected states.
2. Waffle — each state's share of combined total cases.
3. Donut — each state's share of combined reported deaths.
4. Side-by-side bar — total cases compared with cases in the last seven days.
5. Bar — case rate per 100,000 residents.

These are starter recommendations. Confirm the final goals, calculations, and chart
choices against the assignment rubric and your instructor's expectations.

## Add another Tableau chart

1. Publish the chart to Tableau Public.
2. Open the published view and choose **Share**.
3. Copy the view URL or embed URL.
4. Open `assets/js/dashboard.js`.
5. Find the matching chart object and replace its empty `tableauUrl: ""` with a URL
   in this form:

   ```js
   tableauUrl: "https://public.tableau.com/views/WORKBOOK_NAME/SHEET_NAME?:showVizHome=no&:embed=true",
   ```

6. Save and refresh the website.

Do not paste the entire `<div>...</div><script>...</script>` embed snippet into the
JavaScript file. This starter uses Tableau's published view URL in an iframe.

## Preview locally

Because the dashboard fetches a CSV file, preview it through a local web server rather
than opening `index.html` directly.

If Python is installed:

```powershell
py -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Stop the server with `Ctrl+C`.

## Publish with GitHub Pages

1. Create a new GitHub repository, for example `covid19-github-dashboard`.
2. Extract this ZIP file.
3. Upload the **contents** of this folder to the repository root (so `index.html`
   is at the top level, not buried inside another folder).
4. Commit the files to the `main` branch.
5. In GitHub, open **Settings → Pages**.
6. Under **Build and deployment**, choose **Deploy from a branch**.
7. Select branch `main` and folder `/ (root)`, then save.
8. Wait for GitHub Pages to publish. The site URL will appear in the Pages settings.

## Important data and privacy notes

- Tableau Public views are public. Do not embed data that should remain private.
- The dashboard's CSV is also public once committed to a public GitHub repository.
- These values are a snapshot from the supplied workbook, not live COVID-19 statistics.
- The workbook contains 50 state rows and the fields `State`, `Total Cases`,
  `Total Deaths`, `CasesInLast7Days`, and `RatePer100000`.
- Add the original dataset source and reporting date/range to the page once verified.
