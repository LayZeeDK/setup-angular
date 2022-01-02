# setup-angular [WIP]

Set up your GitHub Actions workflow with a specific version of Angular.

# Usage

## Basic

```yml
name: Test
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with:
          cache: yarn
          node-version: 12
      - uses: ngworker/setup-angular@v1
        with:
          angular-version: 12
      - run: yarn install
      - run: yarn test
```

## Matrix usage

```yaml
name: Test
jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        angular:
          - 9.0
          - 9.1
          - 10.0
          - 10.1
          - 10.2
          - 11.0
          - 11.1
          - 11.2
          - 12.0
          - 12.1
          - 12.2
          - 13.0
          - 13.1
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with:
          cache: yarn
          node-version: 12
      - name: Set up Angular ${{ matrix.angular }}
        uses: ngworker/setup-angular@v1
        with:
          angular-version: ${{ matrix.angular }}
      - run: yarn install
      - run: yarn test
```

## Node.js compatibility

See [Angular compatibility matrix](https://gist.github.com/LayZeeDK/c822cc812f75bb07b7c55d07ba2719b3)
for Angular's Node.js compatibility.
