# Culinary Knowledge Graph & Session Log

A version-controlled repository treating cooking as an experimental discipline. Rather than maintaining static, idealized recipe cards, this log records the planned blueprint alongside real-time pan adjustments, sensory feedback, and technical deltas across iterative sessions..

---

## Directory Pattern

* `/templates/`: JSON schema for session validation and Markdown templates for scaffolding.
* `/sessions/YYYY-MM-DD-<dish-slug>/`: Append-only session logs containing the triad:
  * `meta.json`: Machine-readable metadata (tags, course, rating, corpus role) conforming to `templates/meta.schema.json`.
  * `recipe.md`: Pre-cook blueprint detailing mise en place, cut geometry, and intended execution order.
  * `results.md`: Post-cook retrospective documenting reality vs. intent, pan behavior, balance, and next-iteration deltas.

---

## Corpus Roles

To distinguish utilitarian sustenance from technical study, sessions classify their intent via `corpus_role`:

* `foundation`: Building blocks and basic components (stocks, simple grains, boiled potatoes).
* `technique-study`: Dedicated exploration of specific mechanical principles (dry-searing fungi, steam-braising alliums, blooming whole spices).
* `weeknight-staple`: Low-cognitive-load dishes built for reliable, efficient execution.
* `showcase`: Complex, high-effort compositions focused on harmony and plating.
* `experiment`: Exploratory trials with novel pairings or unfamiliar ingredient behaviors.

---

## Rating Scale

Evaluated from **1.0 to 5.0** in 0.5 steps:

* **5.0**: Mastered composition. Complete harmony, repeatable, zero structural flaws.
* **4.0 – 4.5**: Highly successful with a distinct identity; clear room for technical or textural refinement.
* **3.0 – 3.5**: Functional; evident imbalance in moisture, fat, acid, or heat control.
* **< 3.0**: Mechanical failure or flavor clash; requires structural rethinking.

---

## Logging Workflow

1. **Scaffold:**
   ```bash
   SLUG="2026-09-16-braised-leek-shiitake-figs"
   mkdir -p "sessions/$SLUG"
   cp templates/recipe.template.md "sessions/$SLUG/recipe.md"
   cp templates/results.template.md "sessions/$SLUG/results.md"