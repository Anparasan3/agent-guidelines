# TypeScript Best Practices

## Types & Safety

- Never use `any`.
  This was a necessary evil in early TypeScript, but it causes serious problems in modern codebases.
  It propagates and weakens type safety across the application.
  If the type is unknown, use `unknown`.

- Use `as` sparingly.
  In TypeScript, `as` does NOT perform real type casting — it only tells the compiler to trust you.
  This can introduce runtime bugs.

  Example:
  typeof ('0' as number) === 'string'  // still true ❌

- Prefer `interface` over `type`.

  ❌ Avoid:
  type Thing = { id: number }

  ✅ Prefer:
  interface Thing {
    id: number
  }

  Use `type` only when needed (e.g., unions, advanced types).

- Prefer type inference.

  ✅ Good:
  arrayOfStrings.map(x => x.substring(0, 1))

  ❌ Bad:
  arrayOfStrings.map((x: string) => x.substring(0, 1))

---

## Equality

- Always use strict equality:
  === and !==

- Never use loose equality:
  1 == '1' // true ❌

---

## Variables

- Prefer `const` over `let`
- Use `let` only when reassignment is required
- Never use `var`

---

## Code Structure

- One function or type per file
- Keep files small and focused
- Split reusable logic into separate functions/files
- Prefer pure functions:
  - Same input → same output
  - No side effects

---

## Loops

- Do NOT use Array.forEach
- Use:
  for (const item of items) {
    // logic
  }

---

## Dates

- Avoid native Date
- Use helper libraries:
  - date-fns
  - dayjs

Reference:
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Temporal

---

## Math

- Use Decimal.js for calculations
- Avoid floating point issues:
  0.1 + 0.2 !== 0.3

Reference:
https://github.com/tc39/proposal-decimal

---

## Error Handling

- Avoid try/catch unless required for control flow
- Always log full error (not just error.message)

- Prefer:
  - logging + returning
  - instead of throwing

### When throwing errors:

- Use static messages
- Include cause

throw new Error('Something went wrong', {
  cause: { customerId: 1 }
})

---

## Formatting

- Always format your code
- Use Prettier
- Enable format on save

---

## General Reminder

TypeScript is just JavaScript — be aware of pitfalls:

https://github.com/denysdovhan/wtfjs
