# Linguistic Dataset Explorer

An interactive browser-based tool for exploring linguistic benchmark datasets by language and phenomenon coverage. No server required — runs entirely in the browser.

## Live Demo

➜ Deploy via GitHub Pages (see below) or open `index.html` directly.

## Features

- **Upload any CSV** in the standard format — drag & drop or click to browse
- **Filter by language** — select one or many languages to find matching datasets
- **Filter by phenomenon** — narrow down by grammatical phenomena covered
- **Year range filter** — focus on recent or historical datasets
- **Two views**:
  - **Cards** — detailed view with all metadata per dataset
  - **Matrix** — phenomenon × dataset grid for quick comparison
- **Active filter bar** — see and remove filters at a glance
- Works offline — no dependencies are fetched at runtime (PapaParse loaded from CDN)

## CSV Format

The tool expects a CSV with the following columns:

| Column | Description |
|--------|-------------|
| `Citation` | Author(s) and year string |
| `Year` | Publication year (integer) |
| `Method` | Python-list-style string, e.g. `['Expert-written']` |
| `Languages` | Python-list-style string, e.g. `['English', 'French']` |
| `EvalType` | Python-list-style string, e.g. `['Minimal pairs']` |
| `NumExamples` | Integer or empty |
| `IsMultilingual` | `True` or `False` |

Followed by **phenomenon columns** — one column per phenomenon. Mark presence with the string `check` (case-insensitive). Empty or any other value = absent.

Default phenomenon columns:
`Agreement`, `Case`, `DOM`, `Derivation`, `Inflection`, `TAME`, `Morphology`, `Word formation`, `Determiner`, `Pronouns`, `Classifiers`, `Ergativity`, `Word order`, `Argument Structure`, `oblique`, `Passive`, `Copular construction`, `Negation`, `Nominalization`, `Comparison`, `Interrogatives`, `Ellipsis`, `Coordination`, `Relative Clause`, `Complex clauses`, `Adverbial Clauses`, `control&raising`, `Movement`, `Island Effects`, `Filler-Gap`, `Topicalization`, `ba`, `coverb`, `definiteness-effect`, `Quantifiers`, `NPI`, `Binding`

## Deploy to GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch → main → / (root)**
4. Your tool will be live at `https://yourusername.github.io/linguistic-dataset-explorer/`

That's it. Anyone with the link can upload their own CSV and use the explorer.

## Local Use

Just open `index.html` in any modern browser. No build step, no dependencies to install.

## Adding Custom Phenomena

If your CSV has different phenomenon column names, edit the `PHENOM_COLS` array at the top of the `<script>` section in `index.html`:

```js
const PHENOM_COLS = [
  'Agreement', 'Case', 'DOM', /* ... your columns ... */
];
```

## License

MIT
