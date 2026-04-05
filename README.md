# ZMK Config for Ergonaut One: Elixir + Vim + macOS

 Custom ZMK firmware configuration for Ergonaut One keyboard, optimized for Elixir development in Vim on macOS.


## Design Philosophy

This layout is designed around three core workflows:

1. **Elixir-first symbols** - Quick access to Elixir operators and syntax
2. **Vim-style navigation** - Arrow keys positioned for vim-like movement
3. **macOS integration** - Native support for Mission Control, media, and brightness

## Keymap

![Keymap Visualization](./keymap-drawer/ergonaut_one.svg?raw=true "Keymap")

*Auto-generated via [`keymap-drawer`](https://github.com/caksoylar/keymap-drawer) - updates automatically when keymap changes.*

## Layer Breakdown

### MAIN Layer
Standard QWERTY with home row mods:
- **Outer columns**: Brackets and special chars with Gui hold-taps
- **Home row**: Modifiers on hold (Ctrl, Alt)
- **Thumbs**: Layer access via hold-taps (SYM, NAV, Shift)

### SYM Layer - Elixir Operators
Optimized for Elixir development with dedicated macros:

**Top row (Elixir-specific):**
- `<-` - Pattern matching arrow
- `->` - Function arrow / case clause
- `%{` - Map literal (auto-spaced)
- `insl` - IO.inspect( ,label: "via vim macro")
- `<=` - Less than or equal (auto-spaced)
- `=>` - Map key-value separator (auto-spaced)
- `|>` - Pipe operator (the heart of Elixir)

**Middle row:** Standard symbols (`!@#$%^&*()`)

**Bottom row:** Numbers 0-9 with quick access

### NAV Layer - Vim-Style Navigation
Dual arrow key clusters for vim-like movement:

**Left cluster:**
- Arrow keys with `+/-/=` for quick math
- Home/End for line navigation

**Right cluster:**
- Mirrored arrows for convenience
- PageUp/PageDown for scrolling

**Top row:** F1-F12 with Gui hold-taps

### ADJ Layer - System Controls
Activated when both SYM + NAV are held (tri-layer):

**macOS controls:**
- Brightness: `Bri+` / `Bri-`
- Mission Control: `Windows` (Show All Windows) / `Apps` (Show All Apps)
- Media: `Mute`, `Vol-`, `Vol+`, `Play`, `Prev`, `Next`

**Bluetooth:**
- `BT 1-5` - Switch between 5 paired devices
- `BT CLR` - Clear current pairing

**System:**
- `BOOT` - Enter bootloader
- `RESET` - Soft reset
- `UNLOCK` - Studio unlock (for ZMK Studio)

### Chords (Combos)

Press two keys simultaneously (within 40ms) to output an entire word with a trailing space. Works on the MAIN layer only. A 150ms prior-idle guard prevents misfires during fast typing.

Defined in `config/combos.dtsi`. Tune `timeout-ms` (combo window) and `require-prior-idle-ms` (misfire guard) to taste.

**Word chords:**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| T+H | the | A+N | and | T+A | that |
| H+V | have | W+H | with | F+O | for |
| N+T | not | Y+U | you | T+S | this |
| B+U | but | F+M | from | T+Y | they |
| W+L | will | W+D | would | W+A | what |
| A+B | about | W+C | which | W+N | when |
| J+S | just | K+N | know | L+C | like |
| Y+R | your | C+D | could | S+H | should |
| B+F | before | B+C | because | T+K | think |
| A+L | also | A+F | after | T+M | time |
| A+G | again | S+M | some | G+D | good |
| M+R | more | N+V | never | E+V | even |
| V+R | very | W+K | work | W+Y | way |
| M+K | make | N+D | need | N+L | only |
| B+N | been | H+L | while | C+N | can |
| C+M | come | O+E | one | G+E | great |
| M+G | might | F+N | found | U+D | under |
| O+T | other | P+E | people | R+L | really |
| H+R | her | H+S | his | A+E | are |
| W+S | was | | | | |

**Utility chords:**

| Chord | Output |
|-------|--------|
| J+K | Escape |
| U+I | `(` |
| I+O | `)` |
| W+F | Caps Word |

## Key Features

### Elixir Macros
All Elixir operators are pre-spaced for faster typing:
```elixir
# Instead of typing: space + < + - + space
# Just tap: <-

result <- async_task()
%{key => value}
data |> transform() |> process()
```

### Vim Navigation
Natural arrow placement on right hand, mirrored on left for flexibility:
```
Left hand:         Right hand:
  ↑                   ↑
← ↓ →     mirrors   ← ↓ →
```

### macOS Integration
Native shortcuts for:
- Mission Control (Cmd+F3 variants)
- Brightness controls
- Media playback

### Software Bootloader
No need to disassemble the keyboard for firmware updates:
- **SYM + NAV + ]** (left) or **[** (right) enters bootloader
- Drag-and-drop `.uf2` files over USB
- Physical RESET button only needed if keyboard is completely bricked

## Setup

### Flashing Firmware

1. Download latest `firmware.zip` from [Actions](../../actions) tab
2. Extract to get `ergonaut_one_left-*.uf2` and `ergonaut_one_right-*.uf2`

**Method 1: Software Bootloader (Recommended)**

For **left half**:
1. Connect via USB-C (power can stay ON)
2. Hold **SYM + NAV** (both thumb keys) to activate ADJ layer
3. Tap **]** key (far left of top row = BOOT)
4. Drive mounts automatically
5. Copy `ergonaut_one_left-*.uf2` to the drive
6. Done! Keyboard reboots automatically

For **right half**:
1. Connect via USB-C (power can stay ON)
2. Hold **SYM + NAV** to activate ADJ layer
3. Tap **[** key (far right of top row = BOOT)
4. Drive mounts automatically
5. Copy `ergonaut_one_right-*.uf2` to the drive
6. Done!

**Method 2: Hardware Reset (if software method fails)**

Only needed if keyboard is completely non-responsive:
1. Turn power OFF
2. Connect via USB-C
3. Double-press physical RESET button (requires opening case)
4. Copy `.uf2` file to mounted drive

### Pairing Halves

1. Turn power OFF on both halves
2. Turn power ON on both halves
3. Press RESET **once** on both halves **simultaneously**

### Bluetooth Pairing

Hold SYM + NAV, then tap BT 1-5 to switch profiles:
- **BT 1-5**: Select device slot
- **BT CLR**: Clear current pairing (pair new device)

## Customization

### Editing the Keymap

Two options:

#### Option 1: Keymap Editor (GUI)
1. Open [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)
2. Connect to your GitHub account
3. Make changes and save - firmware builds automatically

#### Option 2: Manual (recommended for advanced users)
1. Edit [`config/ergonaut_one.keymap`](config/ergonaut_one.keymap)
2. Commit and push
3. Download built firmware from Actions tab

### Customizing Elixir Macros

Macros are defined in the keymap file. To modify:

```c
macros {
    m_elpipe: m_elpipe {
        bindings = <&kp PIPE &kp GT &kp SPACE>;
        // Produces: |>
    };
}
```

### Visualization

The keymap visualization auto-updates via GitHub Actions when you change the keymap. Configuration is in [`keymap-drawer/config.yaml`](keymap-drawer/config.yaml).

## Troubleshooting

### "File Transfer Error" after flashing
This is normal and expected behavior. See [ZMK docs](https://zmk.dev/docs/troubleshooting#file-transfer-error).

### Halves not connecting
1. Turn both OFF
2. Turn both ON
3. Simultaneously press RESET on both halves

### Keys not working as expected
Check layer indicators - you might be on the wrong layer. Press SYM or NAV thumb keys to return to MAIN.

## Credits

Hardware: [Ergonaut One](https://github.com/ergonautkb/one) by ergonautkb

Original layout inspiration:
- [Miryoku](https://github.com/manna-harbour/miryoku) - Home row mods concept
- [Watchman layouts](https://github.com/aroum/Watchman-layouts) - Layer structure

Heavily modified for Elixir/Vim/macOS workflow.
