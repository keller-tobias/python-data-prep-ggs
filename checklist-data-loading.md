# Checklist for Data Loading Issues

Use this quick checklist when a dataset won't load. These are the seven most common causes.

## Quick checklist

✅ [Saved the notebook or script](#check-1)<br>
✅ [Notebook/script is inside the project folder](#check-2)<br>
✅ [Using the correct pandas reader for the file type](#check-3)<br>
✅ [For text files: correct delimiter and header](#check-4)<br>
✅ [For Excel: correct sheet, range, and header](#check-5)<br>
✅ [Installed required dependencies (openpyxl/pyarrow)](#check-6)<br>
✅ [Activated the correct virtual environment](#check-7)<br>

## Detailed Checklist

<a id="check-1"></a>

### 1. Have you saved the notebook or script?

Otherwise you may be working in a temporary directory and your relative path might be incorrect.

<a id="check-2"></a>

### 2. Is your notebook or script located in the project directory (or a subfolder)?

Otherwise relative paths might not work as expected.

<a id="check-3"></a>

### 3. Are you using the appropriate function to read the file type?

- `pd.read_csv()` or `pd.read_table()` — text files (CSV/TSV)
- `pd.read_excel()` — Excel files
- `pd.read_parquet()` — Parquet files

<a id="check-4"></a>

### 4. For text files, have you specified the correct delimiter and header?

`pd.read_csv()` and `pd.read_table()` let you specify the delimiter and header row. Check the documentation for details.

<a id="check-5"></a>

### 5. For Excel files, have you specified the sheet name, range, and header?

`pd.read_excel()` lets you specify the sheet name, range, and header row. Check the documentation for details.

<a id="check-6"></a>

### 6. For Excel, Parquet, and other binary formats, have you installed the necessary dependencies?

Install any required libraries, for example:
- Excel: `openpyxl`
- Parquet: `pyarrow`

<a id="check-7"></a>

### 7. Have you selected/activated the correct virtual environment?

You may be using the global environment instead of the project's virtual environment. Activate it before running the notebook, and install project dependencies into that environment (not the global one).
