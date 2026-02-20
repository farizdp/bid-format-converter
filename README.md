# BID Format Converter

A lightweight, single-file web tool for formatting data entries used in BID systems. It zero-pads numbers to 8 digits, lowercases text, and wraps each line in single quotes — ready to paste into queries or config files.

## Features

- **Real-time formatting** — output updates as you type
- **Copy to clipboard** — one-click copy button
- **Responsive layout** — side-by-side panels on desktop, stacked on mobile
- **Zero dependencies** — just a single `index.html` file

## How It Works

Each input line is processed with the following rules:

| Input type | Rule | Example |
|---|---|---|
| Number (digits only) | Zero-padded to 8 digits, wrapped in single quotes | `123` → `'00000123'` |
| Text | Converted to lowercase, wrapped in single quotes | `Hello World` → `'hello world'` |

Lines are joined with commas so the output is ready to drop into an `IN (...)` clause or similar list.

## Usage

Open `index.html` in any browser. No build step or server required.

## Example

**Input:**
```
123456
Netflix 89000
Amazon Prime VIDEO
1
```

**Output:**
```
'00123456',
'netflix 89000',
'amazon prime video',
'00000001'
```
