# Scientific Calculator

A fully client-side scientific calculator inspired by the Casio fx-100MS, built with plain HTML/CSS/JS — no frameworks, no build step, no dependencies.

**Live demo:** https://kshitija2105.github.io/scientific_calculator/

## Features

- **Live-updating display** — the result updates as you type, not just when you press `=`
- **SHIFT / HYP modifier keys** — one-shot modifiers just like a real scientific calculator: press `SHIFT`, then the next key does its secondary (yellow-labelled) function, and it resets automatically
  - `SHIFT` + `sin`/`cos`/`tan` → `sin⁻¹`/`cos⁻¹`/`tan⁻¹`
  - `HYP` + `sin`/`cos`/`tan` → `sinh`/`cosh`/`tanh` (add `SHIFT` too for the inverse hyperbolic versions)
  - `SHIFT` + `ln`/`log` → `eˣ`/`10ˣ`
  - `SHIFT` + `√`/`x²`/`^` → `³√`/`x³`/`ˣ√y`
  - `SHIFT` + `x⁻¹`/`RCL`/`M+` → `x!`/`STO`/`M−`
- **DEG / RAD / GRAD** angle modes, cycled with one button
- **Memory**: `RCL`, `STO`, `M+`, `M−`
- **Combinatorics**: `nPr`, `nCr`
- **Fractions**: toggle any result between decimal and simplified fraction (`a b/c`)
- **Engineering notation** toggle (`ENG`)
- **History panel** — click any past calculation to recall it
- **Full keyboard support** (digits, operators, Enter, Backspace, Escape, Shift)
- **Responsive** down to small mobile widths

## How it works

The math is evaluated with a hand-written recursive-descent parser (not `eval()`), following standard operator precedence:

```
expr    := term (('+'|'-') term)*
term    := comb (('*'|'/') comb)*
comb    := unary (('nPr'|'nCr') unary)*
unary   := '-' unary | power
power   := postfix (('^'|'nroot') unary)?      // right-associative
postfix := primary ('!'|'²'|'³'|'⁻¹'|'%')*
primary := number | const | fn '(' expr ')' | '(' expr ')'
```

This avoids the security and correctness issues of `eval()`-based calculators and correctly handles nested parentheses, right-associative powers, and postfix/infix custom operators (factorial, roots, permutations, etc.) composing with each other.

## Running locally

No build step required — just open the file:

```bash
git clone https://github.com/Kshitija2105/scientific_calculator.git
cd scientific_calculator
open index.html   # or just double-click it
```

## Scope notes

Deliberately left out: base-N conversion (HEX/BIN/OCT), complex numbers, statistics/regression, and the equation solver/calculus modes found on the physical calculator. Each of those needs its own input mode and display grammar, so bolting them onto this single-mode calculator would have meant building three calculators in one — not a good tradeoff for the added complexity.

## Tech

Plain HTML, CSS, and JavaScript. No frameworks, no dependencies, no build tooling. Deployed via GitHub Pages.
# Scientific Calculator

A fully client-side scientific calculator inspired by the Casio fx-100MS, built with plain HTML/CSS/JS — no frameworks, no build step, no dependencies.

**Live demo:** https://kshitija2105.github.io/scientific_calculator/

![Scientific Calculator](preview.png)

## Features

- **Live-updating display** — the result updates as you type, not just when you press `=`
- **SHIFT / HYP modifier keys** — one-shot modifiers just like a real scientific calculator: press `SHIFT`, then the next key does its secondary (yellow-labelled) function, and it resets automatically
  - `SHIFT` + `sin`/`cos`/`tan` → `sin⁻¹`/`cos⁻¹`/`tan⁻¹`
  - `HYP` + `sin`/`cos`/`tan` → `sinh`/`cosh`/`tanh` (add `SHIFT` too for the inverse hyperbolic versions)
  - `SHIFT` + `ln`/`log` → `eˣ`/`10ˣ`
  - `SHIFT` + `√`/`x²`/`^` → `³√`/`x³`/`ˣ√y`
  - `SHIFT` + `x⁻¹`/`RCL`/`M+` → `x!`/`STO`/`M−`
- **DEG / RAD / GRAD** angle modes, cycled with one button
- **Memory**: `RCL`, `STO`, `M+`, `M−`
- **Combinatorics**: `nPr`, `nCr`
- **Fractions**: toggle any result between decimal and simplified fraction (`a b/c`)
- **Engineering notation** toggle (`ENG`)
- **History panel** — click any past calculation to recall it
- **Full keyboard support** (digits, operators, Enter, Backspace, Escape, Shift)
- **Responsive** down to small mobile widths

## How it works

The math is evaluated with a hand-written recursive-descent parser (not `eval()`), following standard operator precedence:

```
expr    := term (('+'|'-') term)*
term    := comb (('*'|'/') comb)*
comb    := unary (('nPr'|'nCr') unary)*
unary   := '-' unary | power
power   := postfix (('^'|'nroot') unary)?      // right-associative
postfix := primary ('!'|'²'|'³'|'⁻¹'|'%')*
primary := number | const | fn '(' expr ')' | '(' expr ')'
```

This avoids the security and correctness issues of `eval()`-based calculators and correctly handles nested parentheses, right-associative powers, and postfix/infix custom operators (factorial, roots, permutations, etc.) composing with each other.

## Running locally

No build step required — just open the file:

```bash
git clone https://github.com/Kshitija2105/scientific_calculator.git
cd scientific_calculator
open index.html   # or just double-click it
```

## Scope notes

Deliberately left out: base-N conversion (HEX/BIN/OCT), complex numbers, statistics/regression, and the equation solver/calculus modes found on the physical calculator. Each of those needs its own input mode and display grammar, so bolting them onto this single-mode calculator would have meant building three calculators in one — not a good tradeoff for the added complexity.

## Tech

Plain HTML, CSS, and JavaScript. No frameworks, no dependencies, no build tooling. Deployed via GitHub Pages.
