# setup-zig

Install the Zig compiler for use in a GitHub Actions or Forgejo Actions workflow, and preserve the
Zig cache across workflow runs.

> [!IMPORTANT]
> **This is `drawmeanelephant`'s fork of [`mlugg/setup-zig`](https://codeberg.org/mlugg/setup-zig).**
>
> Upstream moved from GitHub to chodeberg and has not been updated since `v2.2.1` (January 2026); the
> original author is no longer maintaining it. This fork is based on `v2.2.1` and is maintained here
> so the action keeps working on current runners.
>
> The only functional change is `runs.using` in `action.yml`: `node20` → `node24`, so the action no
> longer trips the GitHub Actions Node 20 deprecation notice. Consuming workflows pin this fork by tag
> or commit SHA.

## Usage

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    name: Build and Test
    steps:
      - uses: actions/checkout@v3
      - uses: drawmeanelephant/setup-zig@v2.2.1-node24
      - run: zig build test
```

This will automatically download Zig and install it to `PATH`.

See the [full documentation](https://github.com/drawmeanelephant/setup-zig/blob/main/README.md) for all
options, including `version`, `mirror`, caching, and matrix strategies.
