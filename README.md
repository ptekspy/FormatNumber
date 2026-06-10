# FormatNumber

A Luau number formatting library with skeleton-based formatter construction and compact number formatting.

## Installation

Install the package with wally:

```bash
wally add ptekspy/formatnumber
```

## Simple API

Use the simple API from `FormatNumber.Simple` for common formatting operations.

```lua
local FormatNumber = require(path.to.FormatNumber.Simple)

local formatted = FormatNumber.Format(1234567)
local compact = FormatNumber.FormatCompact(1234567)

print(formatted) -- e.g. "1234567"
print(compact)   -- e.g. "1.2M"
```

Both `Format` and `FormatCompact` accept an optional skeleton string:

```lua
local formatted = FormatNumber.Format(1234.56, "compact")
local compact = FormatNumber.FormatCompact(1234.56, "compact")
```

## Advanced API

Use `FormatNumber.Main` when you need full control over notation, precision, grouping, and symbol settings.

```lua
local Main = require(path.to.FormatNumber.Main)

local formatted = Main.NumberFormatter.with()
    :Notation(Main.Notation.scientific())
    :Precision(Main.Precision.fraction(2))
    :Format(1234.56)

print(formatted) -- e.g. "1.23E3"
```

## Modules

- `FormatNumber.Simple` — helper functions for common formatting scenarios.
- `FormatNumber.Main` — builder-style formatter API, notation helpers, and advanced settings.
- `FormatNumber.Version` — package version information.

## License

This project is licensed under the Apache-2.0 license.
