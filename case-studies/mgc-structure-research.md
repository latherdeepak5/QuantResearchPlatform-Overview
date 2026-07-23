# MGC Structure Research Case Study

This public-safe case study summarizes the transfer of the private
market-structure research framework to Micro Gold futures. It excludes source
code, raw datasets, exact executable rules, and account information.

## Objective

Determine whether a structure-driven model can participate in both directional
changes and trend continuation while using smaller paper size and explicit
partial-plus-runner management.

## Research Path

The private study compared:

- Market-structure direction changes.
- Independent trend confirmation.
- Directional moving-average alignment.
- Retracement entries.
- Same-direction continuation behavior.
- Partial profit-taking and reduced-size runners.
- Immediate versus confirmation-aware reversal exits.

## Retained Direction

The current research branch requires structure, trend, and moving-average
direction to agree before a retracement entry becomes eligible. It also permits
a continuation setup when structure breaks again in the direction of the active
trend.

The position is intentionally smaller than the original MES research size. A
majority is assigned to the first partial, with a reduced remainder managed as
runners.

## Exit Finding

An isolated opposite-structure marker can appear during a healthy trend. Exiting
immediately may therefore remove a good runner too early. The retained research
branch arms the reversal first and waits for independent trend confirmation. A
new same-direction continuation event can invalidate that pending exit.

This is still under paper validation and may change with a larger sample.

## Rejected Transfers

- A more aggressive retracement setting was tested but did not replace the
  earlier baseline.
- A larger trend-factor variant was tested and restored.
- Applying the same moving-average filter to MNQ did not justify changing that
  separate strategy.

These decisions reinforce the platform's rule that each instrument should earn
its own settings rather than inherit another market's parameters automatically.

## Paper Controls

The optional MGC paper path includes:

- A hard maximum contract count.
- Separate broker client and strategy ownership.
- Position-aware exits.
- Telegram lifecycle notifications.
- Private dashboard reconciliation.
- Broker-held emergency protection derived from the accepted structure risk.

Live-account routing remains blocked.

## Next Questions

- Does continuation behavior remain stable across different gold regimes?
- How often does confirmation-aware exit management preserve meaningful runner
  profit?
- Do broker-paper fills match the private event model?
- Does performance remain useful after realistic slippage and a larger
  out-of-sample period?

## Risk Notice

All findings are research observations from historical simulation and paper
workflows. They do not guarantee future performance and are not trading advice.
