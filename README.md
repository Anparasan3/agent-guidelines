## Usage

1. Create an `AGENTS.md` file.
2. Add this line:

```md
See rules:
https://github.com/Anparasan3/agent-guidelines/tree/master/agents/rules
```

## GitHub Package

This repository is configured to publish an npm package to GitHub Packages on every push to `main` or `master`.

Package name:

```txt
@anparasan3/agent-guidelines
```

Install from GitHub Packages:

```sh
npm install @anparasan3/agent-guidelines --registry=https://npm.pkg.github.com
```

Or configure `.npmrc` first and then install normally:

```ini
@anparasan3:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}
```

```sh
npm install @anparasan3/agent-guidelines
```

Notes:

- The workflow publishes a unique prerelease version for each push using the GitHub Actions run number.
- The workflow uses `GITHUB_TOKEN`, so the repository must allow GitHub Actions to create and publish packages.
- The published package includes `README.md` and the `agents/` directory.
