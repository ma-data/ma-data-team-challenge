# Data Solutions Architect — Technical Challenge

Welcome, and thanks for taking the time. This is a small but realistic slice of the work you'd
actually do here: take messy source data, turn it into models you can trust, and answer open
questions that a decision-maker actually cares about.

We are **not** looking for a single "correct" answer. We're looking at *how you think* — how you
define a good metric, how you handle imperfect data, and how clearly you can explain your reasoning
to someone non-technical.

## The scenario

You've been handed the raw data for one season of a football (soccer) league. Four questions have
landed on your desk from people around the business:

1. **Which team was the best overall?**
2. **Who was the best player?**
3. **Which team had the best offense?**
4. **Which team had the best defense?**

Simple questions. The interesting part is *defending* your answers.

## What you'll deliver

1. **Ingestion (Python).** Code that loads the raw files into a local DuckDB database.
2. **Modeling (dbt + DuckDB).** A dbt project — staging through to final models — that transforms
   the raw data into what you need to answer the four questions. Tests and documentation count.
3. **Answers (a short write-up).** An `ANSWERS.md` (or PDF) that gives, for each question: your
   answer, the metric you chose and **why**, the assumptions and caveats behind it, any data issues
   you found and how you handled them, and — honestly — what you'd improve with more time.

## How we think about the data

The data comes from real-world-style sources and **has not been cleaned for you.** Treat it exactly
as you would any new source you're being asked to trust. Deciding what's trustworthy is part of the job.

## Ground rules

- **Timebox:** aim for about **half a day (~4 hours).** "With more time I would…" is a perfectly good
  sentence — we'd rather see sound judgment about scope than an exhausted candidate.
- **Stack:** Python, dbt, and DuckDB (a zero-setup, file-based local warehouse — see [SETUP.md](SETUP.md)).
- **Tools & AI:** Use anything you like, **including AI assistants — we use them here every day.** What
  matters is that *you* understand and can defend every decision. Shortlisted candidates will have a
  short call where we walk through the work together, so submit something you can stand behind.

## Using AI well (please read)

We expect strong candidates to use AI as a force multiplier. What interests us is the difference
between someone who **directs** AI expertly and someone who pastes its output unquestioned. In your
write-up, tell us briefly **how you used AI** — what you delegated, what you rewrote, and where its
first answer was wrong or misleading. That reflection tells us a lot.

## Submitting

> _[To be finalized by the hiring team]_ Use this repository as a **template**, build your solution in
> your own copy, and reply to our email with a link to your repo (plus your `ANSWERS.md`). If your
> repo is private, share access with the contact in our email.

## What we value

Ownership, sound judgment under ambiguity, clean and tested models, and the ability to explain
complex things simply. Have fun with it — the questions are genuinely open, and we love a
well-argued answer.
