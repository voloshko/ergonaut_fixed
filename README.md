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
Standard QWERTY with home row mods (tuned for low false positives):
- **Outer columns**: Brackets and special chars with Gui hold-taps
- **Home row**: Modifiers on hold (Ctrl, Alt, Shift, Meta) — 280ms hold threshold with 180ms idle guard
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

Press two or more keys simultaneously (within 40ms) to output an entire word with a trailing space. Works on the MAIN layer only. A 150ms prior-idle guard prevents misfires during fast typing.

Defined in `config/combos.dtsi`. Tune `timeout-ms` (combo window) and `require-prior-idle-ms` (misfire guard) to taste.

**2-key word chords (158):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| T+H | the | A+N | and | T+A | that |
| H+V | have | W+H | with | F+O | for |
| N+T | not | Y+U | you | T+S | this |
| B+U | but | F+M | from | T+Y | they |
| W+L | will | W+D | would | W+A | what |
| A+B | about | W+C | which | W+N | when |
| J+S | just | K+N | know | L+C | like |
| Y+R | your | C+O | could | S+H | should |
| B+F | before | B+C | because | T+K | think |
| A+L | also | A+F | after | T+M | time |
| A+G | again | S+M | some | G+D | good |
| M+R | more | N+V | never | E+V | even |
| V+Y | very | W+K | work | W+Y | way |
| M+K | make | N+D | need | N+L | only |
| B+N | been | H+L | while | C+N | can |
| C+M | come | O+E | one | G+E | great |
| M+G | might | F+N | found | U+D | under |
| O+T | other | P+E | people | R+L | really |
| H+R | her | H+S | his | A+E | are |
| A+S | was | | | | |

**2-key word chords (100 new):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| A+I | said | O+K | look | W+T | want |
| I+E | give | I+N | find | T+E | tell |
| S+E | seem | E+L | feel | A+V | leave |
| C+A | call | A+R | start | S+O | show |
| E+R | hear | P+A | play | M+E | move |
| B+E | believe | O+D | hold | E+N | begin |
| T+L | talk | T+R | turn | U+T | must |
| U+C | much | M+A | many | L+S | less |
| N+R | number | P+R | part | P+L | place |
| O+N | down | E+F | left | R+O | problem |
| A+D | hand | C+S | case | E+Y | early |
| H+E | change | I+D | kind | E+X | next |
| B+O | both | O+A | social | O+I | doing |
| G+I | going | N+M | name | S+I | possible |
| G+R | general | H+O | school | H+I | high |
| U+E | business | I+U | issue | S+D | side |
| P+I | public | A+K | market | S+N | sense |
| P+O | program | U+O | question | G+O | government |
| O+M | company | W+E | week | I+L | family |
| S+R | service | R+I | friend | R+C | price |
| P+T | report | C+I | decision | P+N | parent |
| I+T | situation | D+L | develop | S+Y | system |
| R+U | product | S+U | student | P+S | process |
| T+D | method | A+H | research | W+R | water |
| T+C | article | U+P | support | V+I | evidence |
| A+Y | activity | A+U | nature | O+Y | theory |
| I+Y | history | U+L | quality | C+Y | security |
| M+Y | economy | D+R | industry | M+I | media |
| P+C | practice | U+N | education | N+G | management |
| L+V | level | H+P | relationship | M+L | material |
| B+R | behavior | I+W | view | F+T | effect |
| L+Y | policy | F+I | field | D+H | daughter |
| C+H | teacher | P+G | page | F+C | force |
| U+H | truth |

**3-key word chords (91) — common English:**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| T+H+R | through | T+H+E | there | T+H+A | than |
| T+H+I | their | T+H+O | those | H+I+G | thing |
| T+H+U | though | T+R+E | three | T+O+R | together |
| A+N+T | another | W+H+R | where | W+H+T | whether |
| B+E+N | between | S+M+T | something | A+R+D | already |
| A+L+W | always | A+R+N | around | D+I+R | different |
| M+P+R | important | S+T+L | still | E+V+Y | every |
| F+I+S | first | W+R+L | world | L+T+I | little |
| R+I+G | right | B+I+N | being | S+M+L | small |
| T+A+K | take | W+E+L | well | I+N+T | into |
| H+E+R | here | S+I+N | since | S+T+R | story |
| W+R+T | write | U+S+N | using | A+C+L | actually |
| L+R+N | learn | P+N+T | point | O+N+G | long |
| K+E+P | keep | S+A+M | same | E+A+H | each |
| H+L+P | help | | | | |

**3-key word chords — ML/AI:**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| D+F+N | diffusion | E+M+B | embedding | G+R+D | gradient |
| I+N+F | inference | T+R+N | training | A+C+T | activation |
| B+P+R | backprop | N+R+L | neural | D+R+P | dropout |
| D+S+T | dataset | T+K+N | tokenize | L+T+N | latent |
| S+F+M | softmax | R+S+D | residual | C+K+P | checkpoint |
| L+G+I | logit | E+P+O | epoch | B+A+C | batch |
| M+D+L | model | L+N+G | language | P+R+M | parameter |
| M+A+B | mamba | C+N+V | convolutional | | |

**3-key word chords — Rust:**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| T+R+A | trait | A+W+T | await | I+M+L | impl |
| R+S+L | Result< | O+T+N | Option< | E+N+M | enum |
| M+T+C | match | R+E+T | return | D+R+I | derive |
| C+L+S | closure | L+F+T | lifetime | B+R+W | borrow |
| M+T+N | mut | | | | |

**3-key word chords — Haskell:**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| M+N+D | monad | F+C+T | functor | M+A+Y | Maybe |
| M+N+I | monoid | L+M+B | lambda | T+P+C | typeclass |

**3-key word chords — other:**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| F+N+C | function | C+L+A | Claude | A+T+P | Anthropic |
| A+U+R | Azure | D+U+K | duckdb | I+C+B | iceberg |

**4-key word chords (10):**

| Chord | Word | Chord | Word |
|-------|------|-------|------|
| T+R+A+N | transformer | K+W+N+T | quantization |
| I+M+P+L | implementation | S+T+R+C | struct |
| A+S+N+C | async | H+S+K+L | haskell |
| F+O+A+N | forall | S+K+N+L | Skinly |
| B+E+I+R | Beiersdorf | A+R+C+H | architecture |

**Utility chords:**

| Chord | Output |
|-------|--------|
| J+K | Escape |
| D+F | Tab |
| K+L | Tab |
| W+F | Caps Word |
| U+I | `(` |
| I+O | `)` |
| H+J | `[` |
| J+L | `]` |
| N+M | Enter |
| H+M | Backspace |

## Key Features

### Home Row Modifier Tuning

Home row mods use a hold-tap behavior with custom timing to prevent accidental modifier activation during fast typing:

| Setting | Value | Purpose |
|---------|-------|---------|
| `tapping-term-ms` | 280ms | Must hold this long before registering as modifier |
| `require-prior-idle-ms` | 180ms | If any key was pressed in the last 180ms, always register as tap |
| `quick-tap-ms` | 200ms | Retap within this window always produces a tap |
| `flavor` | `balanced` | Context-aware hold/tap decision algorithm |

**Why this matters:** The idle guard (`require-prior-idle-ms`) is the key setting — it prevents accidental Meta+Space language switches during fast typing. When you're typing quickly, home row keys always produce letters. You must intentionally pause and hold to get a modifier.

To adjust sensitivity, edit the `&mt` block in [`config/ergonaut_one.keymap`](config/ergonaut_one.keymap):
- **Too sensitive?** Increase `tapping-term-ms` (try 300–350ms) or `require-prior-idle-ms` (try 200–250ms)
- **Too slow to activate?** Decrease `tapping-term-ms` (try 230–260ms)

### Tap-Dance

Double-tap keys for extra functionality (150ms window):

| Key | 1 Tap | 2 Taps | Use case |
|-----|-------|--------|----------|
| **Backspace** | Backspace | Ctrl+Backspace | Delete word on double-tap |
| **Dot** | `.` | `:` | Vim command mode without SYM layer |
| **Comma** | `,` | `;` | Semicolon without SYM layer |

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
