# links
https://www.taxexemptworld.com/organization.asp?tn=2371103

# 501(c)(3)
Information about 501(c)(3) organizations

## Prohibited Political Actions

Prohibited from directly/indirectly participating in, or intervening in, any political campaign on behalf of any candidate for 
elective pulbic office.

https://www.irs.gov/charities-non-profits/charitable-organizations/the-restriction-of-political-campaign-intervention-by-section-501c3-tax-exempt-organizations

## 
As with the following query you can check, top three payee are are all 501(c)(3) organizations 

- Barack Obama Foundation
- WorkingNations - JaneOates
- WITA ( Washington International Trade Foundation)


```sql
select cd.ld203_uuid, cd.organization_name, cb.contributor_name, p.pac_name, cb.payee_name, cb.amount, cb.recipient_name, cb.contribution_date, cd.report_year, cd.report_period_code, cd.comments 
from relational___campaign.contributiondisclosure cd
	inner join relational___campaign.contributions cb using ("ld203_uuid")
	inner join relational___campaign.pacs p using ("ld203_uuid")
where cb.amount::numeric > 0
order by cb.amount desc
>>>
Boeing Company	Self	The Boeing Company Political Action Committee	Barack Obama Foundation	$9,999,999.00	Barack Obama - Obama Presidential Center - NOTE - Contribution was $10,000,000.00.  The form will not accept $10,000,000.00 - - -  LRC staff said to record the highest amount the form will accept.	2018-12-11	2018	YY
Goodwill Industries International, Inc.	Self		Hyatt; Washington, DC	$8,642,017.00	Jane Oates	2011-04-11	2011	MM
BOEING COMPANY	Self		Washington International Trade Foundation	$7,000,000.00	Rep. Kevin Brady, Rep. Joseph Crowley.	2009-07-22	2009	YY
BOEING COMPANY	Self	The Boeing Company Political Action Committee	Washington International Trade Foundation	$7,000,000.00	Rep. Kevin Brady, Rep. Joseph Crowley.	2009-07-22	2009	YY
BOEING COMPANY	Self	United Space Alliance Political Action Committee (USAPAC)	Washington International Trade Foundation	$7,000,000.00	Rep. Kevin Brady, Rep. Joseph Crowley.	2009-07-22	2009	YY
```
