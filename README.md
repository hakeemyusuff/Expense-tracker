# Expense Tracker

A command-line application to help manage your finances by allowing users to add, view, and delete expenses. This application is part of the [roadmap.sh backend project](https://roadmap.sh/projects/expense-tracker), designed to build backend skills through practical projects.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Snippets I’m Proud Of](#snippets-im-proud-of)
- [License](#license)

## Overview

The Expense Tracker CLI app allows users to effectively track their expenses by adding, viewing, and deleting expense entries. Built with simplicity in mind, this application is designed to be intuitive, lightweight, and scalable for basic financial tracking needs.

## Features

- Add a new expense with description, amount, and date.
- View a list of all expenses or filter by month.
- Delete expenses based on a unique ID.
- Calculate total expenses, either by a specific month or overall.

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/hakeemyusuff/Expense-tracker.git
   cd Expense-tracker
   ```

2. **Change to executable files:**

    ```bash
    chmod +x ./expense-tracker.py
    ```

3. **To view how to use the program use:**

    ```bash
    ./expense-tracker --help or -h
    ```

## Usage

- **Adding an Expense**

    To add a new expense, use the following command:

    ```bash
    ./expense_tracker.py add --description "Lunch" --amount 12.50 --date "2024-11-11"
    ```

- **Viewing All Expenses**

    To view all recorded expenses, run:

    ```bash
    ./expense_tracker.py list
    ```

- **Viewing Monthly Summary**

    To view a summary of expenses for a specific month, run:

    ```bash
    ./expense_tracker.py summary --month 11
    ```

    Run the above command without the month argument for summary of  all expenses.

- **Deleting an Expense**

    To delete an expense by its ID, use:

    ```bash
    ./expense_tracker.py delete --id 3
    ```

## Snippet I’m Proud Of

 ```python
def calc_summary(month=None):
    data = get_data()
    if month:
        data_list = [row for row in data if get_month(row.get("Date")) == month]
        print(f"# Total expenses for {calendar.month_name[month]}: ${get_sum(data_list)}")
    else:
        print(f"# Total expenses: ${get_sum(data)}")

```