# Integer Overflow Explorer

A small interactive app that shows what happens when a number gets too big to fit in a fixed number of bits.

## Purpose

This app makes integer overflow easier to understand by showing the mathematical answer alongside the value actually stored. You can also see how the same binary pattern represents different numbers depending on whether it is signed or unsigned.

## Features

- Switch between 4-bit and 8-bit numbers.
- Compare unsigned and signed two's complement values.
- Adjust the starting number and how much to add.
- See the binary patterns before and after addition.
- Check whether the result overflows.
- Try the largest allowed value plus one with a single button.

## Run the app

1. Download or clone this repository.
2. Open `index.html` in your browser.

No installation, extra libraries, API keys, or server are needed.

## How it works

A fixed number of bits can only store a limited range of values. The app adds two numbers, keeps the lowest bits, and interprets the result using the selected signed or unsigned mode.

For `n` bits, keeping the lowest bits is equivalent to taking the sum modulo `2^n`.

For example:

- With 8-bit unsigned numbers, `255 + 1` wraps around to `0`.
- In the app's 8-bit signed wrapping model, `127 + 1` becomes `-128`.

The binary display helps explain where those results come from.

## Limitations

This app intentionally simulates fixed-width wrapping. JavaScript's regular number addition does not use 4-bit or 8-bit storage.

Actual overflow behavior depends on the programming language and data type. Signed integer overflow in C and C++ is undefined behavior, so those languages are not guaranteed to produce the signed wrapping results shown here.

This is a learning tool and contains no exploit or attack code.

## Testing

Open the app in your browser and check these examples:

| Bits | Mode     | Calculation | Expected result | Overflow? |
| ---- | -------- | ----------- | --------------- | --------- |
| 8    | Unsigned | 255 + 1     | 0               | Yes       |
| 8    | Signed   | 127 + 1     | -128            | Yes       |
| 4    | Unsigned | 15 + 1      | 0               | Yes       |
| 4    | Signed   | 7 + 1       | -8              | Yes       |
| 8    | Signed   | -1 + 1      | 0               | No        |
| 8    | Unsigned | 10 + 5      | 15              | No        |

Also check that the sliders, dropdowns, example button, and reset button work.

Browser used: chrome

Test results: All six test cases matched the expected results in the table, including the stored values and overflow indicators.

## AI assistance

AI helped generate the app's starting structure and visual format, so that I was able to work on the actual logic and test cases for the application.

See `reflection.md` for more about the workflow and what I learned.
