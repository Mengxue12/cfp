# CFP Tracker

My personal list of conference deadlines (edge/fog, systems, ML systems, architecture, performance, HPC).

- `index.html`: the page (no build step, nothing to install)
- `conferences.yaml`: the data. **This is the only file you normally edit.**

## Put it online (free, ~5 minutes)

1. On github.com, click **New repository**. Name it e.g. `cfp`, set it to **Public**, and create it.
2. On the new repo page, click **Add file → Upload files**. Drag in `index.html`, `conferences.yaml` and `README.md`, then click **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then click **Save**.
4. After about a minute, your tracker is live at `https://<your-username>.github.io/cfp/`

GitHub hosts it. Your computer doesn't need to be on.

> **Private instead of public?** GitHub Pages on a private repo needs GitHub Pro. Pro is free for students through the GitHub Student Developer Pack (PhD students qualify, apply with your university email). The repo's visibility doesn't change the page itself.

## Add or update a conference

Open `conferences.yaml` on github.com, click the ✏️ pencil, edit, then click **Commit changes**. The page updates within a minute. Hard-refresh if you still see the old version.

Copy an existing block and change it:

```yaml
- name: ICPE
  full: ACM/SPEC Int'l Conference on Performance Engineering
  edition: 2027
  tags: [perf]
  ccf:              # A / B / C or empty
  link: https://icpe2027.spec.org/
  when: 2027
  where: Gothenburg, Sweden
  status: planning  # watching | planning | submitted | skip
  note: target for the characterization paper
  deadlines:
    - label: Research track
      abstract: "2026-11-09 23:59"
      paper: "2026-11-16 23:59"
      notification: "2027-01-25"   # optional, date only
      camera_ready: "2027-03-12"   # optional, date only
      tz: AoE        # AoE (default), UTC, UTC+2, UTC-7, ...
```

Rules of thumb:
- Keep dates **in quotes** and in the format `"YYYY-MM-DD HH:MM"`.
- Indentation is two spaces. No tabs.
- If every deadline of a venue has passed, the page shows next year's date as **est.** (same day, +1 year) until you put in the real one.
- Statuses and tags are free text. New ones become filter buttons automatically.

## Other bits

- **Table / Cards** switch in the top-right of the list. The table has one row per submission cycle. Hover a deadline to see it in your local time.
- **Export to calendar** downloads an `.ics` file with the upcoming (non-estimated) deadlines, each with a reminder 7 days before. Import it into Google Calendar or Apple Calendar. Re-export when you change the list.
- Times are converted to whoever is viewing the page, and the original timezone is shown next to them.
- Opening `index.html` straight from your disk won't load the data, because browsers block that. Use the GitHub Pages link. To test locally, run `python3 -m http.server` in the folder and open `localhost:8000`.
