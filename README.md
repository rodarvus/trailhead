# Trailhead

Trailhead is a native MUSHclient plugin for Aardwolf route research. It reads
Search & Destroy area starts, asks the mapper for distances from a configured
source room, and can catalogue long mapper walks observed while playing.

Trailhead also runs in Proteles through its MUSHclient compatibility shim.

## Install

Load `trailhead.xml` as a MUSHclient plugin. The plugin is self-contained in
that XML file.

The short command alias is `th`.

## Commands

```text
trailhead                 Show cached area table.
trailhead areas           Group cached areas by best distance.
trailhead refresh [area]  Re-read S&D and mapper distances.
trailhead missing         Show no-start/no-path/portal-only rows.
trailhead area <key>      Show one area key or name fragment.
trailhead monitor [on|off]  Record observed mapper walks. Default: off.
trailhead threshold [n]   Record walks longer than n steps. Default: 10.
trailhead walks [n] [area]  Show longest confirmed mapper walks. Default: 10.
trailhead source [room]   Show or set source room. Default: 32418.
trailhead version         Show installed version.
trailhead reload          Reload the plugin.
trailhead update [confirm]  Check GitHub; confirm downloads and reloads.
trailhead help            Show help.
```

Examples:

```text
th refresh
th areas
th monitor on
th threshold 15
th walks tol 2
th update
```

## Data

Trailhead stores runtime state in a local SQLite database. On native
MUSHclient, the catalogue lives under the plugin state directory reported by
`GetInfo(85)`. On Proteles, it uses the per-character database directory
reported by `proteles.databaseDir()`.

## License

MIT. See `LICENSE`.
