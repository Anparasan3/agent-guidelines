# Important Guidelines

1. Keep the code DRY. Functions should be reused.
2. This project uses Prisma. Use Prisma and avoid raw SQL as much as possible.
3. Use type inference as much as possible. Do not construct new types when they can be derived from Prisma.
4. Split components into their own files.
5. Use bun instead of node or npm.
6. Use react-router v7 constructs:
   - typed routes
   - loaderData and actionData from Route.ComponentProps
7. Never use `any`, and avoid using `as`.
8. After completing changes:
   - Run `bun run typecheck`
   - Fix all type issues
9. When adding new features:
   - Add unit tests
   - Run `bun run test`
   - Ensure all tests pass