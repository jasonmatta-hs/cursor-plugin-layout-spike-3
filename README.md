# cursor-plugin-layout-spike-3

This is a throwaway Cursor marketplace for a test. It is not a Hootsuite plugin.

## Purpose

This marketplace is an identical copy of layout-spike-2 at phase 3 (commit 835eeb4). The only change is the marketplace name, which is now `layout-spike-3`.

It tests whether a brand-new marketplace URL imports into Cursor. layout-spike-2 was removed from Cursor and would not re-import by URL, even though its repo is valid.

## How to read the result

- If this marketplace imports and lists all three plugins (flat-probe, nested-probe, platform-flat-probe), then re-adding a removed marketplace is the problem.
- If this marketplace also fails to import, then Cursor's marketplace import is having trouble.

## Steps

1. In Cursor, add https://github.com/jasonmatta-hs/cursor-plugin-layout-spike-3 as a marketplace.
2. Confirm that all three plugins are listed: flat-probe, nested-probe, and platform-flat-probe.
3. Install platform-flat-probe.
4. In a new chat, ask "Is platform-flat-probe installed?" The expected answer is `SPIKE2_PLATFORM_FLAT_V1`.

Optional checks, each in a new chat after installing the plugin:

- Ask "Is flat-probe installed?" The expected answer is `SPIKE2_FLAT_V3_MOVED install platform-flat-probe`.
- Ask "Is nested-probe installed?" The expected answer is `SPIKE2_NESTED_V2`.

## Notes

- The markers keep the SPIKE2 prefix on purpose. The plugin files are byte-identical to layout-spike-2.
- A chat may echo a line-number prefix such as `10|` before a marker. That prefix is not part of the marker.
- Each chat loads its skill list when it opens, so use a new chat after installing a plugin.
