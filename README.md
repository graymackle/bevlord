# Bevlord - Beverage Price Calculator

A web-based calculator for determining the true cost per beverage in BC, accounting for taxes and deposit fees.

## Live Site
https://graymackle.github.io/bevlord

## Current Features

### Basic Calculator
- Input total price and pack size
- Calculates cost per beverage including all fees

### BC Tax Calculation
- **Default (unchecked)**: 15% tax for alcoholic beverages
- **Mixer checkbox**: 7% tax for mixers and non-alcoholic drinks
- **Deposit fee**: Automatically adds $0.10 per beverage

### Display Modes
- **Light Mode (Default)**: Red theme with clean Arial font
- **Guinness Mode**: Dark brown theme with gold accents and Metamorphous font - toggle above title
- **SPD Mode**: Black and red theme with Times New Roman font and Greek letter conversion - toggle at bottom
  - Overrides other modes when active
  - All text converts to Greek letters while maintaining meaning

### Running Total Feature
- **Running Total checkbox**: Track multiple calculations in a list
- Each item shows:
  - Original price
  - Quantity
  - Price per can (with tax and deposit)
  - Remove button (×) to delete from list
- **Combined Total**: Automatically calculates the average price per can across all items in the list
  - Handles mixed alcoholic/non-alcoholic items with proper tax rates
  - Shows detailed breakdown (total price, tax, deposits)

### Mobile Friendly
- Responsive design works on iPhone Safari and Android browsers
- Optimized touch targets and input handling

## Recent Updates

- Complete styling overhaul with three distinct modes
- Square corners throughout the design
- Custom fonts (Kings, Metamorphous, Times New Roman)
- Greek letter conversion in SPD mode

## Technical Details

- Single-page HTML/CSS/JavaScript application
- No dependencies or frameworks required
- Hosted free on GitHub Pages
- Repository: https://github.com/graymackle/bevlord

## Local Development

1. Open `index.html` in any browser to test locally
2. Make changes to the file
3. Push to GitHub to update the live site:
   ```bash
   cd /c/Users/gmacgillivray/Projects/Bevlord
   git add .
   git commit -m "Description of changes"
   git push
   ```

## Calculation Logic

### Single Item
```
Total with tax = Total Price × (1 + tax rate)
Total deposits = Pack Size × $0.10
Grand total = Total with tax + Total deposits
Cost per beverage = Grand total ÷ Pack Size
```

### Running Total (Combined)
```
1. Sum all original prices (separated by alcoholic/non-alcoholic)
2. Apply appropriate tax to each portion (15% or 7%)
3. Add deposits for all cans ($0.10 × total quantity)
4. Calculate combined price per can across all items
```

Where tax rate is:
- 15% (0.15) for alcoholic beverages (default)
- 7% (0.07) for non-alcoholic beverages (when checkbox is checked)
