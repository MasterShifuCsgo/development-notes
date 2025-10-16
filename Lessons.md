1. failed in architecting the control flow of my validation logic
I treated multiple independent constraints (green, yellow, black) as if they could be validated simultaneously inside one loop,
when in reality their evaluation must be ordered and isolated, because they interact and override each other.
- Loss of control — each letter’s condition could override the previous decision (addword flipping unpredictably).
- Logical entanglement — green/yellow/black rules operated on the same iteration level, even though they depend on global letter context.
- Unclear separation of responsibility — your loop mixed verification (checking) and decision-making (adding/removing) in one place.
- Resulting effect: the algorithm’s correctness depended on side-effects instead of structured reasoning.
You failed not in syntax or concept, but in designing the sequence of logic — you attempted parallel validation where ordered reasoning was required.
