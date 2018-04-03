# uk-advisory

Finding UK government political advisors in the absence of an official record

## Sources

- LinkedIn is the primary source for now
  - various scrapers in Python exist, e.g. [here][1] and [here][2]

[1]: https://github.com/junks/linkedInScraper
[2]: https://github.com/eracle/linkedin

- Following the hiQ court case (in which LinkedIn was ordered not to restrict or hinder in any way the collection of data made public through its platform), I don't expect there to be any issue with regards to the collection of this information.
  - [injunction source][3] (PDF)

[3]: https://www.almcms.com/contrib/content/uploads/sites/292/2017/08/HiQInjunction.pdf

## Non-sources

- The government publishes [SpAd data releases][SpAd_data_releases] which are useful but not my focus
  - Another SpAd dataset was put out by the 'The Consitution Unit' at UCL ([Excel spreadsheet available here][SpAd_data_UCL]), from 1979-2013
    - this has been added to the `data` directory for good measure (`spad-public-database.tsv`)
  - data.gov.uk has "[Special Advisers working in the UK Government][SpAd_data_gov]" but it's very poor quantity/quality
- the concept of 'adviser' is somewhat ill defined, hence the lack of standard records
  - Ministries, departments, and government agencies, all tend to have boards with [non-executive directors][NED_wiki], and sometimes advisory boards.
  - Public appointments of this kind are often found on the Cabinet Office [recruitment portal][CO_portal] (but it doesn't seem tied to historical records)
- It's probably possible to obtain these records via FOI requests (but I'm not sure how easy/messy/expensive that would be
- There are also groups whose membership lists are available [here][gov_groups] (but these do not all go back very far historically)

[SpAd_data_releases]: https://www.gov.uk/government/collections/special-adviser-data-releases-numbers-and-costs
[SpAd_data_gov]: https://data.gov.uk/dataset/special-advisers
[SpAd_data_UCL]: https://www.ucl.ac.uk/constitution-unit/research/government/special-advisers
[NED_wiki]: https://en.wikipedia.org/wiki/Non-executive_director
[CO_portal]: https://publicappointments.cabinetoffice.gov.uk/search-appointments/
[gov_groups]: https://www.gov.uk/government/groups

## Approach

- As a first attempt, I'm going to set up a query for the phrase "minister adviser" and limit the results to the UK
  - this will ignore anyone who has left the UK since their time advising in government
  - this will also miss anyone who phrases the same role differently (e.g. adviser at the Ministry of such-and-such)
  - obviously, this will also miss anyone who simply does not use LinkedIn, but there does not seem to be an official record so I'll make do!
- The profile URLs will be collected, from which I should be able to discern the time period in which they were an adviser
  - the next step is then to determine which adviser this corresponds to, which should be possible through Wikipedia/Wikidata

## TODO

- [ ] try out a LinkedIn query tool/scraper
- [ ] sort the results into ministries/departments
  - UCL SpAd database or Wikipedia/Wikidata may provide guidance here
- [ ] map the advisers' time period and department to the sitting minister
- [ ] look at (?) the institution the advisers are currently working at (etc.)
