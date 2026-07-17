# models/

Build your dbt models here. There's no prescribed structure — a common, sensible approach is:

- **staging/** — one model per raw source, lightly cleaned and typed (define your `sources` in a
  `.yml` here too, and add `tests`).
- **marts/** — the models that actually answer the four questions.

But the design is yours to make and defend.
