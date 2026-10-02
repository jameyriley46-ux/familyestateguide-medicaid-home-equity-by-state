# Medicaid Home Equity and Estate Recovery Reach by State: Senior Home Values vs. the 2026 Federal Limits

For 50 states + DC: how each state defines the 'estate' Medicaid can recover from (FEG statute research with confidence codes) and how senior-owned home values (ACS 2024 PUMS) compare with the 2026 federal home-equity limits of $752,000 and $1,130,000.

**Live page:** https://familyestateguide.com/estate-planning-data/medicaid-home-equity-by-state/  
**Publisher:** Family Estate Guide (https://familyestateguide.com)  
**Version:** 1.0.0 (2026-10-02)  
**License:** CC BY 4.0 (data). See LICENSE.

> Not legal, tax, financial or medical advice. Figures are estimates with sampling error; legal rules change. Verify anything important with the original source or a qualified professional.

## Files

| File | Rows | Contents |
|---|---|---|
| `data/medicaid-home-equity-by-state.csv` | 51 | 51 rows (50 states + DC). |
| `data/pums_senior_home_stats.csv` | 52 | 52 rows: 51 states + DC by FIPS code, plus a US row. Underlying PUMS statistics. |

Blank cells mean not available, not published or not applicable; they are never zero.

## Data dictionary

### `data/medicaid-home-equity-by-state.csv`

| Column | Description |
|---|---|
| `state` | State name (50 states + District of Columbia; some files add a United States row). |
| `abbr` | Two-letter USPS state abbreviation (US = national row). |
| `estate_definition` | How the state defines the estate subject to Medicaid estate recovery: 'Probate only', 'Expanded ...' (reaches some non-probate assets), or 'Not verified'. |
| `estate_definition_cite` | Statute or regulation citation for the estate definition. |
| `estate_definition_conf` | Confidence code. A = official current text read; B = official source read indirectly or an older official release; C = secondary source only; U = not verified. |
| `estate_definition_note` | Notes on scope, effective dates or why the rule was not verified. |
| `median_home_value_65plus_owners_2024` | Weighted median owner-reported home value (VALP), owner-occupied units with householder 65+, USD, ACS 2024 1-year PUMS. |
| `pums_sample_units` | Unweighted PUMS sample size (housing units) behind the state's statistics. |
| `pct_65plus_owners_free_and_clear` | Share of those homes owned free and clear (TEN = 2), %. |
| `pct_senior_homes_valued_over_752k` | Share valued above $752,000 (2026 federal minimum home-equity limit), %. |
| `pct_valued_over_1m` | Share valued above $1,000,000, %. |
| `pct_valued_over_1130k` | Share valued above $1,130,000 (2026 federal maximum home-equity limit), %. |
| `pct_between_1m_and_1130k` | pct_valued_over_1m minus pct_valued_over_1130k, percentage points. |
| `median_home_share_in_recoverable_estate` | Rule-based statement (not a computed average) of how much of a typical senior home could fall in the recoverable estate, given estate_definition. |

### `data/pums_senior_home_stats.csv`

| Column | Description |
|---|---|
| `fips` | Two-digit state FIPS code (US = national). |
| `sample_units` | Unweighted PUMS sample (housing units, householder 65+, owner-occupied, VALP > 0). |
| `weighted_units` | Weighted count of those housing units (sum of WGTP). |
| `median_value_65plus_owner` | Weighted median VALP, USD. |
| `pct_free_and_clear` | Weighted share owned free and clear, %. |
| `pct_over_752k` | Weighted share with VALP > $752,000, %. |
| `pct_over_1m` | Weighted share with VALP > $1,000,000, %. |
| `pct_over_1130k` | Weighted share with VALP > $1,130,000, %. |

## Sources

- Family Estate Guide statute/regulation research on state Medicaid estate-recovery definitions (October 2026). Compiled data; underlying law is public.
- U.S. Census Bureau, ACS 2024 1-year Public Use Microdata Sample (PUMS) via https://api.census.gov/data/2024/acs/acs1/pums (VALP, WGTP, TEN; RELSHIPP = 20 householder, AGEP 65-99, TEN 1-2). Public domain.
- Federal 2026 home-equity limits ($752,000 minimum / $1,130,000 maximum) under 42 U.S.C. 1396p(f), as published by CMS (2026 SSI and Spousal Impoverishment Standards; figures confirmed via New York DOH GIS 26 MA/03 because the CMS PDF could not be downloaded). U.S. government facts, public domain.

## Methodology

- PUMS: one record per housing unit (householder 65+, owner-occupied); weighted by WGTP; median is the weighted 50th percentile.
- Estate definitions were coded from official statute/regulation text where it could be read, with A/B/C/U confidence codes.

## Limitations

- UNVERIFIED LEGAL RULES: estate definition is coded U (not verified) for 28 jurisdictions: AL, AK, AZ, AR, CO, CT, DE, DC, FL, HI, IL, IN, LA, MD, MI, MO, NJ, NM, NY, ND, OK, PA, SD, TN, TX, UT, VT, WV. 'Expanded' on paper does not mean a state pursues every non-probate asset in practice.
- Value is not equity: VALP is self-reported value, top-coded and rounded; with a mortgage, equity is lower. The free-and-clear share is shown so users can judge this.
- PUMS estimates carry sampling error with no MOE published here; DC and small states are noisy.
- Only homes where the 65+ person is the householder are counted.
- Which states elected the higher home-equity limit is NOT in this release (see Rights exclusions). Not legal, tax, financial or medical advice. Figures are estimates with sampling error; legal rules change. Verify anything important with the original source or a qualified professional.

## Rights review and exclusions

Family Estate Guide publishes here only its own compiled data and U.S. government public-domain data (Census, BLS, CMS, DOL), plus third-party data that is under CC BY or a compatible open license, with attribution. Third-party copyrighted or non-commercial-licensed data is excluded.

- Removed `home_equity_limit_tier`, `home_equity_limit_2026`, `limit_note` and `median_as_pct_of_limit`. The state-by-state limit election in the live page was taken from KFF's 2025 Medicaid eligibility survey table and Justice in Aging's 2026 list (both copyrighted, no open license), and the official CMS documents could not be retrieved to confirm it. Columns that only use the federal $752,000 / $1,130,000 thresholds are kept.
- The live page's citations to Justice in Aging and MassHealth in one note (Massachusetts effective date) are kept as citations only; no JIA data is reproduced.

## How to cite

Family Estate Guide (2026). *Medicaid Home Equity and Estate Recovery Reach by State: Senior Home Values vs. the 2026 Federal Limits* (Version 1.0.0) [Data set]. https://familyestateguide.com/estate-planning-data/medicaid-home-equity-by-state/ . GitHub: https://github.com/jameyriley46-ux/familyestateguide-medicaid-home-equity-by-state

A Zenodo DOI will be added here once version 1.0.0 is released and archived. Machine-readable citation: `CITATION.cff`.

Please link to the live page when you use the data.

## License

Data in this repository is licensed under the Creative Commons Attribution 4.0 International license (CC BY 4.0). Underlying U.S. government data is public domain; third-party CC BY data keeps its original attribution requirements (see Sources).
