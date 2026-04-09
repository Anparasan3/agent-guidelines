# Allowed Commands

Agents are allowed to run ONLY the following commands:

- bun run dev
- bun run test
- bun test *
- bun run typecheck
- bun run --cwd src typecheck
- bun tsc --noEmit
- cat package.json | python3 -c "import sys, json; print(json.load(sys.stdin).get('scripts', {}))"