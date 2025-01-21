[![lintr](https://github.com/dfe-analytical-services/explore-education-statistics-analytics/actions/workflows/lintr.yml/badge.svg)](https://github.com/dfe-analytical-services/explore-education-statistics-analytics/actions/workflows/lintr.yml)
[![Dashboard tests](https://github.com/dfe-analytical-services/explore-education-statistics-analytics/actions/workflows/dashboard-tests.yml/badge.svg)](https://github.com/dfe-analytical-services/explore-education-statistics-analytics/actions/workflows/dashboard-tests.yml)

# Explore education statistics analytics 

Analysis of analytics data for our explore education statistics (EES) service, pulling in data from a number of sources to disseminate out. Primarily shared with publishers on the service to understand usage of their content, and with the EES service team for assessing service performance.

There are three main parts to this repository:
1. Ad hoc analysis scripts (`adhoc-scripts/`)
2. Data processing and update pipelines (`data-updates/`)
3. Analytics dashboard (`analytics-dashboard/`)

Guides for each of these are provided in the README files in the respective folders.

### Ad hoc scripts

Assorted collection of scripts used in ad hoc analysis that may or may not be useful and may or may not work.

### Analytics dashboard

There is an R Shiny dashboard that is deployed via the DfE POSIT Connect subscription internally. There are three environments, all accessible to DfE AD:

* Production - https://rsconnect/rsc/ees-analytics/
* Pre-production - https://rsconnect-pp/rsc/ees-analytics/
* Development - https://rsconnect-pp/rsc/dev-ees-analytics/

### Data processing and update pipelines

Code used to extract source data, process it, and save a permanent store for usage by the analytics dashboard.

## Access requirements

To run any of the code in this repo, you may need to contact the maintainers to gain access to the source data:
- Google Analytics (GA) property 
- Google Search Console property (separate to GA!)
- Access to the database where we have a permanent store of analytics data
  
## Contributing

If you want to make edits to the code or run anything locally, start by familiarising yourself with the specific README in the part of the project you're intending to use.

### Flagging issues

If you spot any issues with the application, please flag it in the "Issues" tab of this repository, and label as a bug. Include as much detail as possible to help us diagnose the issue and prepare a suitable remedy.

### Making suggestions

You can also use the "Issues" tab in GitHub to suggest new features, changes or additions. Include as much detail on why you're making the suggestion and any thinking towards a solution that you have already done.

### Navigation

In general all `.R` files will have a usable outline, so make use of that for navigation if in RStudio: `Ctrl-Shift-O`.

### Code styling 

The function `styler::style_dir()` will tidy code according to tidyverse styling using the styler package. Run this regularly as our pre-commit hooks will prevent you committing code that isn't tidied. This function also helps to test the running of the code and for basic syntax errors such as missing commas and brackets.

You should also run `lintr::lint_dir()` regularly as lintr will check all pull requests for the styling of the code, it does not style the code for you like styler, but is slightly stricter and checks for long lines, variables not using snake case, commented out code and undefined objects amongst other things.

### Pre-commit hooks

We have some pre-commit hooks set up to help with code quality and deployment dependencies. These are controlled by the `.hooks/pre-commit.R` file.

## Contact

explore.statistics@education.gov.uk