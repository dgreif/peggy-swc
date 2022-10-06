# peggy-swc

Repro for peggy + swc compression bug

The peggy.js library can easily generate deeply nested conditions. If the nesting gets sufficiently deep, SWC compression seems to slow down exponentially.

In this repo, you will find 3 peggy files to demonstrate how compression slows down

- `npm run small` - 0.149s
- `npm run medium` - 4.677s
- `npm run large` - 18.408s

The slow down seems directly tied to the `unused` compression option. If you run large with `unused: false`, it is almost instant

- `npm run large-unused-off` - 0.163s
