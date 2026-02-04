# Glove80 ZMK Configuration

Custom ZMK firmware configuration for the MoErgo Glove80 keyboard, adapted from the [sliceMK ErgoDox configuration](https://github.com/nothingfortune/unified-zmk-config-template-sliceMK).

**Optimized for**: macOS, Technical Project Managers, clamshell/monitor setups

## ⌨️ Layout Overview

This configuration features a QWERTY layout with **Home Row Mods** using the **GACS** pattern (Gui-Alt-Ctrl-Shift), optimized for macOS productivity.

### Layers

| Layer | Name | Description |
|-------|------|-------------|
| 0 | **Base** | QWERTY with home row mods, media, Rectangle shortcuts |
| 1 | **Symbol** | Programming symbols, brackets, operators (sliceMK layout) |
| 2 | **Power** | Shortcuts, navigation, sticky mods, clipboard |
| 3 | **Navigation** | Mouse movement and scrolling with acceleration |
| 4 | **Numpad** | Numeric keypad, function keys, brightness |
| 5 | **Function** | F1-F24, Bluetooth, USB/BLE toggle |
| 6 | **Magic** | Glove80 RGB controls, bootloader, system reset |

### Key Features

#### 🎤 TPM-Optimized Function Row
| Left Side | Right Side |
|-----------|------------|
| 🔅 Brightness Down | ⏮ Previous Track |
| 🔆 Brightness Up | ⏭ Next Track |
| 🪟 Mission Control | 🔉 Volume Down |
| 🔒 **Lock Screen** | 🔊 Volume Up |
| ✨ Magic Layer | `[]` Auto-pair |

> **Lock Screen**: ⌃⌘Q - instantly locks macOS

#### 🪟 Right Column (Auto-pair Brackets)
| Position | Function |
|----------|----------|
| Top | `[]` Auto-pair brackets |
| Row 1 | `{}` Auto-pair braces |
| Row 2 | `()` Auto-pair parens |
| Row 3 | Enter/' (hold/tap) |
| Row 4 | `<>` Auto-pair angles |
| Bottom | ⚡ Hyper Key (⌘⌃⌥⇧) |

#### 🏠 Home Row Mods (GACS Layout)
| Key | Hold | Tap |
|-----|------|-----|
| A | Left GUI (⌘) | A |
| S | Left Alt (⌥) | S |
| D | Left Ctrl (⌃) | D |
| F | Left Shift (⇧) | F |
| J | Right Shift (⇧) | J |
| K | Right Ctrl (⌃) | K |
| L | Right Alt (⌥) | L |
| ; | Right GUI (⌘) | ; |

#### 🎯 Smart Behaviors
- **Backspace** → Hold: Delete Word (⌥+⌫) | Tap: Backspace
- **Left Arrow** → Hold: Word Left (⌃+←) | Tap: Left
- **Right Arrow** → Hold: Word Right (⌃+→) | Tap: Right
- **Grave/Escape** → Escape normally, Grave with Shift/⌘
- **G/H keys** → Hold: Symbol Layer | Tap: G/H
- **Hyper Key** → ⌘⌃⌥⇧ sticky mods for Raycast/Alfred
- **Lock Screen** → ⌃⌘Q in function row

#### 🖱️ Mouse Keys (Pointing)
| Setting | Value | Description |
|---------|-------|--------------|
| Cursor Speed | 1500 | 2.5x default (600) |
| Scroll Speed | 20 | 2x default (10) |
| Time to Max | 0ms | Instant max speed |
| Acceleration | Linear | No ramp-up curve |

#### ⌨️ Symbol Layer (sliceMK Layout)
```
Left Hand:               Right Hand:
~  _  _  _  _  _         _  _  _  _  `  
_  _  $  #  ^  _         _  _  @  %  _  
_  -  *  |  &  _         _  (  )  +  =  :
_  {  }  <  >  _         _  [  ]  !  ?  _
```

## 🔧 Building Firmware

### Using GitHub Actions (Recommended)

1. Fork this repository
2. Push your changes
3. GitHub Actions will automatically build the firmware
4. Download `glove80.uf2` from the Actions artifacts

### Local Build

```bash
# Using Docker
./build.sh

# Or use the provided Dockerfile
docker build -t glove80-zmk .
docker run -v $(pwd):/workspace glove80-zmk
```

## 📁 File Structure

```
config/
├── glove80.keymap    # Main keymap configuration
├── glove80.conf      # ZMK settings (mouse, RGB, Bluetooth)
├── keymap.json       # Layout editor export (if used)
└── info.json         # Keyboard metadata
```

## ⚙️ Configuration Options

Edit `config/glove80.conf` to customize:

| Setting | Description |
|---------|-------------|
| `CONFIG_ZMK_POINTING=y` | Enable mouse/pointing support |
| `CONFIG_ZMK_SLEEP=y` | Enable deep sleep mode |
| `CONFIG_ZMK_IDLE_SLEEP_TIMEOUT` | Sleep timeout in ms |
| `CONFIG_BT_CTLR_TX_PWR_PLUS_8=y` | Max Bluetooth power |
| `CONFIG_ZMK_RGB_UNDERGLOW=y` | Enable RGB lighting |

## 🔗 Layer Access

| Key Combo | Layer |
|-----------|-------|
| Hold **Space** | Navigation (mouse) |
| Hold **Return** (left thumb) | Power (shortcuts) |
| Hold **?** (bottom left) | Numpad |
| Hold **.** (bottom right) | Symbol |
| Hold **FN** keys (top center) | Function/System |
| Tap **Magic** (bottom left corner) | RGB status, hold for Magic layer |

## 🎨 Magic Layer Functions

The Magic layer provides Glove80-specific controls:

- **RGB Controls**: Speed, Saturation, Hue, Brightness, Effects
- **Bluetooth**: Profile selection (BT 0-4), Clear pairing
- **Output**: Toggle USB/BLE mode
- **System**: Bootloader, System Reset

## 📚 Resources

- [MoErgo Glove80 Support](https://moergo.com/glove80-support)
- [MoErgo Discord](https://moergo.com/discord)
- [ZMK Documentation](https://zmk.dev/docs)
- [ZMK Discord](https://discord.gg/8cfMkQksSB)
- [Glove80 ZMK Fork](https://github.com/moergo-sc/zmk)

## 🙏 Credits

- Keymap adapted from [nothingfortune's sliceMK ErgoDox config](https://github.com/nothingfortune/unified-zmk-config-template-sliceMK)
- Based on MoErgo's official Glove80 ZMK template

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

