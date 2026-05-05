# SEO Product Name Optimizer

AI-powered Excel SEO optimization tool for Canadian grocery market — specifically designed for Asian/Chinese food products sold in Canadian retail (T&T, Walmart, Costco, Save-On-Foods).

## Features

- **Upload Excel** (.xlsx / .xls) with B-column (Chinese names) and C-column (original English names)
- **AI-powered analysis** using Google Gemini 3.1 Flash via OpenRouter
- **SEO optimization** with Canadian grocery naming conventions
- **Consistent product family naming** — similar products with different flavors maintain uniform English naming patterns
- **Batch processing** with concurrent API calls
- **Auto-download** optimized results

## Product Family Consistency

The tool maintains **consistent naming across product variants**:

```
Input:
- 香辣味牛肉拉面 → spicy beef ramen noodles
- 麻辣味牛肉拉面 → mala beef ramen noodles
- 原味牛肉拉面 → original beef ramen noodles
```

All three share the same base: `beef ramen noodles`, with only the flavor modifier changing.

## Flavor Modifier Standardization

| Chinese | English |
|---------|---------|
| 原味 / 原汁 | original |
| 香辣 / 辣味 / 微辣 | spicy |
| 麻辣 | mala |
| 特辣 / 超辣 | extra spicy |
| 甜辣 | sweet chili |
| 红烧 | hong shao |
| 卤味 | lu wei |
| 酱香 / 酱汁 | in sauce |

## SEO Naming Conventions

- Lowercase, hyphenated for multi-word compounds
- Format: `[flavor] [product type], [authentic name]`
- Weight/size in parentheses: `(500g)` | `(10 pcs)` | `(1L)`
- Keywords: flavor > product type > brand/region

## Usage

1. Open `index.html` in any modern browser
2. Upload your Excel file (B = Chinese name, C = English name)
3. Click **Start SEO Optimization**
4. Download the optimized Excel when complete

## Excel Format

| Row | B: Chinese Name | C: Original English | D: Optimized English | E: Reason |
|-----|---------------|--------------------|--------------------|-----------|
| 1 | 麻婆豆腐 | Mapo Tofu | mapo tofu, spicy (500g) | Added weight. Standardized format. |
| 2 | 香辣味牛肉拉面 | Spicy Beef Ramen | spicy beef ramen noodles | Lowercase. Consistent base with sibling products. |

## Tech Stack

- Pure HTML/CSS/JS (no build required)
- [SheetJS](https://sheetjs.com/) for Excel parsing
- Google Gemini 3.1 Flash via OpenRouter API

## API Configuration

The tool uses OpenRouter API. Update the `CONFIG` object in `index.html`:

```javascript
const CONFIG = {
    API_URL: 'https://openrouter.ai/api/v1/chat/completions',
    API_KEY: 'your-api-key',
    MODEL: 'google/gemini-3.1-flash-lite-preview',
    MAX_CONCURRENT: 3,
    DELAY_BETWEEN_BATCHES: 500
};
```

## License

MIT
