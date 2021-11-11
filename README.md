# Setup Simba

This ation is used to setup a Simba 1400 environment.

## Setting up this action

If you haven't already done so, create a `.github/workflows` folder in your repository (_this is where your actions will live_).
Now create a `.github/workflows/setup-simba.yml` file with these contents:

```yaml
on:
  push:
    branches:
      - main
jobs:
  test:
    runs-on: windows-latest #windows is recommended for Simba generally.
    name: Test Simba Setup
    steps:
      - uses: actions/checkout@v2.2.0
      - name: Setup Simba
        uses: Torwent/setup-simba@master
```

You can also optionally setup SRL and/or WaspLib like so:

```yaml
on:
  push:
    branches:
      - main
jobs:
  test:
    runs-on: windows-latest #windows is recommended for Simba generally.
    name: Test Simba Setup
    steps:
      - uses: actions/checkout@v2.2.0
      - name: Setup Simba
        uses: Torwent/setup-simba@master
        with:
          setup-srl: true
          setup-wasplib: true
```

After running this action Simba will be available in `./Simba/Simba.exe`.
