# openermatch-data

Open data behind [OpenerMatch](https://openermatch.com/), an independent guide to garage door opener remotes, keypads, sensors, and batteries. Updated 2026-10-23.

| File | What it holds | Rows |
| --- | --- | --- |
| [models.csv](models.csv) | Remotes, keypads, wall controls, smart hubs and batteries, one row per model: buttons, protocol, radio frequency, learn button colors it works with, the year of the oldest opener it fits, status, replacement, and battery | 96 |
| [learn-button-colors.csv](learn-button-colors.csv) | The learn button colors on garage door openers, with the protocol, radio frequency, and years of openers that carry each | 8 |
| [sources.csv](sources.csv) | The manufacturer pages these facts come from, with the date each was read | 55 |

Brands in `models.csv`: Chamberlain, Clicker, Craftsman, Genie, LiftMaster, Linear, myQ, Overhead Door.

## Where the facts come from

Every row comes from a help page, product page, or compatibility list that a manufacturer publishes, read between 2026-10-14 and 2026-10-14. The `source_ids` columns point to `sources.csv`, which names each page and the date it was read. The files hold facts only, in our own words and layout: no manufacturer text, images, or logos are copied. Where a value could not be found in a published source, the cell is empty. It is never estimated.

## How the columns work

- `type`: remote, keypad, wall control, smart hub, or battery. `format`: keychain, visor, or learning remote, when the source says so. `universal`: “yes” for a model sold as a universal remote or keypad.
- `protocol` and `frequency_mhz`: what the manufacturer publishes for the model, or what follows from the learn button colors it is listed for. `derived_columns` names the columns that were worked out that way. See `learn-button-colors.csv` for the protocol and frequency of each color.
- `learn_button_colors`: the `color_id` of each learn button color of the openers the model is listed for. `yellow-mc` is the round yellow button with a Step Saver label on the MC models, sold from 2022.
- `openers_made_after`: the year from which the model is listed for openers (for example 1993 means openers made after 1993).
- `status`: “current” or “discontinued”, as the sources show it. `replaced_by`: the models the sources name as replacements. A cell is empty when no source says.
- `battery`: the battery the model takes, as the manufacturer lists it.
- `opener_years` (in `learn-button-colors.csv`): the years of openers that carry that color. “present” means still sold.

How OpenerMatch builds its guides, and what it covers: [Method](https://openermatch.com/method/#open-data).

## License and credit

To the extent Julien Fourel holds rights in the compilation and the derived columns, they are licensed under [CC BY 4.0](LICENSE): free to quote, chart, and republish, including commercially. Please credit “OpenerMatch” with a link to https://openermatch.com/. Facts such as model numbers and learn button colors belong to no one; we claim no rights in them. Brand and model names belong to their owners and are used only to say which products work together. OpenerMatch is independent and is not affiliated with any brand named in these files. It earns commissions on some links to retailers; they play no part in these files.

Corrections: https://openermatch.com/method/#corrections
