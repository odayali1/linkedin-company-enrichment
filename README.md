# Enrich a company from a LinkedIn company URL

Turn LinkedIn company URLs into account data for CRM and account-based marketing. This example runs **LinkedIn Company Details from URL** and saves the website, industry, employee range, headquarters, locations, specialties, similar companies, and recent posts.

The code in this repository calls a published [Mawsool](https://mawsool.tech) Actor on [Apify](https://apify.com/oday). You use your own Apify token. The run is billed on Apify. Mawsool does not receive your CRM export, only the lookup you submit to the Actor.

**Start on Apify:** [LinkedIn Company Details from URL](https://apify.com/oday/mawsool-linkedin-company-details)

**Talk to Mawsool:** info@mawsool.tech · osama@mawsool.tech · https://mawsool.tech

## How do I run it?

```bash
pip install -r requirements.txt
python enrich.py examples/input.csv --dry-run
set APIFY_TOKEN=your_apify_token
python enrich.py examples/input.csv --out results.json
```

On macOS or Linux, use `export APIFY_TOKEN=your_apify_token`.

Create the token at [Apify integrations](https://console.apify.com/settings/integrations). Use `linkedin.com/company/...` URLs. Profile URLs that contain `/in/` belong in the people examples, not this one.

## What does the CSV look like?

A header named `url` is required.

```csv
url
https://www.linkedin.com/company/example
```

## What do I get back?

Each result row includes `name`, `website`, `industry`, `company_size`, `headquarters`, `organization_type`, `founded`, `followers`, `specialties`, `locations`, `similar_companies`, `employees`, and `recent_updates`. The `employees` list is the people shown on the company page. It is not a full employee directory and it does not include email addresses or phone numbers.

For a large file, use the same input with [Mass LinkedIn Company Scraper](https://apify.com/oday/mawsool-mass-linkedin-company-scraper). Set `resumeId` to continue a stopped run.

## How much does it cost?

Company details start at **$2.00 per 1,000** company URLs on the Free plan. Bronze is $1.80, Silver is $1.60, and Gold, Platinum, and Diamond are $1.30 per 1,000. The mass Actor uses the same price. The current price is always on the Actor page. Paid Apify plans receive the plan discount shown there.

`cost = rows processed × your plan price per row`.

## Which Mawsool Actor should I use?

- [Email to LinkedIn Finder](https://apify.com/oday/mawsool-email-linkedin-lookup)
- [LinkedIn Profile Finder by Name & Company](https://apify.com/oday/mawsool-linkedin-profile-finder)
- [LinkedIn Profile Details from URL](https://apify.com/oday/mawsool-linkedin-profile-details)
- [Mass LinkedIn Profile Scraper](https://apify.com/oday/mawsool-mass-linkedin-profile-scraper)
- [LinkedIn Current Company Checker](https://apify.com/oday/mawsool-linkedin-company-checker)
- [LinkedIn Job Change Detector](https://apify.com/oday/mawsool-linkedin-job-change-watch)
- [LinkedIn Company Details from URL](https://apify.com/oday/mawsool-linkedin-company-details)
- [Mass LinkedIn Company Scraper](https://apify.com/oday/mawsool-mass-linkedin-company-scraper)

## Related example clients

- [linkedin-email-to-profile](https://github.com/odayali1/linkedin-email-to-profile)
- [find-linkedin-profile-by-name](https://github.com/odayali1/find-linkedin-profile-by-name)
- [linkedin-job-change-checker](https://github.com/odayali1/linkedin-job-change-checker)

## Does this repository include Mawsool's data service?

No. This is an open-source example of how to start the public Actor and save the dataset. The Actor page is the product. For a data partnership, email info@mawsool.tech or osama@mawsool.tech.
