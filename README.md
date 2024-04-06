# tsconfig-domdomegg

Personal preset for general TypeScript settings. To be used in conjunction with a TSConfig for the specific platform (e.g. @tsconfig/node-lts)

See https://github.com/tsconfig/bases/issues/262 for a brief motivation behind creating this separate preset. In short: I want great type-checking, but without linting rules. This is because TypeScript's linting rules:
- often get in the way of testing things out, e.g. it's useful to be comment stuff out temporarily to see behavior without the compiler complaining about unused code or variables
- tend to just duplicate rules better handled by [ESLint](https://eslint.org/) anyway

## Usage

In your `tsconfig.json`:

```jsonc
{
    "extends": [
        // Set the TSConfig for the specific platform, see https://github.com/tsconfig/bases
        "@tsconfig/node-lts/tsconfig.json",
        "tsconfig-domdomegg/tsconfig.json"
    ],
    // ...
}
```

## Contributing

Pull requests are welcomed on GitHub! To get started:

1. Install Git and Node.js
2. Clone the repository
3. Install dependencies with `npm install`
4. Run `npm run test` to run tests

## Releases

Versions follow the [semantic versioning spec](https://semver.org/).

To release:

1. Use `npm version <major | minor | patch>` to bump the version
2. Run `git push --follow-tags` to push with tags
3. Wait for GitHub Actions to publish to the NPM registry.
