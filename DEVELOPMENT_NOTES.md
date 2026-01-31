# Bevlord Development Notes

## Current State (2026-01-30)

### Project Overview
A beverage price calculator for BC that calculates cost per beverage including taxes and deposit fees. Live at: https://graymackle.github.io/bevlord

### Three Display Modes

#### 1. Light Mode (Default)
- **Font**: Arial (body), Kings (title)
- **Colors**: Deep red background gradient (#8B0000 to #B22222), white container, black text, crimson buttons
- **Icon**: Beer emoji 🍺 on both sides of title
- **Checkbox color**: Red (#DC143C)
- **Square corners** throughout

#### 2. Guinness Mode
- **Toggle**: Above title on the right
- **Font**: Metamorphous throughout (including title) at 15px base
- **Colors**: Dark brown background, beige/gold accents (#d4af37), off-white text
- **Icon**: Shamrock ☘️ on both sides of title
- **Checkbox color**: Gold (#d4af37)
- **Special behavior**: Disabled when SPD mode is active

#### 3. SPD Mode (Overrides everything)
- **Toggle**: At bottom below combined total, on the right
- **Label**: Changes from "SPD Mode" to "ΣΦΔ Mode" when active
- **Font**: Times New Roman throughout at 17px base
- **Colors**: Black container, red text (#FF0000), very dark red background (#5a0000 to #7a0000)
- **Icon**: Castle emoji 🏰 on both sides of title
- **Text conversion**: ALL English letters convert to Greek (retains capitalization)
  - Applies to all visible text AND placeholder text in input fields
  - Input text color is dull red (#8B0000)
- **X button**: Black text (#000000) on dark red background (#5a0000)
- **Combined total box**: Dark red background (#5a0000) with red text
- **Border above SPD toggle**: Matches background (#5a0000)
- **Prevents**: Guinness mode from changing anything while active

### Key Features
- **Mixer checkbox**: 7% tax (was "Non-Alcoholic")
- **Default**: 15% tax for alcoholic beverages
- **Deposit**: $0.10 per beverage automatically added
- **Running Total**: Optional list tracking with combined average
- **Remove buttons**: Square, red with appropriate text color per mode

### Technical Details
- Single HTML file (index.html)
- Uses Google Fonts: Kings, Cinzel, Metamorphous
- Greek letter mapping in JavaScript for SPD mode conversion
- Container positioned at top with fixed margin to reduce mode-switching shifts
- Minimum height: 600px on container

### Known Issues/Quirks
- Minor shifting still occurs when switching modes (acceptable per user)
- Container uses `align-items: flex-start` with `padding-top: 40px` to minimize vertical shifting

### Mode Interaction Logic
```
SPD Mode OFF:
  - Guinness toggle controls appearance (beer ↔ shamrock, colors, fonts)

SPD Mode ON:
  - Overrides all styling with SPD theme
  - Guinness toggle does nothing
  - Castle icons, Greek text, Times New Roman

SPD Mode turned OFF:
  - Restores appropriate mode based on Guinness toggle state
  - Converts Greek text back to English
  - Restores original emojis
```

### File Structure
```
/Bevlord
  index.html          - Main application file
  README.md           - User-facing documentation
  DEVELOPMENT_NOTES.md - This file (development context)
```

### Next Potential Tasks
- Add images (SVG preferred) for icons if desired
- Consider additional visual refinements
- Performance optimizations if needed
- Additional calculation features if requested

### Greek Letter Mapping (SPD Mode)
```javascript
Uppercase: A→Α, B→Β, C→Ξ, D→Δ, E→Ε, F→Φ, G→Γ, H→Η, I→Ι, J→Ψ, K→Κ, L→Λ, M→Μ,
           N→Ν, O→Ο, P→Π, Q→Θ, R→Ρ, S→Σ, T→Τ, U→Υ, V→Ω, W→Ω, X→Χ, Y→Ψ, Z→Ζ

Lowercase: a→α, b→β, c→ξ, d→δ, e→ε, f→φ, g→γ, h→η, i→ι, j→ψ, k→κ, l→λ, m→μ,
           n→ν, o→ο, p→π, q→θ, r→ρ, s→σ, t→τ, u→υ, v→ω, w→ω, x→χ, y→ψ, z→ζ
```

### Git Repository
- GitHub: https://github.com/graymackle/bevlord
- Live site auto-deploys from main branch via GitHub Pages
