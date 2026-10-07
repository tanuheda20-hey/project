# PaaniPact

**A community-first prototype for fair, explainable irrigation turns when several farms share one pump.**

PaaniPact demonstrates a simple way to turn a group’s stated needs, waiting time, rain forecast and available pump hours into a schedule that people can review together. It is a hackathon prototype—not an agronomy tool or a pump controller.

## Run it

This is a no-build static website. Open `index.html` in a browser, or serve the folder locally:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

There are no dependencies, API keys, backend services or external assets. The demo works offline after the files are available locally.

## Demo features

- A sample group of five farmers and one shared pump.
- Recalculates the suggested queue when you change available pump hours or toggle the sample rain forecast.
- Shows each suggested slot, an explanation, partial allocations and requests that need another planning window.
- Add or remove sample farmers.
- Download the current demo schedule as CSV.
- Saves changes to this browser only with `localStorage`; use the reset button to restore the sample group.
- Responsive layout with keyboard-accessible controls and print styling.

## Scheduling logic

The prototype uses a transparent, deterministic score. It is intentionally simple so a community can inspect and challenge it:

```text
priority = stated-need points
         + (days since watering × 0.9)
         + (days since last turn × 0.6)
         - 1.5 rain adjustment for medium/low stated need
```

Need points are **High = 8, Medium = 5, Low = 2**. Demo slot lengths are **High = 1.5 hours, Medium = 1 hour, Low = 0.5 hour**. Higher scores are scheduled first, with longer-waiting members used as a tie-breaker. The schedule is capped by the selected pump window.

These values are illustrative UX defaults, not scientifically validated irrigation recommendations. The crop label is informational only; this version does not calculate crop water demand, soil moisture, groundwater impact, or actual rainfall.

## Privacy and safety

- The demo uses fictional sample records and does not send data to a server.
- Do not enter sensitive personal information into a public demo.
- PaaniPact does not start, stop or control a pump.
- A real pilot would need farmer validation, an agronomist-approved model, a community-approved allocation policy, reliable local weather inputs, and clear human confirmation before any schedule is acted on.

## GitHub repository setup

### Upload using the GitHub website (no terminal)

1. Download and extract the project ZIP.
2. On GitHub, choose **New repository**, name it `paanipact`, choose public or private, and create it.
3. In the new repository, choose **Add file → Upload files**. Upload `index.html`, `README.md`, `SUBMISSION.md` and `.gitignore` from the extracted folder, then select **Commit changes**.
4. To publish a free static demo, open **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save. GitHub will provide the public Pages URL after deployment.

### Or upload from a terminal

1. Create a new **public or private** GitHub repository named `paanipact` (do not initialize it with a README if you are uploading these files).
2. Extract this project folder and open a terminal inside `paanipact`.
3. Run:

   ```bash
   git init
   git add .
   git commit -m "Build PaaniPact scheduling prototype"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/paanipact.git
   git push -u origin main
   ```

   Replace `YOUR-USERNAME` with your GitHub username. GitHub will ask you to authenticate; never put a password or token in the repository.
4. To publish a free static demo, open **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save. GitHub will provide the public Pages URL after it finishes deploying.

## Suggested next steps before claiming real-world impact

1. Ask a few local farmers or pump operators how shared turns are currently decided.
2. Ask whether “stated need,” last-turn history, or another rule would be fair and understandable.
3. Record what they disagree with; let the community, not the score alone, decide the policy.
4. Replace the sample assumptions only after validation, and report measured results rather than projected savings.

## Project structure

```text
paanipact/
├── index.html       # Self-contained interactive prototype
├── README.md        # Setup, logic, safety notes and GitHub instructions
├── SUBMISSION.md    # Hackathon-ready description and demo pitch
└── .gitignore
```
