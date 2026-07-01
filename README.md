# Monthly Budget Tracker — Mobile-Native Google Sheets System

A fully automated, mobile-first personal finance tracker built entirely within the Google Sheets mobile app.

## Overview

This tracker solves the common problem of desktop-oriented budget templates being unusable on mobile. It was conceptualized, designed, built, and tested entirely on a phone, using a single transaction ledger as the source of truth for all derived dashboard elements — income, balance, savings, and visualizations.

## Architecture

- **Transaction Ledger:** A single table logging date, category, and amount for every entry. All other components read from this ledger.
- **Historical Income Log:** A secondary table storing income by month, referenced to keep the dashboard's income figure current.
- **Dashboard Layer:** Monthly Income, Remaining Amount, Days Left, Savings Goal Progress, and two pie charts — all formula-driven and updated live as entries are logged.

---

## Automation Logic

- **Monthly Income Sync:** Automatically updates on the 1st of each month by referencing the historical income log against the current date.
- **New-Month Prompting:** If income for the new month hasn't been entered yet, the dashboard displays a contextual prompt (e.g., "Add June Income") instead of an empty or broken value.
- **Days Left Counter:** Calculates days remaining in the current month live, using `TODAY()`.
- **Savings Tracking:** Any ledger entry categorized as "Savings" is automatically aggregated toward a user-defined yearly goal, with progress shown via an in-cell `SPARKLINE` bar and a dynamic status message.

## Usage

1. Copy the spreadsheet to your own Google Drive.
2. Add current and upcoming month's income to the Historical Income Log.
3. Set a Yearly Savings Goal.
4. Log transactions in the ledger, using the category "Savings" for savings entries.
5. View live updates to income, balance, days left, and savings progress on the dashboard.
6. Use the month-selector dropdown to review spending breakdowns for any past month.

LINK: https://docs.google.com/spreadsheets/d/1B0MSAH_YPNHZi7WpXXWOTOiCPoLUq5wQ/edit?usp=drivesdk&ouid=112301417908589440906&rtpof=true&sd=true
