# metaculus-bot

Made by SKILLMERC.

An automated forecasting bot for the Metaculus FutureEval bot tournaments. It reads open questions from the Metaculus API, researches each one, asks a language model for a probability or a distribution, and posts the forecast with a private comment that explains its reasoning. Nobody edits, reviews or re-runs its forecasts by hand.

This repository is a fork of the official Metaculus template bot (https://github.com/Metaculus/metac-bot-template). The template's own instructions are in `TEMPLATE-README.md`.

## Rules this bot follows

From the Metaculus FutureEval rules (https://www.metaculus.com/notebooks/38928/ai-benchmark-resources/#competition-rules):

- No human in the loop. The bot forecasts and comments through the API on its own. No one copies, edits or adjusts its forecasts, and its forecasts are never influenced by a person's own view on a question.
- No previewing and no re-runs. The bot is never tested on open or upcoming tournament questions, and a forecast is never re-run because someone dislikes it. Testing happens only in the Metaculus Bot Testing Area or on closed questions.
- One forecast per question in the bot-only tournaments.
- A comment with every forecast, posted as a private comment as the rules ask.
- One prize-eligible bot. Any extra bot is a marked secondary bot.
- The code is public so anyone, including Metaculus, can see how the bot works.

## How it runs

GitHub Actions in this repository:

- `Test Bot` (`test_bot.yaml`): manual run against the unscored Bot Testing Area.
- `Forecast on new AI tournament questions` (`run_bot_on_tournament.yaml`): every 20 minutes, but it does nothing unless the repository variable `TOURNAMENT_ENABLED` is `true`.
- `Forecast on Metaculus Cup` (`run_bot_on_metaculus_cup.yaml`): every 2 days, off unless `METACULUS_CUP_ENABLED` is `true`.

Secrets it needs (Settings, Secrets and variables, Actions): `METACULUS_TOKEN` and one model key such as `OPENROUTER_API_KEY`.

## Status

Set-up stage. The bot is not entered in any tournament yet.
