# Data dictionary

One record per customer. Survey characteristics are measured at the start of
the campaign; all history variables are measured before treatment assignment.
`30d` means 30 days and `90d` means 90 days. These baseline windows end immediately
before assignment. The campaign outcome window is the following 30 days.

| Variable | Meaning | Values / units |
|---|---|---|
| CustomerID | Artificial customer identifier | HG00001-HG10000; not a quantitative predictor |
| Age | Customer's age at assignment | Whole years, 18-80 |
| HouseholdIncome | Annual household income reported in the panel survey | Dollars; blank if missing |
| HouseholdSize | People living in the household, including the customer | Integer, 1-6 |
| ChildrenAtHome | Children living in the household | Integer, 0 through HouseholdSize minus 1 |
| Homeowner | Household owns its primary residence | 1 = owns; 0 = does not own |
| Region | US region of residence | Northeast, Midwest, South, West |
| Education | Customer's highest completed education | High school or less; Some college/associate; Bachelor's; Graduate |
| HomeSizeSqFt | Floor area of primary residence from the survey | Square feet; blank if missing |
| SiteVisits30d | Website sessions in the 30 days before assignment | Nonnegative integer |
| ProductViews30d | Product-page views in the same prior 30 days | Nonnegative integer; repeated views count |
| DaysSinceLastVisit | Days since the most recent website session at assignment | Whole days; 0 means less than one day; over 30 when SiteVisits30d = 0 |
| EmailEngagement90d | Fraction of prior marketing emails with at least one click in the preceding 90 days | 0-1; all panel members received at least one prior email |
| PreviousSpend | Total spending at this retailer in the 12 months before assignment | Dollars |
| Treatment | Random assignment to the campaign email | 1 = assigned email; 0 = no campaign email |
| Conversion | Made at least one purchase in the 30 days after assignment | 1 = purchased; 0 = did not purchase |
| CampaignSpend | Total spending at this retailer in those same 30 days | Dollars; 0 for nonconverters; positive for converters |

Treatment records assignment, not whether the customer opened or clicked the
new email. EmailEngagement90d refers only to **earlier** messages. Conversion and
CampaignSpend are measured after assignment. PreviousSpend is historical and
does not include CampaignSpend.
