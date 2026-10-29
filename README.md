# King of Tokyo Tournament Manager

A single-file web app for running King of Tokyo and King of New York tournaments. Add your players, generate tables, enter results and let the app handle seeding, standings and finals. Open the HTML file in a browser and you're ready to go. There is no install, build step or backend.

## Features

**Tournament setup**
- Players per table: 2 to 6
- Prelim rounds: 1 to 5
- Match timer: 5 to 60 minutes in 5 minute steps
- Add players by name (comma or new line separated), or use Quick Add to drop in 4 random monsters from every monster with official Evolution cards (29 in total, including the Monster Packs and the Godzilla set)

**Running rounds**
- Round 1 is a random Swiss draw that splits players evenly across tables
- Later rounds seed players by current standings, with the top seeds on Table 1
- Drag and drop players between tables to fix seating
- Round timer with start, pause and +/- adjustment
- Each seat has rank, VP and HP entry, with bonuses on a second line to keep cards compact
- Tables submit automatically once every player has a rank, or manually with Submit Table Results

**Scoring**
- Tournament points: 3 for 1st, 2 for 2nd, 1 for 3rd
- Bonuses (+1 point each): Smasher, Tanker, Collector and Harvester
- Standings are ranked by points, then wins, then total VP, then total HP

**Finals**
- Grand Finals table for the top seeds, with consolation pods for everyone else
- Champion crowning with confetti

**Data**
- Progress saves automatically to your browser's localStorage
- Export and import the full tournament as JSON
- Built-in tournament rules reference

## Getting started

1. Download `king_of_tokyo_tournament_manager.html`.
2. Open it in any modern browser.
3. Add players, choose your settings and click **Generate Tournament**.

The page loads Tailwind CSS, Font Awesome and the Inter font from CDNs, so you need an internet connection the first time you open it.

## Tech

- HTML, vanilla JavaScript and Tailwind CSS (CDN)
- State lives in `window.tournament` and is persisted to localStorage
- No dependencies to install

## Notes

King of Tokyo and King of New York are products of IELLO. This is an unofficial fan-made tool and is not affiliated with or endorsed by IELLO.
