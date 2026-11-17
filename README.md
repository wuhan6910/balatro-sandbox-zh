# Sandbox — a creative-mode toolbox for Balatro

> **中文增强版**：本项目基于 Tariq Almheiri 的 Balatro Sandbox 继续开发，增加中文界面、
> 优惠券获取、自定义扑克牌、整副牌批量删除，以及牌型等级、出牌/弃牌次数、手牌上限和
> 经济数值编辑。原版与衍生版均采用 MIT License。

Spawn **any Joker or consumable** (Tarot / Planet / Spectral) straight into your live run,
with any **edition** (Foil / Holographic / Polychrome / Negative), through an in-game menu
built entirely from Balatro's own UI, card art, sounds, and animations — it looks and feels
like part of the game.

- Four compact buttons sit quietly on the right edge during a run.
- Click it → a collection-style browser opens with every Joker in the game (paginated,
  locked/undiscovered included), plus tabs for Tarot, Planet, and Spectral cards.
- Pick a modifier, click a card → it materializes into your Joker row / consumable slots
  with the game's own spawn animation. Reorder by dragging, exactly like normal play.

This fork also includes a Voucher browser, a playing-card creator, whole-deck
multi-selection deletion, and an in-game run editor for poker-hand levels, hand/discard
counts, hand-size limit, and money.

Great for: testing builds and joker orders, practicing lines, verifying score
calculators, content creation, or just messing around.

> Single-player only. It's a sandbox tool — obviously don't use it to fake scores on
> leaderboards or challenge runs you share as legitimate.

## Requirements

- Balatro (Steam, v1.0.1o) on **Windows or macOS**
- [Lovely injector](https://github.com/ethangreen-dev/lovely-injector/releases)
- [Steamodded](https://github.com/Steamodded/smods)

## Install

### 1. Lovely (the injector)

**Windows:** download `lovely-x86_64-pc-windows-msvc.zip`, extract `version.dll` into the
game folder (right-click Balatro in Steam → Manage → Browse local files). Launch normally.

**macOS:** download `lovely-aarch64-apple-darwin.tar.gz` (Apple Silicon) or
`lovely-x86_64-apple-darwin.tar.gz` (Intel), extract `liblovely.dylib` and
`run_lovely_macos.sh` into the game folder. If macOS quarantines them, run:
`xattr -d com.apple.quarantine liblovely.dylib run_lovely_macos.sh` in that folder.
Always launch via `run_lovely_macos.sh` — or make a double-clickable launcher so
you never need Terminal again:

```bash
osacompile -o "/Applications/Balatro Modded.app" -e 'do shell script "cd \"$HOME/Library/Application Support/Steam/steamapps/common/Balatro\" && nohup ./run_lovely_macos.sh > \"$HOME/Library/Application Support/Balatro/Mods/lovely/console.log\" 2>&1 &"'
```

Then launch **Balatro Modded** from Applications / Spotlight / the Dock like any
app (the game log goes to `Mods/lovely/console.log`). Windows users don't need
any of this — with `version.dll` in place, launching from Steam just works.

### 2. Steamodded (the mod loader)

Clone or download [Steamodded](https://github.com/Steamodded/smods) into your Mods folder:

- **Windows:** `%AppData%/Balatro/Mods/Steamodded`
- **macOS:** `~/Library/Application Support/Balatro/Mods/Steamodded`

### 3. This mod

Clone this repository:

```bash
git clone https://github.com/wuhan6910/balatro-sandbox-zh.git
```

Copy the cloned folder into the same `Mods` folder. Launch the game — you'll see the mods
badge on the main menu, and the Sandbox button in the HUD once you start a run.

## Usage

Four small buttons sit on the right edge of the screen during a run:

**`牌` — the playing-card creator.** Choose a rank, suit, enhancement, edition and
seal, then add the card to your hand or the draw pile.

**`数值` — run tuning.** Pick any poker hand and adjust its level, change the
hands and discards available in the current blind, change the base hands/discards
used by later blinds, edit the hand-size limit, and edit your money. Changes apply
immediately.

**`删牌` — the deck editor.** The whole run deck is shown on one screen (draw
pile, hand, discard and play areas). Click cards to select or deselect them, then press
`删除选中` to permanently remove every selected card at once.

**`全部` — the Browser.** A full collection-style screen of every card in the set,
five per row, with edition + sticker pickers. **Click a card** to add it, spawn as
many as you like, then back out.

| Action | How |
|---|---|
| Switch card type | tab buttons in the browser |
| Choose a modifier | edition cycle: None / Foil / Holo / Poly / Negative |
| Stickers | browser only: Eternal / Perishable / Rental |
| Spawn | click a card in the browser |
| Poker-hand level | open `数值`, choose the hand, then use -10 / -1 / +1 / +10 |
| Hands and discards | edit the current blind or the base value for later blinds in `数值` |
| Hand-size limit | use the -10 / -1 / +1 / +10 buttons next to `手牌上限` in `数值` |
| Money | use the -100 / -10 / -1 / +1 / +10 / +100 / 归零 buttons in `数值` |
| Delete deck cards | open `删牌`, select several cards, then press `删除选中` |
| Reorder / manage | drag cards in your Joker row as normal; sell to remove |

Everything spawns free and works exactly like the real item (copies, scoring, sell value).

## Compatibility

Built and tested against Balatro **1.0.1o** with Steamodded **1.0.0-beta**. No game files
are modified on disk; remove the mod folder to uninstall completely.

## License

This project is a derivative of Balatro Sandbox by Tariq Almheiri. The original work and
this derivative are distributed under the MIT License — see [LICENSE](LICENSE).
