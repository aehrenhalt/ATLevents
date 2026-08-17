# Cute ATL

A one-month-at-a-time calendar of real events in **Reynoldstown, Inman Park, Old Fourth Ward, Poncey-Highland, Midtown** — plus the Beltline.

Everything lives in a single `index.html`. No build step, no dependencies, no server. Double-click it and it works.

---

## Adding or editing an event

Open `index.html`, search for `EVENTS`, and add an object to the array:

```js
{
  name: "Movie Monday",
  venue: "Ladybird Grove & Mess Hall",
  hood: "o4w",                       // reynoldstown | inman | o4w | poncey | midtown | beltline
  when: { weekly: 1 },               // see rules below
  time: "7:30 PM",
  end:  "10:00 PM",                  // optional
  cost: "Free",                      // optional — "Free" / "No cover" gets a green tag
  note: "A cult classic on the jumbotron…",
  url:  "https://www.ladybirdatl.com/happenings"
}
```

### `when` rules

| Rule | Meaning |
|---|---|
| `{ weekly: 1 }` | Every Monday (Sun=0 … Sat=6) |
| `{ weekly: 5, every: 2, anchor: "2026-08-21" }` | Every other Friday, counting from that real date |
| `{ monthly: 5, nth: 1 }` | 1st Friday of each month (`nth: -1` = last) |
| `{ date: "2026-09-19" }` | One-off |
| `{ dates: ["2026-09-05","2026-09-06"] }` | A few specific days |

Add `from: "YYYY-MM-DD"` and/or `until: "YYYY-MM-DD"` to any rule to bound a season — that's how *Cocktails in the Garden* stops after Sept 24.

---

## Putting it online

**GitHub Pages from a private repo requires a paid plan** (Pro, Team, or Enterprise — Pages on free accounts only serves public repos). Pick whichever fits:

**A. Private repo + GitHub Pro** (~$4/mo) — private source, and you can restrict who can view the site.

```bash
cd ~/atl-cute-calendar && git init && git add -A && git commit -m "Cute ATL calendar"
gh repo create cute-atl --private --source=. --push
```

Then Settings → Pages → Source: `main` / root.

**B. Public repo, free Pages.** Same commands with `--public`. There's nothing private in here — it's a list of bars and farmers markets.

**C. Skip GitHub.** Open `index.html` from Finder, or drag the folder onto [Netlify Drop](https://app.netlify.com/drop) for a free URL in about ten seconds.

---

## Where these events came from

Verified **August 17, 2026**. Bars change their nights without telling anyone, so every event links back to the venue's own page — check before you go.

- [Ladybird Grove & Mess Hall](https://www.ladybirdatl.com/happenings) — Movie Mondays, Chess Knight, Saturday DJ
- [The Krog District](https://www.thekrogdistrict.com/events) — trivia, concert series, run club, markets
- [Stereo ATL](https://www.stereoatl.com/) — nightly vinyl sets
- [High Museum Friday Nights](https://high.org/friday-nights/) — High Frequency Friday, Friday Jazz
- [Piedmont Park Conservancy](https://piedmontpark.org/calendar/) — Green Market, yoga, workshops
- [Midtown Alliance](https://www.midtownatl.com/events) — Midtown recurring + one-offs
- [Atlanta Botanical Garden](https://atlantabg.org/plan-your-visit/atlanta-garden-calendar/cocktails-in-the-garden/) — Cocktails in the Garden
- [The Roof at Ponce City Market](https://poncecityroof.com/skyline-park) — Peak of the Week
- [Plaza Theatre](https://www.plazaatlanta.com/now-showing/) — Rocky Horror w/ LDOD
- [Freedom Farmers Market](https://freedomfarmersmkt.com/) — Saturdays at the Carter Center
- [Dad's Garage](https://www.dadsgarage.com/) — improv, Thu–Sat
- [Wheelbarrow Festival](https://www.wheelbarrowfestival.com/) · [Beltline Lantern Parade](https://beltline.org/art/lantern-parade/)

Good accounts to mine for new listings: `@ladybirdatlanta`, `@stereo.atl`, `@krogstreetmarket`, `@poncecitymarket`, `@highmuseumofart`, `@piedmontpark`, `@atlantabeltline`, `@freedomfarmersmkt`.
