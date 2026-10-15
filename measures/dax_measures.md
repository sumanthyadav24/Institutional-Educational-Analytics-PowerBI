# DAX Measures

This file lists all custom DAX formulas used in the Power BI dashboard.

## Calculated Table

**DepartmentList** (bridge table to resolve many-to-many relationships)

```
DepartmentList = DISTINCT(Faculty[Department])
```

## Measures

**Total Students**
```
Total Students = COUNTROWS('Admissions')
```

**Total Revenue**
```
Total Revenue = SUM('Fee_Transactions'[Amount_Paid_INR])
```

**Pending Fees**
```
Pending Fees = SUM('Fee_Transactions'[Amount_Pending_INR])
```

**Collection Rate %**
```
Collection Rate % = DIVIDE([Total Revenue], [Total Revenue] + [Pending Fees], 0)
```

**Average GPA**
```
Avg GPA = AVERAGE('Student_Performance'[GPA])
```
