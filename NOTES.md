## One fix

The PHP 0.00 booking bug came from the backend counting rental days exclusively in `rental_days()`. That made a same-day rental count as 0 days, and short rentals were undercharged by one day. I fixed it by making the calculation inclusive with `+ 1`, which matches the business rule that both the start and end dates count.

## Double-booking example

Original code wrongly allowed: `2026-01-08` to `2026-01-12`

## AI use

I used AI to help me review the code, narrow down the cause of each bug, and suggest small fixes. I still reviewed each change myself by tracing the relevant code paths and checking that the behavior matched the requirements in the README file.
