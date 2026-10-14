# Buden-Helper data

The data Buden-Helper, a tracker for Magic: The Gathering Arena, fetches once a day. Nothing here is meant to
be edited by hand: the files are written by a scheduled build and by the maintainer's publish script.

| Path | What | Written by |
|---|---|---|
| `metagame/<format>.json` | Metagame snapshots for Standard, Pioneer, Historic and Timeless: the decks that are played, their share and their lists. The app guesses the opponent's deck from them. | A daily build |
| `metagame/index.json` | The snapshots with their checksums | The same build |
| `models/index.json` | The draft models, roles files and replay drafts per set, with their checksums and addresses | `python -m draftbot.publish` |
| Release [`models`](https://github.com/RaizQQW/buden-helper-data/releases/tag/models) | The files `models/index.json` points at, named by checksum | The same script |

The app reads the two indexes, compares each checksum with the one it took last, and downloads what changed.
A path under `files` in an index is the file's place in the app's config folder.

## Sources and licences

- **Standard and Pioneer snapshots** are built from the tournament decklists in
  [fbettega/MTG_decklistcache](https://github.com/fbettega/MTG_decklistcache), which is licensed GPL-3.0. They
  are derived from that data and are offered here under the
  [GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html) as well. Archetype names come from the rules in
  [Badaro/MTGOFormatData](https://github.com/Badaro/MTGOFormatData).
- **Historic and Timeless snapshots** are the decks, reference lists and tiers of the
  [Meta Confluence tier lists](https://metaconfluence.com/tier-lists/). Meta Confluence has kindly agreed to
  their lists being shared with Buden-Helper; they remain Meta Confluence's work. Please ask them before
  using these two files elsewhere.
- **Draft models, roles files and replay drafts** are trained on, and taken from, the
  [17lands public datasets](https://www.17lands.com/public_datasets), licensed under
  [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). They are offered here under CC BY 4.0, with
  credit to 17lands.

Buden-Helper is unofficial Fan Content permitted under the Wizards of the Coast Fan Content Policy. Not
approved or endorsed by Wizards. Portions of the materials used are property of Wizards of the Coast.
© Wizards of the Coast LLC.
