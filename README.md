##IT23310582 - Fernando H.G
# Assignment 1 – Transliteration Accuracy Testing
## IT3040 – IT Project Management | BSc (Hons) in Information Technology – Year 3

This project automates the testing of the **Chat Sinhala transliteration** function available at:
[https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

It uses **Playwright** (via Python) to input 50 chat-style Singlish test cases and capture the actual Sinhala output, then records the results in an Excel file.

---

## Project Structure

```
test_automation/
├── test_automation.py          # Main Playwright automation script
├── Assignment 1 - Test cases.xlsx  # Excel file with test cases and results
├── Commands.txt                # Quick reference commands
└── README.md                   # This file
```

---

## Prerequisites

- Python 3.11 or 3.12
- Google Chrome (recommended) — or Playwright will install Chromium automatically
- Internet connection (the script accesses a live website)

---

## Installation (One-Time Setup)

Open **Command Prompt** and navigate to the project folder:

```bash
cd /d D:\test_automation
```

Then run the following commands one by one:

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## Running the Tests

From the `test_automation` folder in Command Prompt, run:

```bash
python test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Command Arguments Explained

| Argument | Description |
|---|---|
| `--excel` | Path to the Excel file containing test cases |
| `--url` | URL of the chat translator application |
| `--wait-ms` | Milliseconds to wait after typing before reading output (default: 5000) |
| `--type-delay-ms` | Delay between keystrokes in milliseconds (default: 80) |
| `--slow-mo-ms` | Slow motion delay for browser actions (default: 200) |
| `--save-every` | Save Excel file after every N tests (1 = save after each test) |
| `--keep-open` | Keep the browser open after all tests complete |
| `--headless` | Run browser without UI (optional, not recommended for this assignment) |

---

## Checking Results

After the script finishes:

1. Open `Assignment 1 - Test cases.xlsx`
2. Check the **Actual output** column (column E) — populated automatically by the script
3. Check the **Status** column (column F) — `PASS` or `FAIL` set automatically by comparing actual vs expected output

---

## Test Case Summary

- **Total test cases:** 50 (all negative — cases where the system fails)
- **TC ID format:** `Neg_0001` to `Neg_0050`
- **Input length types:** S (≤30 chars), M (31–299 chars), L (300–450 chars)
- **Singlish input types covered:** All 24 types from Appendix 1

### Input Types Covered

| # | Input Type |
|---|---|
| 1 | Question forms |
| 2 | Command forms |
| 3 | Greetings |
| 4 | Requests |
| 5 | Responses |
| 6 | Repeated Words |
| 7 | Inputs with Punctuation Marks |
| 8 | Romanization / Spelling Variants |
| 9 | Isolated English Word Insertions in Singlish |
| 10 | Multi-Word English Phrases in Singlish |
| 11 | English Digital Terms in Singlish |
| 12 | Platform/App Names in Singlish |
| 13 | English Abbreviations/Acronyms in Singlish |
| 14 | English Clipped Forms in Singlish |
| 15 | Place Names Embedded in Singlish |
| 16 | Person Names Embedded in Singlish |
| 17 | Inputs with Numbers and Numeric Suffixes |
| 18 | Inputs with Currency |
| 19 | Inputs with Time Formats |
| 20 | Inputs with Dates |
| 21 | Inputs with Unit of Measurements |
| 22 | Inputs with Slang and Casual Phrasing |
| 23 | Online Identifiers in Singlish |
| 24 | Inputs Containing Emojis |

---

## Notes

- The script only tests the **Chat Sinhala** transliteration function.
- Standard Sinhala, backend APIs, performance, scalability, and security testing are **out of scope**.
- All 50 test cases are **negative** (expected to fail transliteration).
- Do not manually edit the **Actual output** or **Status** columns — these are filled automatically.
