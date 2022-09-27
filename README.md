# @sammcj/renovate-config

My [shareable config](https://renovatebot.com/docs/config-presets/) for [Renovate](https://renovatebot.com)

## Setup

Enable Renovate in your repo and just `extends` in `renovate.json`.

```js
{
  "extends": ["github>sammcj/renovate-config"]
}
```

Note: You don't have to do `npm i -D @sammcj/renovate-config`.
Renovate fetches it from this GitHub repo automatically.

## Presets

### `github>sammcj/renovate-config` (`default`)

#### General

- Ignore `node_modules`, `bower_components`, and various test/tests directories
- Apply label `renovatebot` to PRs
- Limit to maximum 10 concurrent Renovate PRs at any time
- Wait until branch tests have passed or failed before creating the PR
- If semantic commits detected, use semantic commit type `fix` for deps and peerDeps, `chore` for all others
- Use `Australia/Melbourne` timezone
- Group [preset monorepo packages](https://renovatebot.com/docs/presets-monorepo/) together

#### for npm

- Automerge patch upgrades if they pass tests
- Make no updates to branches when not scheduled
- Separate major, minor and patch releases of dependencies into individual branches/PRs
- Set a status check to warn when upgrades < 24 hours old might get unpublished
- Run `npm dedupe` after package-lock.json updates
- Disable major upgrade of `@types/node`
- Upgrade semver ranges to latest version even if latest version satisfies existing range.
- Group ESLint, ESLint configs, ESLint plugins and Prettier together
- Automerge minor updates of widely used libraries like `mocha` in devDeps

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
![npm-downloads-image](https://img.shields.io/npm/dm/@sammcj/renovate-config.svg)
![ci-image](https://github.com/sammcj/renovate-config/workflows/ci/badge.svg)
![ci-url](https://github.com/sammcj/renovate-config/actions?query=workflow%3Aci)
![deps-image](https://img.shields.io/david/sammcj/renovate-config.svg)
![deps-url](https://david-dm.org/sammcj/renovate-config)
![node-version](https://img.shields.io/badge/Node.js%20support-v6,v8,v9-brightgreen.svg)
![coverage-image](https://img.shields.io/coveralls/sammcj/renovate-config/main.svg)
![coverage-url](https://coveralls.io/github/sammcj/renovate-config?branch=main)
![license](https://img.shields.io/npm/l/@sammcj/renovate-config.svg)
