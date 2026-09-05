# DAX Measures

## Task 1 — Financial
```DAX
Revenue = SUM(financial_health[Revenue])
Gross Profit = [Revenue] - SUM(financial_health[COGS])
Gross Margin % = DIVIDE([Gross Profit], [Revenue])
EBIT = SUM(financial_health[EBIT])
EBIT Margin % = DIVIDE([EBIT], [Revenue])
Net Income = SUM(financial_health[Net Income])
Net Margin % = DIVIDE([Net Income], [Revenue])
Operating Cash Flow = SUM(financial_health[Operating Cash Flow])
Free Cash Flow = [Operating Cash Flow] - SUM(financial_health[Capital Expenditure])
Ending Cash = MAX(financial_health[Cash])
Debt = MAX(financial_health[Debt])
Debt to Cash = DIVIDE([Debt], [Ending Cash])
```

## Task 2 — HR
```DAX
Headcount = CALCULATE(COUNTROWS(hr_employees), hr_employees[Status] = "Active")
Exited Employees = CALCULATE(COUNTROWS(hr_employees), hr_employees[Status] = "Exited")
Turnover Rate = DIVIDE([Exited Employees], COUNTROWS(hr_employees))
Avg Satisfaction = AVERAGE(hr_employees[SatisfactionScore])
Avg Performance = AVERAGE(hr_employees[PerformanceScore])
Total Applicants = SUM(hr_recruitment[Applications])
Total Hires = SUM(hr_recruitment[Hires])
Hire Conversion % = DIVIDE([Total Hires], [Total Applicants])
```

## Task 3 — Real Estate
```DAX
Average Property Price = AVERAGE(real_estate[Price])
Median Property Price = MEDIAN(real_estate[Price])
Average Rental Yield % = AVERAGE(real_estate[RentalYieldPct])
Demand Index = AVERAGE(real_estate[DemandIndex])
Supply Index = AVERAGE(real_estate[SupplyIndex])
Demand Supply Gap = [Demand Index] - [Supply Index]
Average Price per SqFt = DIVIDE(SUM(real_estate[Price]), SUM(real_estate[AreaSqFt]))
High Demand Properties = CALCULATE(COUNTROWS(real_estate), real_estate[DemandIndex] >= 80)
```
