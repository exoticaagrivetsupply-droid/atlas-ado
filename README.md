# ATLAS ADO Sales & Market Intelligence Suite — v2

Manager → Supervisor → ADO. Area profiling, herd-level market sizing, scorecards, coaching and rewards.

One `index.html`. Saves on the phone, syncs through Supabase, installs as an app. No build step.

---

## The chain of command

| Seat | Sees | Can do |
|---|---|---|
| **Area Manager** (the admin) | every area, every supervisor, every ADO | areas, accounts, targets, settings, feed-intake table, score weights, reward ladder, approves and releases rewards |
| **Supervisor** | one area only — every ADO in it | scores the team, writes coaching notes, proposes rewards, works customers and market |
| **ADO / Technician** | their own territory only | profiles the market, sells, visits, follows up, sees their own scorecard and coaching |
| Encoder | area they are placed in | types in sales and visits only |
| Viewer | area they are placed in | reads dashboards and reports |

An ADO belongs to an **area**. An area has **one supervisor**. Every record an ADO makes carries their id, so it rolls up through their area to the manager without anybody re-entering anything. Manager and supervisor get an **Area / ADO picker** at the top of every screen; set it and the whole app re-scopes.

**Setup order matters:** Areas → Supervisors (role Supervisor + area) → ADOs (role ADO + area) → barangays assigned to ADOs → customers. An ADO with no area rolls up to nobody; the Areas screen flags them in red.

---

## The flow, point by point

**1. Profile the area market — raisers, dealers, and both.** One `Customers` list. Each record has two tick boxes: *is a store dealer* and *raises hogs*. Tick both and it is one record, not two. A record starts as a **Prospect** and becomes live on its first order (the app flips it for you).

**2. Where does the raiser buy his feeds?** Every raiser has a *Buys feeds from* field pointing at a dealer record. From that one link the app builds: which raisers source at each outlet, what volume flows through it, and what share of that outlet is ours.

**3. What brand are they using?** Brand is recorded **per stage**, not per farm — because a farm is often Atlas on starter and a rival on finisher. That is where switches actually start.

**4. Heads per stage.** The Herd Profile screen takes a line per stage: gestating sows, lactating sows, boars, suckling, starter, grower, finisher — each with head count and the brand actually fed. A stage can appear twice if part of it is on each brand.

Heads become bags through the intake table (bags per head per month, editable in Settings):

| Stage | Default |
|---|---|
| Gestating sow | 1.2 |
| Lactating sow | 2.8 |
| Boar | 1.2 |
| Suckling piglet | 0.2 |
| Starter / weanling | 0.6 |
| Grower | 1.2 |
| Finisher | 1.6 |

**Change these to your own field figures and every market number in the app moves with them.**

**5. Volume per brand per area.** Market → Volume by brand: total bags a month, split by brand, plus a **barangay × brand matrix**, plus a **stage table** showing where you win and lose. The stage with the lowest share is your cheapest door in.

**6. Volume per dealer per area.** Market → Volume by dealer: every outlet ranked by throughput, how many raisers source there, and what percentage of it is ours. Manager, supervisor and ADO all see this at their own scope.

**7. A dashboard per seat.** ADO gets targets, KPIs, their own scorecard and their coaching notes. Supervisor gets their area plus a ranked team list and an attention list. Manager gets every area, drills into any one, and sees rewards waiting for approval.

---

## The scorecard — the basis for guidance and rewards

Six parts, weighted, out of 100. Every figure is read from the records, so nobody can talk their way into a better number.

| Part | Default weight | Full marks at |
|---|---|---|
| Target achievement | 40 | bags = target |
| New customers | 15 | 3 first-time buyers (editable) |
| Switch wins | 15 | 50 bags/month converted (editable) |
| Territory coverage | 10 | every barangay has a live buyer |
| Field activity | 10 | the monthly visit quota |
| Follow-through | 10 | every due follow-up closed on time |

Weights are editable in Settings. Tiers: **Platinum 90+ · Gold 75–89 · Silver 60–74 · Bronze 45–59 · below 45 gets coaching, not cash.** Each tier has a peso value, plus an optional bonus per bag over target.

**Reward flow:** supervisor proposes → manager approves → manager marks released. Nothing pays out on one person's say-so, and every step is stamped with a name.

**Coaching flow:** open any scorecard, hit *Write a note*. The app pre-fills the wording from that ADO's weakest part; edit it in your own words, attach **one action** and a **date**. It lands on the ADO's dashboard the moment it syncs, and they mark it done.

**Activity trail** (Team → Activity trail) shows everything each ADO has entered, by day: orders, visits, farms mapped, herds profiled, follow-ups closed, switches won, problems logged and problems resolved.

One thing worth watching: if a column in the team matrix is red across *every* ADO, that is not a people problem. It is a target, a price or a route problem — fix it once at the top.

---

## Problems & Needs — the ADO as the company's eyes on the farm

An ADO who only takes orders is a delivery boy. The one who asks *what is hurting you, and what would help* is the reason the farm stops shopping around. This module makes that question part of the routine instead of something that depends on who is in a good mood.

**On every farm page** there is a check-in row: when they were last asked, how many days ago, and an **Ask now** button. The standing cadence is every 60 days (editable in Settings). Anybody overdue surfaces automatically in Today's priority visits, and the Problems screen lists them with a one-tap button each.

**Logging a problem** captures: the category (17 of them — scouring, repeat breeding, ASF scare, dealer out of stock, no buyer, short of capital, needs training…), how bad it is, what they said in their own words, and then the important field: **what would actually help them.** That is picked from a list — vet visit, medicine, vaccine, dewormer, feeding programme, trial bags, training, biosecurity supplies, credit terms, delivery, breeding stock, equipment, help finding a buyer — with a quantity, a unit and a date needed.

Anything with a "what would help" attached lands on the **Demand board**.

**The Demand board** (supervisor and manager) gathers every request in the area into one screen: grouped by what is being asked for, how many farms, total quantity, the earliest date promised, and which barangays. One button books a whole group at once — you name the dealer or distributor and the date, and every ADO who raised it sees *Booked with…* on their own screen. A second table breaks it down by barangay so a delivery run can be planned in one trip.

At the bottom sits a **ready-written proposal**: what still needs booking, what is already booked and with whom, and the market figures behind it. Copy it into a message to your distributor, or download it as a text file.

**Two things the app draws out that a pile of individual complaints never would:**

- On the Problems screen, a bar chart of what the area is actually struggling with. A problem appearing on a third of the farms is not a farm problem. It is an area problem, and it usually has one answer that works everywhere.
- Every resolved problem keeps its resolution note — what actually fixed it. That is the answer you hand the next farm with the same complaint, instead of working it out again.

**It counts on the scorecard.** A seventh component, *Customer care*, worth 10 points: raisers actually asked what they need this month, against the number due under the cadence. An ADO cannot score full marks by selling alone. If it reads zero, the coaching note writes itself.

Default weights are now: target 35 · new customers 12 · switch wins 15 · coverage 10 · field activity 10 · follow-through 8 · customer care 10.

---

## Install

1. Unzip. Upload the 8 files (not the folder, not the zip) to a public GitHub repo.
2. Settings → Pages → Deploy from a branch → `main` / `(root)`.
3. Open the link. Android Chrome: menu → Install app. iPhone: **Safari** → Share → Add to Home Screen. Computer: Chrome/Edge → install icon in the address bar.

Editing `index.html` later? Bump `const CACHE = 'atlas-v2'` in `sw.js` to `atlas-v3`, or the phones keep serving the cached copy.

## Supabase

Run once in the SQL editor:

```sql
create table if not exists atlas_state (
  id text primary key,
  rev int default 0,
  data jsonb,
  updated_at timestamptz default now(),
  updated_by text
);
alter table atlas_state enable row level security;
create policy atlas_rw on atlas_state for all to anon using (true) with check (true);
```

Then More → Cloud sync → Set up the first connection (Project URL + **anon** key). Copy the sync code and give it to everybody else; they paste it instead of creating accounts. Only the manager ever sees the setup screen.

v2 uses its own storage keys (`atlas_v2`, `atlas_cloud2`), so it will not collide with a v1 install on the same phone or the same Supabase table.

---

## Editing it

One file, in order: data model and stages → hierarchy → market sizing → customer state and KPIs → scorecard engine → shell → dashboards → customers and herd editor → sales → field → market → team, coaching, rewards → areas, settings, users → sign-in → cloud sync.

To change how heads convert to bags, edit `DEFRATE` (or just use Settings). To add a stage, add a line to `STAGES`. To add a scorecard part, add it to `COMP` and give it a weight.
