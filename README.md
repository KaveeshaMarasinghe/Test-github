# Test Automation

This project automates frontend transliteration testing using Python + Playwright.
It reads Singlish inputs and expected Sinhala outputs from an Excel file, runs each test case in the web UI, and writes back:

- `Actual output`
- `Status` (`PASS`, `FAIL`, or `COLLECTED`)

By default, it targets:

- URL: `https://www.pixelssuite.com/chat-translator`
- Excel file: `Assignment 1 - Test cases.xlsx`

## What This Script Does

- Opens the transliteration frontend in Chromium.
- Reads test rows from the Excel sheet.
- Sends each input to the UI and captures generated Sinhala output.
- Compares actual output with expected output (if provided).
- Saves results back into the Excel file.

## Requirements

- Python `3.10+`
- `pip`
- Internet connection (to access the frontend URL)

## Clone and Run (Windows / PowerShell)

```powershell
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>

python -m venv .venv
.venv\Scripts\Activate.ps1

pip install playwright openpyxl
python -m playwright install chromium

python test_automation.py
```

## Useful Run Options

- Run in headless mode:

```powershell
python test_automation.py --headless
```

- Use a different Excel file:

```powershell
python test_automation.py --excel "C:\path\to\your_file.xlsx"
```

- Use a different sheet name:

```powershell
python test_automation.py --sheet "Test cases"
```

- Use a different frontend URL:

```powershell
python test_automation.py --url "https://your-frontend-url"
```

## Output

After execution, the Excel file is updated with output and status columns, and results are saved to the same file unless `--output` is provided.
