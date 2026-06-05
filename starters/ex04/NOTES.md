# ex04 — SDK Bridge · NOTES

## Full flow explanation

> Describe in your own words the complete flow:
> C++ → system() → bridge.mjs → SDK → Claude → JSON → C++ displays result

### Step 1: C++ reads JSON
> How does your program parse sample_report.json? What library did you use?

### Step 2: bridge.mjs
> How does the script work? How does it send the file to Claude via SDK?

### Step 3: C++ launches bridge.mjs
> What does system() do exactly? What are its risks?

### Step 4: Validation with test_files
> What did Claude find in each file? Were the results accurate?

## Why doesn't C++ call the SDK directly?

> [Your answer here]

## Why limit to allowedTools: ["Read"]?

> [Your answer here]

## Error handling: what cases did you cover?

> [List the error cases and how you handled each one]

## Bonus: system() vs fork()/exec()

> If you implemented the bonus, explain the difference and why fork()/exec() is more robust.
