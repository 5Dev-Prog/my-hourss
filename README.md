# My Hours

A buildless, mobile-first PWA for tracking shifts and cash pay from Beauty Bar and Regal Jewelers.

## Run and install

Serve this folder over HTTP for local testing or HTTPS for use on a phone. If Python is installed, run the following from this folder and open **http://localhost:8080**.

```sh
python -m http.server 8080
```

For Netlify, deploy this folder as the site root. If linking the parent repository, set the base directory to `my-hours`. The included configuration publishes the current directory with no build command.

Open the hosted app once while online so the service worker can cache it. On iPhone, open the page in Safari and tap **Share → Add to Home Screen**. On Android, use **Install** when the browser offers it. The app works offline once its initial cache is ready. The optional Outfit font has a system-font fallback.

## Use the tracker

- Set the usual hours for both jobs during setup. Weeks run Sunday through Saturday. Template changes apply starting the current Sunday. A date-specific override takes precedence.
- Tap **Edit hours** to log both jobs for one date. Enter hours after breaks, such as `4.5` for four and a half hours. Use zero for a day off or leave a job blank to keep it unlogged. Use **Scheduled** to edit planned hours for that date, or tap a job’s checkmark to log its planned hours.
- Open **Week totals** for the daily breakdown. **Overview** charts worked hours by job for a week or month.
- **Profile** lets you edit rates and manage data. Current rates apply to all worked entries. Cash is rounded to cents per job per day before totaling.
- Data is stored in the browser on that origin. To move to another phone, export JSON on the old phone and import it on the new one. Import replaces the current tracker after confirmation. Keep the exported file if you clear browser data.

When changing the app shell, increment the cache version in `sw.js` so returning users receive the new files.
