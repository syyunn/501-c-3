# 501(c)(3)
Information about 501(c)(3) organizations

## Prohibited Political Actions

Prohibited from directly/indirectly participating in, or intervening in, any political campaign on behalf of any candidate for 
elective pulbic office.

https://www.irs.gov/charities-non-profits/charitable-organizations/the-restriction-of-political-campaign-intervention-by-section-501c3-tax-exempt-organizations

## 

```sql
select cd.ld203_uuid, cd.organization_name, cb.contributor_name, p.pac_name, cb.payee_name, cb.amount, cb.recipient_name, cb.contribution_date, cd.report_year, cd.report_period_code, cd.comments 
from relational___campaign.contributiondisclosure cd
	inner join relational___campaign.contributions cb using ("ld203_uuid")
	inner join relational___campaign.pacs p using ("ld203_uuid")
where cb.amount::numeric > 0
order by cb.amount desc
```
