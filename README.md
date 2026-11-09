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

Press two or more keys simultaneously (within 40ms) to output an entire word with a trailing space. Works on the MAIN layer only. A 250ms prior-idle guard prevents misfires during fast typing.

Defined in `config/combos.dtsi`. Tune `timeout-ms` (combo window) and `require-prior-idle-ms` (misfire guard) to taste.

**2-key word chords — core (58):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `T+H` | the | `A+N` | and | `T+A` | that |
| `H+V` | have | `W+H` | with | `O+F` | for |
| `T+N` | not | `Q+Y` | you | `T+S` | this |
| `U+B` | but | `F+M` | from | `T+Y` | they |
| `W+L` | will | `W+D` | would | `W+A` | what |
| `A+B` | about | `W+C` | which | `W+N` | when |
| `S+J` | just | `K+N` | know | `L+C` | like |
| `R+Y` | your | `O+C` | could | `S+H` | should |
| `J+B` | before | `C+B` | because | `T+K` | think |
| `A+L` | also | `A+F` | after | `T+M` | time |
| `A+G` | again | `S+M` | some | `D+G` | good |
| `R+M` | more | `V+N` | never | `E+V` | even |
| `Y+V` | very | `W+K` | work | `W+Y` | way |
| `K+M` | make | `D+N` | need | `L+N` | only |
| `B+N` | been | `H+L` | while | `C+N` | can |
| `C+M` | come | `E+O` | one | `E+G` | great |
| `G+M` | might | `F+N` | found | `U+D` | under |
| `T+O` | other | `E+P` | people | `R+L` | really |
| `R+H` | her | `H+Z` | his | `E+A` | are |
| `A+S` | was |  |  |  |  |

**2-key word chords — extended (100):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `Y+A` | activity | `T+C` | article | `E+N` | begin |
| `O+V` | behavior | `E+B` | believe | `O+B` | both |
| `E+U` | business | `A+C` | call | `S+C` | case |
| `E+H` | change | `O+M` | company | `D+H` | daughter |
| `I+C` | decision | `D+L` | develop | `I+O` | doing |
| `O+N` | down | `E+Y` | early | `Y+X` | economy |
| `U+Z` | education | `F+J` | effect | `I+V` | evidence |
| `I+L` | family | `E+L` | feel | `I+F` | field |
| `I+N` | find | `F+C` | force | `R+I` | friend |
| `G+L` | general | `E+I` | give | `I+G` | going |
| `O+G` | government | `A+D` | hand | `E+R` | hear |
| `I+H` | high | `Y+I` | history | `O+D` | hold |
| `R+D` | industry | `U+I` | issue | `I+D` | kind |
| `A+V` | leave | `E+F` | left | `S+L` | less |
| `L+V` | level | `O+K` | look | `G+N` | management |
| `A+M` | many | `A+K` | market | `L+M` | material |
| `I+M` | media | `T+D` | method | `E+M` | move |
| `U+C` | much | `T+U` | must | `Z+M` | name |
| `U+A` | nature | `E+X` | next | `R+N` | number |
| `P+G` | page | `P+N` | parent | `R+P` | part |
| `P+L` | place | `P+A` | play | `Y+L` | policy |
| `I+S` | possible | `P+C` | practice | `R+C` | price |
| `R+O` | problem | `P+S` | process | `R+U` | product |
| `O+P` | program | `I+P` | public | `U+L` | quality |
| `U+O` | question | `P+H` | relationship | `T+P` | report |
| `A+H` | research | `I+A` | said | `O+H` | school |
| `Y+C` | security | `E+S` | seem | `R+S` | service |
| `O+S` | show | `S+D` | side | `T+I` | situation |
| `O+A` | social | `R+A` | start | `U+S` | student |
| `U+P` | support | `Y+S` | system | `T+L` | talk |
| `H+C` | teacher | `E+T` | tell | `Y+O` | theory |
| `U+X` | truth | `Q+U` | turn | `U+V` | value |
| `W+I` | view | `W+T` | want | `W+R` | water |
| `W+E` | week |  |  |  |  |

**3-key word chords — common English (43):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `U+O+G` | through | `E+T+H` | there | `T+A+H` | than |
| `T+I+H` | their | `T+O+H` | those | `I+G+H` | thing |
| `O+G+H` | though | `Q+E+H` | three | `E+O+G` | together |
| `T+A+N` | another | `W+R+H` | where | `W+T+H` | whether |
| `E+B+N` | between | `T+S+M` | something | `R+A+D` | already |
| `W+A+L` | always | `R+A+N` | around | `R+I+D` | different |
| `R+P+M` | important | `T+S+L` | still | `E+Y+V` | every |
| `I+S+F` | first | `W+R+L` | world | `T+I+L` | little |
| `R+I+H` | right | `I+B+N` | being | `S+L+M` | small |
| `T+A+K` | take | `W+E+L` | well | `T+I+N` | into |
| `E+R+H` | here | `I+S+N` | since | `R+Y+O` | story |
| `W+E+I` | write | `U+S+G` | using | `A+L+C` | actually |
| `R+L+N` | learn | `T+P+N` | point | `O+G+N` | long |
| `E+P+K` | keep | `A+S+M` | same | `E+A+H` | each |
| `P+H+L` | help |  |  |  |  |

**3-key word chords — ML/AI (23):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `D+F+N` | diffusion | `E+B+M` | embedding | `I+D+G` | gradient |
| `I+F+N` | inference | `I+G+N` | training | `T+A+C` | activation |
| `P+K+B` | backprop | `E+R+U` | neural | `R+P+D` | dropout |
| `T+S+D` | dataset | `T+K+N` | tokenize | `T+L+N` | latent |
| `S+F+M` | softmax | `R+S+D` | residual | `P+K+C` | checkpoint |
| `I+G+L` | logit | `E+O+P` | epoch | `A+C+B` | batch |
| `D+L+M` | model | `G+L+N` | language | `E+P+M` | parameter |
| `A+B+M` | mamba | `C+V+N` | convolutional |  |  |

**3-key word chords — Rust (13):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `R+I+A` | trait | `W+T+A` | await | `I+L+M` | impl |
| `R+S+L` | Result< | `T+O+N` | Option< | `Q+E+U` | enum |
| `T+C+M` | match | `E+T+U` | return | `I+D+V` | derive |
| `S+L+C` | closure | `E+F+M` | lifetime | `W+O+B` | borrow |
| `T+U+Z` | mut |  |  |  |  |

**3-key word chords — Haskell (6):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `O+D+M` | monad | `U+F+C` | functor | `E+Y+B` | Maybe |
| `I+D+M` | monoid | `L+B+M` | lambda | `T+P+C` | typeclass |

**3-key word chords — other (6):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `F+C+N` | function | `U+D+L` | Claude | `T+P+A` | Anthropic |
| `R+U+A` | Azure | `U+D+K` | duckdb | `I+C+B` | iceberg |

**4-key word chords (10):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `O+S+F+M` | transformer | `W+T+K+N` | quantization | `I+P+L+M` | implementation |
| `R+U+S+C` | struct | `A+S+C+N` | async | `S+H+K+L` | haskell |
| `O+A+F+N` | forall | `S+K+L+N` | Skinly | `O+S+D+B` | Beiersdorf |
| `R+A+H+C` | architecture |  |  |  |  |

**Newest common-word chords (100):**

| Chord | Word | Chord | Word | Chord | Word |
|-------|------|-------|------|-------|------|
| `A+X+M` | am | `A+X+N` | an | `W+R+N` | answer |
| `A+S+J` | as | `T+A+J` | at | `E+J+B` | be |
| `K+B` | book | `Y+O+B` | boy | `Q+Y+B` | buy |
| `Y+B` | by | `U+S+C` | cause | `H+L+C` | child |
| `R+H+C` | children | `T+Y+C` | city | `T+U+C` | cut |
| `Y+D` | day | `T+D+H` | death | `Q+I+D` | did |
| `O+D+X` | do | `O+S+D` | does | `O+D+N` | done |
| `D+V` | drive | `R+A+H` | earth | `E+T+A` | eat |
| `E+Y+Z` | eye | `A+F+C` | fact | `F+H` | father |
| `O+F+M` | form | `E+G+J` | get | `R+I+L` | girl |
| `Q+O+G` | go | `O+G+Z` | got | `U+G` | group |
| `A+D+H` | had | `A+S+H` | has | `E+H+Z` | he |
| `D+H+X` | head | `Q+I+H` | hi | `I+H+Z` | him |
| `I+H+V` | hit | `E+O+M` | home | `U+O+S` | house |
| `I+A+D` | idea | `I+F+Z` | if | `I+X+N` | in |
| `Q+I+S` | is | `T+I+Z` | it | `T+I+S` | its |
| `Q+W+L` | law | `E+T+L` | let | `E+R+L` | letter |
| `F+L` | life | `E+L+N` | line | `I+L+V` | live |
| `E+S+L` | lose | `D+M` | made | `A+V+M` | man |
| `Y+A+X` | may | `E+X+M` | me | `E+Z+M` | men |
| `R+O+M` | mother | `Y+G` | my | `Q+O+N` | no |
| `O+F+X` | of | `O+H+Z` | oh | `O+X+N` | on |
| `Q+R+O` | or | `R+O+D` | order | `R+U+O` | our |
| `T+U+O` | out | `R+P+A` | paper | `Y+P` | pay |
| `S+N` | person | `W+P` | power | `T+U+P` | put |
| `R+X+N` | ran | `E+R+A` | read | `R+O+N` | reason |
| `Q+R+U` | run | `W+A+J` | saw | `Y+A+S` | say |
| `E+S+J` | see | `E+T+S` | set | `S+H+L` | shall |
| `E+S+H` | she | `I+S+Z` | sit | `O+S+Z` | so |
| `E+T+M` | them | `Q+T+O` | to | `E+R+J` | tree |
| `R+Y+X` | try | `U+P+X` | up | `Q+U+S` | us |
| `E+U+S` | use | `W+E+J` | we | `W+E+N` | went |
| `W+E+R` | were | `W+I+N` | win | `W+O` | word |
| `R+Y+A` | year |  |  |  |  |

**Utility chords (10):**

| Chord | Output | Chord | Output |
|-------|--------|-------|--------|
| `J+K` | Esc | `D+F` | Tab |
| `K+L` | Tab | `W+F` | Caps Word |
| `J+X` | `(` | `Q+J` | `)` |
| `J+Z` | `[` | `J+L` | `]` |
| `J+V` | Enter | `Y+Z` | Backspace |

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
