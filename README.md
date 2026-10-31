# CSV Analyzer Skill

An instruction-based Codex skill for inspecting CSV files and producing concise data-quality and descriptive-statistics reports. Useful for checking sales exports, reviewing datasets before analysis, and validating test data.

## Features

- Report row counts, column names, and data types.
- Count missing values and their percentage in each column, with an explicit missing-value rule.
- Detect duplicate rows across all columns, or use user-specified columns.
- Summarize numeric columns with counts, means, sample standard deviations, ranges, and quartiles.
- Summarize non-numeric columns with counts, unique values, and most frequent values.

Calculations ignore missing values and retain duplicate rows. The skill does not fill missing values, remove duplicates, or modify source files. Its instructions and default report language are Chinese. This project contains instructions and sample data, not a standalone analysis program.

## Install in Codex

For project-local use, open this project in Codex. The skill is already located at `.agents/skills/csv-analyzer-skill/SKILL.md`.

To use it in another project, copy the entire `csv-analyzer-skill` folder into that project's `.agents/skills/` directory. For availability across projects, place the folder in `~/.agents/skills/` instead.

Codex detects local skills automatically. If the skill does not appear, restart Codex. In the CLI or IDE extension, use `/skills` or type `$` to select it. See the [official Codex skills documentation](https://learn.chatgpt.com/docs/build-skills) for discovery and installation details.

## Usage

With this project open in Codex, send:

```text
Use $csv-analyzer-skill to analyze examples/sales.csv.
Report the dataset size, missing values, duplicate rows, and descriptive statistics.
Do not modify the CSV file.
```

The included `examples/sales.csv` contains 20 sales records, two missing fields, and two duplicate rows beyond their first occurrences. Its columns are `订单ID` (order ID), `产品` (product), `数量` (quantity), `单价` (unit price), and `销售额` (sales amount).

## Project Structure

```text
csv-analyzer-skill/
├── .agents/
│   └── skills/
│       └── csv-analyzer-skill/
│           └── SKILL.md   # Skill metadata and analysis workflow
├── examples/
│   └── sales.csv          # Sample dataset with intentional data-quality issues
├── .gitignore
└── README.md
```
