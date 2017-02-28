# About Open Print

Open Print is a database of printers, toner and ink available in market.

Welcome contributions, especially the printer brands.

> *note*
>
> This repo is under development and not ready for production

# Data Input

[Google Spreadsheet (temp, view only)][db_spreadsheet]

[db_spreadsheet]: https://docs.google.com/spreadsheets/d/1pn-e6Oy2wYH8X909f_Tvv_CfZfedK1ag0fA9Djn9vY8/edit?usp=sharing

# Data Structure of Printer List

Draft. Start from json:

```js
{ "printers": [
  {
    "brand": "string", // short name (unique in printer brand) of printers
    "model": "string", // unique, FULL model number
    "productName": "string", // optional, used in marketing materials
    "type": "string", // "inkjet", "laser", "dotMatrix", "thermal"
    "barcodes": ["string"], // collection of barcodes in market
    "paperTypes": ["string"], // e.g. A4, A3, etc.
    "cartridges": { // a list of ink available in ink tank of the printer
      "black": ["string"],
      "color": ["string"], // 3-in-1 color cart
      "cyan": ["string"],
      "magenta": ["string"],
      "yellow": ["string"],
      "gray": ["string"],
      "photoBlack": ["string"]
    }, // ink or toner of the printer brand
    "dimensions": {
      "height": "string", // number + unit, e.g. "300 mm"
      "width": "string",
      "depth": "string"
    },
    "tags": ["string"], // tags that can be organized e.g. "digital", "wifi", "fax", "home-use", etc.
    "moreInfo": { // any other information
      "keyName": ["string"] // keyName that can be organized and useful in search
    } // ...
  }
]} // ...
```

```js
{ "inks": [
  {
    "brand": "string",
    "model": "string",
    "productName": "string", // optional, used in marketing materials
    "colors": ["string"], // e.g. "black", "photo black", "yellow", "color" (or "tri-color")
    "capacity": "string", // with unit, printed on the packing, e.g. "8 ml", "~600 pages"
    "forPrinters": ["string"], // printer models shown on the packing
    "barcodes": ["string"],
    "moreInfo": { // any other information
      "keyName": ["string"] // keyName that can be organized and useful in search
    } // ...
  } // ...
]}
```

```js
{ "companies": [
  {
    "brand": "string", // unique, brand identity in market
    "name": "string", // full name of the corporation
    "mainWesite": "string" // url excludes "https://", usually .com
    "otherWebsites": ["string"], // e.g. .com.hk
    "moreInfo": { // any other information
      "keyName": ["string"] // keyName that can be organized and useful in search
    } // ...
  }
]} // ...
```


# Plan

- [ ] Collect printer and ink data. Current model is in priority.
- [ ] Provide user interface for data input
- [ ] Provide api access. Public or registration-based depends on resources.

In long-term, I am open to anything relating to printing in this repo.
