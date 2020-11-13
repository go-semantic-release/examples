# Custom Plugins

This example shows how to create a custom semantic-release plugin without publishing it to the plugin index.

## Setup

Run `./build.sh`, this will build the hooks plugin and place it in the semantic-release plugin directory.

## Run semantic-release

```bash
curl -SL https://get-release.xyz/semantic-release/$(go env GOOS)/$(go env GOARCH) -o ./semantic-release
chmod +x ./semantic-release
# enable the logger plugin
./semantic-release --hooks logger
```

### Example Output

```
[go-semantic-release]: version: 2.10.0
[go-semantic-release]: ci-condition plugin: GitHub Actions@1.2.0
[go-semantic-release]: provider plugin: git@1.0.1
[go-semantic-release]: getting default branch...
[go-semantic-release]: found default branch: master
[go-semantic-release]: found current branch: feature1
[go-semantic-release]: found current sha: 8d9d13d
[go-semantic-release]: hooks plugins: logger@dev
[go-semantic-release]: running CI condition...
[hooks-logger]: reason: CONDITION
[hooks-logger]: message: This test run was triggered on the branch feature1, while semantic-release is configured to only publish from master.
[go-semantic-release]: This test run was triggered on the branch feature1, while semantic-release is configured to only publish from master.
```
