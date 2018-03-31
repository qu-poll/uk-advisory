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

- The only relevant result on data.gov.uk is for SpAds ("[Special Advisers working in the UK Government][SpAd_data_gov]") and the quantity/quality is poor (I would go so far as to say useless)
  - A better dataset was put out by the 'The Consitution Unit' at UCL ([Excel spreadsheet available here][SpAd_data_UCL]), from 1979-2013

[SpAd_data_gov]: https://data.gov.uk/dataset/special-advisers
[SpAd_data_UCL]: https://www.ucl.ac.uk/constitution-unit/research/government/special-advisers

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
