# King of Tokyo Tournament Manager

A single-file web app for organising and running **King of Tokyo** and **King of New York** tournaments. Manage your player roster, generate tables, run timed games, record results, track standings and run the Grand Finals.

The app runs directly in a modern web browser. There is no installation, build step, server or backend required.

## Features

### Tournament setup

- **Quick Start templates** for common tournament sizes:
  - **Brawl:** 3 players per table, 1 game per round, 2 rounds, 35-minute timer.
  - **Melee:** 4 players per table, 2 games per round, 2 rounds, 45-minute timer.
  - **Clash:** 5 players per table, 2 games per round, 3 rounds, 50-minute timer.
  - **Showdown:** 6 players per table, 3 games per round, 3 rounds, 60-minute timer.
- Configure table sizes from **2 to 6 players**.
- Configure **1 to 3 games per round**.
- Configure **1 to 3 preliminary rounds**.
- Set the game timer from **5 to 60 minutes**, in 5-minute increments.
- Enable or disable tournament bonus points and monster tags.
- Lock tournament settings to prevent accidental changes during setup or play. Unlock them to make changes and generate a new tournament.
- An overview estimates the tournament duration using the selected settings. Estimates include approximately 5 minutes between games and are based on a four-player game duration, so larger tables may take longer.

### Player roster and monsters

- Add one or more player names, separated by commas or new lines.
- Quickly add up to **four random monsters** from the app's built-in monster pool. Already-added monster names are excluded from the random selection.
- Remove players from the roster before generating a tournament.
- Assign and track monster selections for players during tournament rounds.
- Toggle monster tags on or off to show or hide the short monster labels alongside player names.

### Running the tournament

- **Round 1** randomly distributes players as evenly as possible across tables.
- Subsequent rounds use current standings to seed tables, placing the highest-ranked players at Table 1.
- Players remain at the same table for all games within a round.
- Drag and drop players between tables to adjust seating.
- Each table has its own visual theme to make tables easier to distinguish.
- A tournament timeline shows the round and game progression.
- Start, pause and resume the game timer.
- Adjust the active game timer by **+5 or -5 minutes**.
- Skip a game that has not started, or restore a skipped game before proceeding. Skipped games remain visible in the tournament progression but do not contribute scores.
- Tables can be submitted manually, or results are submitted automatically once every player at the table has a rank.
- The app automatically pauses the round timer when all tables have completed their results.

### Timer sound and announcements

- Optional spoken timer announcements use the browser's built-in speech synthesis.
- Announcements include halfway (where applicable), 10 minutes, 5 minutes, 1 minute, 30 seconds, 10 seconds and time-up call-outs.
- Enable or disable sound effects in Settings.
- Mute or unmute announcements and adjust the volume using the controls beside the game clock.
- Sound preferences are saved separately for the current browser/device.
- Speech support depends on the browser. Some mobile browsers require an initial user interaction before speech can play.

### Scoring and leaderboard

- Tournament points are awarded by finishing position:
  - **1st:** 3 points
  - **2nd:** 2 points
  - **3rd:** 1 point
  - **4th–6th:** 0 points
- Optional bonuses award **1 additional point each**:
  - **Smasher:** most kills.
  - **Tanker:** most health.
  - **Collector:** most Power cards.
  - **Harvester:** most energy.
- Bonus awards are entered for each player at the end of a game. Tied players can each receive the relevant bonus.
- Record each player's finishing rank, Victory Points (VP), Health Points (HP) and bonuses.
- Players are ranked by:
  1. Total tournament points.
  2. Number of game wins.
  3. Total Victory Points.
  4. Total Health Points.
- The leaderboard tracks games played, wins, tournament points, bonus points, VP and HP.

### Grand Finals

- Trigger the Grand Finals once the preliminary rounds are complete.
- The top seeds, up to the configured table size, play in the Grand Finals table.
- Remaining players are distributed into consolation pods.
- The Finals consist of one decisive game.
- Only results from the Grand Finals table count towards the final tournament standings; consolation pod results are excluded from scoring.
- Crown the champion when the Finals results have been recorded, with a confetti celebration.

### Appearance, rules and data

- Switch between **dark mode and light mode** from the header Menu.
- The selected theme is saved in the browser.
- Built-in **Tournament Rules & Guidelines** cover drafting, play, rounds, scoring, clarifications and general guidance. The rules modal can also be opened directly with the `#rules` URL hash.
- Tournament progress is automatically saved in the browser's `localStorage`.
- Export the tournament state to a JSON file and import it later to continue.
- Existing saved tournament data is migrated when necessary to support newer game and round structures.

## Getting started

1. Download the HTML app file (for example, `king_of_tokyo_tournament_manager_v2_27_2.html`).
2. Open the file in a modern web browser.
3. Add players to the roster, or use **Quick Add** to add random monsters.
4. Choose a Quick Start template or configure the tournament settings.
5. Select **Generate** to create the first round.
6. Start each game, enter player results and progress through the rounds.
7. Use the **Leaderboard** tab to review standings and trigger the Grand Finals when ready.

Use **Menu → Export Data** to save a backup of the tournament. Use **Menu → Import Data** to restore a previously exported JSON file. **Reset Tournament** clears the current tournament, so export first if you want to keep a copy.

## Browser requirements

The app loads the following resources from external CDNs:

- Tailwind CSS
- Font Awesome icons
- Inter font from Google Fonts

An internet connection is required to load these resources. Core tournament state is stored locally in the browser. Clearing browser site data or using a different browser/device may remove or separate the saved tournament, so export regular backups.

Spoken announcements require browser support for the Web Speech API and may not be available in every browser.

## Tech

- HTML, CSS and vanilla JavaScript.
- Tailwind CSS loaded from a CDN.
- Font Awesome icons and the Inter web font.
- Tournament state is held in `window.tournament` and saved to `localStorage` under `kot_tournament_state`.
- Theme preference is saved under `kot_theme`.
- Timer sound preferences are saved separately under `kot_sound`.
- No package installation, build process, backend or external database.

## Notes

King of Tokyo and King of New York are products of IELLO. This is an unofficial fan-made tournament tool and is not affiliated with or endorsed by IELLO.

The app's scoring, timing estimates, seating and tournament workflows are intended as management aids. Tournament Managers have the final say on rules interpretations and results.
