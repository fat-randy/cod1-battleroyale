# CoD 1.1 Battle Royale Gametype (fat-randys update)

This is an update for the original Battle Royale Mod by [cod1raph](https://github.com).

## Features
- **Winner Stats:** Winners can now be stored in the `stats.db`.
- **In-Game HUD:** New CVars allow you to toggle the display of top kill rounds and overall winners directly in the HUD.

## Installation

1. **Replace GSC File:**  
   Replace the original file at `server/maps/MP/gametypes/br.gsc` with the version provided in this fork.

2. **Update Configuration:**  
   Add the following CVars to your `main/br.cfg` (or use the `br.cfg` from this fork):

   ```cfg
   // [bool] Show Top 3 Killrounds in HUD
   set br_show_topkills "1"

   // [bool] Show Winners Top 3 in HUD
   set br_show_winners "1"
   ```

## Database Setup (SQLite)

It may be necessary to manually update your `stats.db`. You need to add the `match_winners` table using the following command:

**Table structure:**
- `name` (TEXT)
- `wins` (INTEGER)
- `total_kills` (INTEGER)
- `lastseen` (INTEGER)

**SQL Command:**
```sql
CREATE TABLE match_winners (
    name TEXT PRIMARY KEY, 
    wins INTEGER, 
    total_kills INTEGER, 
    lastseen INTEGER
);
```

## Statsviewer:

If you are hosting the Gameserver on same machine with a webserver you can use https://github.com/fat-randy/cod1-battleroyale-php-stats-viewer to view your stats!

---
*Screenshot:*
<img width="1702" height="955" alt="Screenshot 2026-04-23 131519" src="https://github.com/user-attachments/assets/7634da63-839f-4fd1-be04-7b1ce506791d" />



