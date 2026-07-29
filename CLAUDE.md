---

editor_options: 
  markdown: 
    wrap: 72
---

# kidonomics_labs

R/Quarto lab materials for a 100-level "Economics of Children" quantitative skills course (Lewis & Clark). This repo mirrors the skill progression of an existing course, **Numbers in the Wild** (`numbers_in_the_wild/`), but replaces its generic example data (penguins, weather stations) with public data relevant to children's economic well-being: the American Community Survey (ACS), Current Population Survey (CPS), and American Time Use Survey (ATUS).

## Source material — `numbers_in_the_wild/` (read-only reference)

Written by Jeremy McWilliams. **Do not edit these files** — they're the template whose skills/structure we're reproducing, not files to update.

Each numbered sub-lesson (e.g. `1.1`, `1.2`) ships as a pair: `code-a-long-X.Y.qmd` (blank, for students) and `code-a-long-X.Y-key.qmd` (same file, code filled in). Some sub-lessons also have matching `homework-X.Y` and `practice-problems-X.Y` pairs.

Module 1 skill progression (what we're rebuilding for kidonomics module 1): - **1.1** — RStudio orientation: panes, running code chunks, arithmetic, `<-` assignment - **1.2** — variables, functions, vectors, `mean()`/`sd()` on a data set - **1.3** — subsetting, relational/logical operators, the pipe (`%>%`), `group_by()`/`summarize()` - **1.4** — `select()`, `filter()`, `mutate()`, `summarize()` on an external CSV

Style conventions to preserve: a `### Learning Objectives` (or `Learning Outcomes`) section near the top; short explanatory prose between chunks; inline **"Your turn"** prompts asking students to write code themselves; blank versions leave the `{r}` chunk empty (sometimes with a one-line `# comment` hint) while key versions contain the working code.

## kidonomics lesson conventions (new files)

- **Pipe style: `%>%`** (magrittr), matching `numbers_in_the_wild` — not the native `|>` pipe, so students see identical syntax across both tracks.
- **File pair per lesson**: `kid-X.Y.qmd` (blank) + `kid-X.Y-key.qmd` (key), mirroring the `code-a-long` naming pattern.
- **Folder per numbers_in_the_wild module**: e.g. `module_1/` holds all kidonomics lessons that reproduce numbers_in_the_wild module 1's skills.
- Data sources: ACS via `tidycensus`, CPS/ATUS via IPUMS (`ipumsr`) or other public microdata packages — confirm the specific package per lesson before building it, since CPS/ATUS access patterns differ from `tidycensus`.
- Keep the same pedagogical shape as the source lesson (same skills, same order, same "Your turn" checkpoints) — just swap the dataset and framing to something about children's economic outcomes.

## Current plan / status

kidonomics is being built as **7 total lesson modules** (not a strict 1:1 mapping to numbers_in_the_wild's module numbers). Status:

- **Module 1** (in progress): rebuilds numbers_in_the_wild module 1 (`1.1`–`1.4` above) as **two** kidonomics lessons — `kid-1.1` and `kid-1.2` — each condensing roughly two of the source sub-lessons' skills, using ACS/CPS/ATUS data instead of penguins/weather data. Each lesson needs a blank + key pair. Exact split of which skills go in 1.1 vs 1.2 TBD.
- **Modules 2–6**: not yet started; will be built once numbers_in_the_wild's later modules are added to this repo. Also using ACS/CPS/ATUS data.
- **Module 7**: [`measuring-child-poverty.qmd`](measuring-child-poverty.qmd) (repo root) — already drafted, ACS child poverty by nation/state/county/ tract with `tidycensus` + maps. This is more advanced than module 1 (uses `geom_sf`, spatial geometry) and currently uses the native `|>` pipe rather than `%>%`. Set aside for now — revisit pipe-style consistency and a blank/key split when we get to it.

**Open assumption to confirm with the user**: the "7 qmd files" goal is being read as 7 lesson *topics* (14 actual files once each gets a blank + key pair), not 7 files total. Correct this section if that's wrong.
