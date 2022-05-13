- uses: actions/checkout@v3
  - uses: actions/setup-go@v3
    with:
      go-version: '^1.13.1' # The Go version to download (if necessary) and use.
  - run: go version

  - uses: actions/checkout@v3
  - uses: actions/setup-go@v3
    with:
      go-version: '>=1.17.0'
  - run: go version
- uses: actions/checkout@v3
  - uses: actions/setup-go@v3
    with:
      go-version: '1.18.0-rc.1' # The Go version to download (if necessary) and use.
  - run: go version
  - 
  - uses: actions/checkout@v3
  - uses: actions/setup-go@v3
    with:
      go-version: '1.16.0-beta.1' # The Go version to download (if necessary) and use.
  - run: go version
- uses: actions/checkout@v3
  - uses: actions/setup-go@v3
    with:
      go-version: '1.16.1' # The Go version to download (if necessary) and use.
  - run: go run hello.go
- uses: actions/checkout@v3
  - uses: actions/setup-go@v3
    with:
      go-version: '1.14'
      check-latest: true
  - run: go run hello.go
  - jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        go: [ '1.14', '1.13' ]
    name: Go ${{ matrix.go }} sample
    steps:
      - uses: actions/checkout@v3
      - name: Setup go
        uses: actions/setup-go@v3
        with:
          go-version: ${{ matrix.go }}
      - run: go run hello.go


