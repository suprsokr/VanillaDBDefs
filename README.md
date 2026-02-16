# Vanilla DBDefs

Database definitions for World of Warcraft Vanilla (1.0.0 - 1.12.3) DBC files.

This is a curated subset of the [WoWDBDefs](https://github.com/wowdev/WoWDBDefs) project, containing only the database definitions for the vanilla expansion of World of Warcraft.

## Features

- Complete DBC column definitions for vanilla WoW (patch 1.0.0 through 1.12.3)
- Lightweight and focused - no expansion content
- Human readable DBD format
- Machine readable for parsing and code generation

## Project Goals

- Provide accurate, up-to-date database definitions for vanilla WoW
- Serve as a reference for private servers, emulators, and content sites
- Maintain a minimal, focused repository dedicated to vanilla only

## DBD Format

The DBD (Database Definition) format specifies the structure of DBC (Database Client) files used by World of Warcraft.

Each `.dbd` file contains:

1. **COLUMNS section** - Defines all possible columns with their types:
   - `int` - 32-bit integer
   - `uint` - 32-bit unsigned integer
   - `float` - 32-bit floating point
   - `string` - String (not localized after 1.12)
   - `locstring` - Localized string (language-specific)

2. **VERSION sections** - Specifies which columns are used in which builds:
   - `BUILD` - Which game build(s) this definition applies to
   - Column list - The columns and their specifications for that version

### Example

```
COLUMNS
int ID
string Name
int Level
float Speed

BUILD 1.12.0.5595-1.12.3.6141
$id$ID<32>
Name
Level<32>
Speed
```

This defines a simple table with 4 columns, used in builds 1.12.0.5595 through 1.12.3.6141.

## Data Types

- `<32>` - 32-bit size
- `<16>` - 16-bit size
- `<8>` - 8-bit size
- `<u32>` - 32-bit unsigned
- `[N]` - Array with N elements
- `$id$` - Primary key annotation
- `?` - Unverified column name

## File Structure

- `/definitions/` - All DBC definition files
  - One file per database table (e.g., `Spell.dbd`, `Item.dbd`, `Quest.dbd`)

## Usage

To use these definitions, you'll need a DBD parser. The original [WoWDBDefs](https://github.com/wowdev/WoWDBDefs) repository includes reference implementations in Python and C# that can parse these files.

## Build Support

This repository contains definitions for vanilla WoW builds:
- **1.0.0** - Launch
- **1.1.0 - 1.3.1**
- **1.4.0 - 1.5.1**
- **1.6.0 - 1.7.1**
- **1.8.0 - 1.8.4**
- **1.9.0 - 1.9.2**
- **1.9.3 - 1.10.2**
- **1.11.0 - 1.11.2**
- **1.12.0 - 1.12.3** (Final vanilla patch)

## Credits

This project is derived from the [WoWDBDefs](https://github.com/wowdev/WoWDBDefs) repository by the WoWDev community.

All feedback and contributions are welcome!

## License

See LICENSE.md for license information. This work is built upon the WoWDBDefs project.
