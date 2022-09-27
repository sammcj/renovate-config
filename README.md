# @sammcj/renovate-config

My [shareable config](https://renovatebot.com/docs/config-presets/) for [Renovate](https://renovatebot.com)

## Setup

1. Enable Renovate in your repo
2. Add this repo to `extends` in your `renovate.json`.

```json
{
  "extends": ["github>sammcj/renovate-config"]
}
```

You don't have to do `npm i -D @sammcj/renovate-config` - Renovate fetches it from this GitHub repo automatically.

Note: By default my config auto-merges pin/minor/patch updates if the checks pass and there isn't a CODEOWNERS file preventing it.

## Presets

### `github>sammcj/renovate-config` (`default`)

[Default config](default.json)

#### General

- Automerge (if there's no CODEOWNERS preventing it).
  - Package pinning if tests pass.
  - Patch upgrades if tests pass.
  - Non-major Github Actions updates.
- Ignore `node_modules`, `bower_components`, and various test/tests directories.
- Automagically rebase stale PRs.
- Apply label `renovate` to PRs.
- Limit to maximum 10 concurrent Renovate PRs at any time.
- Wait until branch tests have passed or failed before creating the PR.
- If semantic commits detected, use semantic commit type `fix` for deps and peerDeps, `chore` for all others.
- Use `Australia/Melbourne` timezone.
- Enable the Renovate [Dependency Dashboard](https://docs.renovatebot.com/key-concepts/dashboard/).
- Use conventional commits with fix, deps and chore scopes.
- Enable docker tag updates (preview feature).
- Enable docker-compose updates (preview feature).

Grouping:

- Group [preset monorepo packages](https://renovatebot.com/docs/presets-monorepo/) updates.
- Group [preset aws-cdk packages](https://renovatebot.com/docs/presets-group/#groupaws-cdkmonorepo) updates.
- Group [present aws-sdk-js-v3 packages](https://docs.renovatebot.com/presets-group/#groupaws-sdk-js-v3Monorepo) updates.
- Group Github Actions updates.
- Group [preset jekyll ecosystem packages](https://docs.renovatebot.com/presets-group/#groupjekyllecosystem) updates.
- Group Dockerfile and Docker-Compose updates.
-

#### for npm

- Separate major, minor and patch releases of dependencies into individual branches/PRs.
- Set a status check to warn when npmjs.com packages are less than < [72 hours old and as such are allowed to be unpublished](https://docs.npmjs.com/policies/unpublish).
- Run `npm dedupe` after package-lock.json updates.
- Disable major upgrade of `@types/node` (e.g. v16 to v17).
- Upgrade semver ranges to latest version even if latest version satisfies existing range.
- Group ESLint, ESLint configs, ESLint plugins and Prettier together.
- Automerge minor updates of widely used libraries like `mocha` in devDependencies.
- Replace the deprecated bable-eslint with @babel/eslint-parser if found.

#### for lock file maintenance

- Run following schedule: before 3am every Saturday

## References

- [Renovate Docs](https://renovatebot.com/docs/)
- [Configuration Options \| Renovate Docs](https://renovatebot.com/docs/configuration-options/)
- [Default Presets \| Renovate Docs](https://renovatebot.com/docs/presets-default/)
- [Other shareable configs in GitHub](https://github.com/search?o=desc&q=%22renovate-config%22&s=stars&type=Repositories&utf8=%E2%9C%93)
- [RunKit \+ npm: later](https://npm.runkit.com/later): [later](https://www.npmjs.com/package/later) is a parser that used to parse `schedule` in renovate
- [teppeis/renovate-config](https://github.com/teppeis/renovate-config)

## License

MIT License: Sam McLeod

![npm-image](https://img.shields.io/npm/v/@sammcj/renovate-config.svg)
![npm-url](https://npmjs.org/package/@sammcj/renovate-config)
![npm-downloads-image](https://img.shields.io/npm/@sammcj/renovate-config.svg)
![ci-image](https://github.com/sammcj/renovate-config/workflows/test-and-publish/badge.svg)
![ci-url](https://github.com/sammcj/renovate-config/actions?query=workflow%3Aci)
![node-version](https://img.shields.io/badge/Node.js%20support-v16,v18-brightgreen.svg)
![license](https://img.shields.io/npm/l/@sammcj/renovate-config.svg)
