# Temporary Containers @berrnd Fork

-----
-----
> This is a fork of [Temporary Containers](https://github.com/stoically/temporary-containers) (based on the v1.9.2 release) which adds compatibility with [my fork](https://github.com/berrnd/containerise) of [Containerise](https://github.com/kintesh/containerise).
>
> The (signed) .xpi file for manual installation can be found in the [release assets](https://github.com/berrnd/temporary-containers/releases/latest).
>
> _Dev note: Node v16 is needed for building._

-----
-----

Original README:

## Development

### Requirements

- Clone the repository
- `npm install`
- `npm run dev`

### Run in Firefox

- `npx web-ext run -s dist`
  - starts the default system Firefox with a temporary profile, loads the Add-on and watches for changes
  - append `-p profilename` to start Firefox with a specific profile

or

- Open `about:debugging` and `Load Temporary Add-on` which is located in the `dist` directory

Check `about:debugging` and click `Inspect` to the right of Temporary Containers to see the console.

### Run the tests

- Once: `npm test`
  - Shows a coverage summary and generates a detailed report in the `coverage` directory
- Watcher: `npm run watch:test`

### Release

#### AMO and GitHub

- Bump manifest version
- Commit, tag and push
- Upload zip web-ext-artifact to AMO
- Download published AMO xpi
- Create and publish GitHub release with AMO xpi

#### Pre-Release on GitHub

- Bump manifest version
- Commit and push
- git tag v1.0beta1
- git push origin v1.0beta1
- git log \$(git tag --sort=-version:refname | sed -n 2p)..HEAD --pretty=format:%s
- Add release notes and publish

## Libraries

[Vue.js](https://vuejs.org) and [SemanticUI](https://semantic-ui.com/) are used for the preferences & popup UI.

## License

MIT
