# MBA-PROJECT-
MBA-Project- three-statement-financial-model
three-statement-financial-model
│
├── README.md
├── financial_model.py
├── assumptions.py
├── requirements.txt
└── data
    └── sample_data.csv
    # Financial Assumptions

revenue_growth_rate = 0.10
cost_of_goods_sold_rate = 0.40
operating_expense_rate = 0.20
tax_rate = 0.25
depreciation = 5000
from assumptions import *

def income_statement(revenue):
    cogs = revenue * cost_of_goods_sold_rate
    gross_profit = revenue - cogs
    operating_expenses = revenue * operating_expense_rate
    ebit = gross_profit - operating_expenses - depreciation
    tax = ebit * tax_rate
    net_income = ebit - tax

    return {
        "Revenue": revenue,
        "COGS": cogs,
        "Gross Profit": gross_profit,
        "Operating Expenses": operating_expenses,
        "EBIT": ebit,
        "Tax": tax,
        "Net Income": net_income
    }


def balance_sheet(cash, assets, liabilities, equity):
    total_assets = cash + assets
    total_liabilities_equity = liabilities + equity

    return {
        "Total Assets": total_assets,
        "Total Liabilities & Equity": total_liabilities_equity
    }


def cash_flow(net_income):
    operating_cash_flow = net_income + depreciation
    investing_cash_flow = -10000
    financing_cash_flow = 5000

    total_cash_flow = operating_cash_flow + investing_cash_flow + financing_cash_flow

    return {
        "Operating Cash Flow": operating_cash_flow,
        "Investing Cash Flow": investing_cash_flow,
        "Financing Cash Flow": financing_cash_flow,
        "Net Cash Flow": total_cash_flow
    }


if __name__ == "__main__":
    revenue = 100000

    income = income_statement(revenue)
    cashflow = cash_flow(income["Net Income"])
    balance = balance_sheet(20000, 50000, 30000, 40000)

    print("Income Statement:", income)
    print("Cash Flow Statement:", cashflow)
    print("Balance Sheet:", balance)
    pandas
numpy
    Income Statement:
Revenue: 100000
COGS: 40000
Gross Profit: 60000
Operating Expenses: 20000
EBIT: 35000
Tax: 8750
Net Income: 26250

