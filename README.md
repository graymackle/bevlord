# Bevlord - Beverage Price Calculator

A simple web-based calculator for determining the true cost per beverage in BC, accounting for taxes and deposit fees.

## Live Site
https://graymackle.github.io/bevlord

## Current Features

### Basic Calculator
- Input total price and pack size
- Calculates cost per beverage including all fees

### BC Tax Calculation
- **Default (unchecked)**: 15% tax for alcoholic beverages
- **Non-Alcoholic checkbox**: 7% tax for sodas and non-alcoholic drinks
- **Deposit fee**: Automatically adds $0.10 per beverage

### Mobile Friendly
- Responsive design works on iPhone Safari and Android browsers
- Optimized touch targets and input handling

## Planned Features (Not Yet Implemented)

- Running total tracker for multiple beverage purchases
- Cost savings analysis/comparisons
- Additional comparison features TBD

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

```
Total with tax = Total Price × (1 + tax rate)
Total deposits = Pack Size × $0.10
Grand total = Total with tax + Total deposits
Cost per beverage = Grand total ÷ Pack Size
```

Where tax rate is:
- 15% (0.15) for alcoholic beverages (default)
- 7% (0.07) for non-alcoholic beverages (when checkbox is checked)
