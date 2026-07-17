# Data Solutions Architect — Technical Challenge

Welcome, and thanks for taking the time. This is a small but realistic slice of the work you'd
actually do here: take raw source data, model it well, and answer open questions that a
decision-maker actually cares about.

We are **not** looking for a single "correct" answer. We're looking at *how you think* — how you
define a good metric, how you reason from raw data to a defensible answer, and how clearly you can
explain that to someone non-technical.

## The scenario

You've been handed the **raw data** for three and a half seasons of a football (soccer) league —
three complete seasons and a fourth still in progress. Four questions have landed on your desk from
people around the business:

1. **Which team was the best overall?**
2. **Who was the best player?**
3. **Which team had the best offense?**
4. **Which team had the best defense?**

Simple questions. The interesting part is *defending* your answers.

## Ground rules

- **Time:** we estimate this takes about **half a day (~4 hours)** — an estimate, not a limit.
- **Stack:** Python, dbt, and DuckDB (a zero-setup, file-based local warehouse — see [SETUP.md](SETUP.md)).
- **Tools & AI:** use anything you like, **including AI assistants — we use them here every day.** What
  matters is that *you* understand and can defend every decision. Shortlisted candidates will have a
  short call where we walk through the work together, so submit something you can stand behind.

## Using AI well

We expect strong candidates to use AI as a force multiplier. What interests us is the difference
between someone who **directs** AI expertly and someone who pastes its output unquestioned. In your
write-up, tell us **how you used AI** — what you delegated, what you rewrote, and where its first
answer was wrong or misleading. That reflection tells us a lot.

## What you'll deliver

Make your own private copy of this repository and share it with us: click **"Use this template" →
Create a new repository** (this is how you get a private copy — a *fork* of a public repo can't be
made private), set it to **Private**, and add **`ma-marcio`** as a collaborator with read access.
**Everything must live in that one repo** — all of the deliverables below *and* all of your work,
with your commit history intact.

Your repository should contain:

1. **Ingestion (Python)** — code that loads the raw files into a local DuckDB database.
2. **Modeling (dbt + DuckDB)** — a dbt project, staging through to final models, that turns the raw
   data into what you need to answer the four questions. Tests and documentation count.
3. **A write-up** — a file, in whatever format you prefer, that gives your answer to each question and
   **explains and defends it**: the metric you chose and *why*, your assumptions and caveats, what you
   found in the data, and what you'd do with more time. The more clearly it shows how your thinking
   was structured, the better.

When you're finished, submit your repository link via this form: **[submission form — link added shortly]**

## What we value

Ownership, sound judgment under ambiguity, clean and well-tested models, and the ability to explain
complex things simply. We also value **clear, well-commented code — the best documentation for any
code is good commentary in the code itself.** Have fun with it: the questions are genuinely open, and
we love a well-argued answer.
