# Serpentine Dream Chess v2.1.0

by WhiteRabbitGeometry

Public browser build with hot-swappable human/computer seats.

## Computer policies

- **Random** — uniformly selects among legal actions.
- **Serpentine** — scores legal actions for immediate victory, material pressure, center presence, mobility, and obvious immediate-opponent victory avoidance, then samples among the strongest moves so it remains challenging without acting like a pure maximizer.
- **Dream** — favors legal states visited least often during the current browser session/game. This is exploration, not winning behavior.

Both White and Black seats may be changed during play, giving:

- Human vs Human hot-seat
- Human vs Computer
- Computer vs Human
- Computer vs Computer Dream runs

Computer state/novelty memory is transient. No player games, telemetry, or persistent analysis logs are saved.

## Rock boundary

Legality remains deterministic and is not learned by the computer policy. The browser implementation follows the frozen Serpentine Dream Chess rules:

- Mirror / Serpentine active-role behavior
- opposing representational Queen non-threat/capture rule
- ordinary check legality
- castling, en passant, and promotion
- Convergence / Royal Convergence
- checkmate = draw
- stalemate = both lose
- Dream Mirror pawn rescue

## Versioning

`2.0.0` follows the project convention:

- first number: public generation
- second number: internal revision generation
- third number: public-facing patch/hotfix

## Deployment

Static GitHub Pages / itch-compatible package. `index.html` is at repository root. No build step.


## v2.1.0 hidden cooperative state

A hidden mutual-victory condition is present but intentionally omitted from the in-game Rules panel and from computer policy scoring.
