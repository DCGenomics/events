# About

This is a submission to the [Force 2018 Conference](https://www.force11.org/meetings/force2018) taking place on 11-12 October 2018 in Montreal. It was submitted shortly prior to the submission deadline on May 1, 2018.

# What areas does your talk cover?

- [ ] Research Techniques
- [X] Publishing
- [ ] Data Publishing
- [X] Global Perspectives
- [ ] Research and Schol Comms Policy
- [X] General - Scholarly Communication
- [ ] Other:

# What is the title of your talk?

Research published over the last week

# What is your talk about? (1 paragraph)

*Please supply one paragraph describing your talk and how it relates to the theme of Engagement. (Please also declare any conflicts of interest. )*

With thousands of research publications coming out each day, it is hard to keep or even get an overview. I will provide a guided tour around research from various fields that was published over the week prior to the session, highlighting (i) how to find such publications, (ii) what can be learned from them in such a short time span, (iii) how to engage with them and (iv) lessons that authors, readers, publishers and others involved in scholarly communication can draw from the experience. The talk will be given on the basis of https://github.com/Daniel-Mietchen/events/blob/master/FORCE-2018-research-published-last-week.md .

# Anything else we should know? 

This talk is closely related to the one at https://github.com/Daniel-Mietchen/events/blob/master/FORCE-2018-research-performed-last-week.md on research *performed* last week, and I would have strongly prefered the two to be scheduled back to back in the same room (either before a session covering scholarly communication more broadly, or before a break), but that other submission did not make it into the program.

# Structure of the session

* Why focus on "last week"?
* Which definition of "last week"?
* Research published over *any* week in the past
* Research *formally* published *over the last week*
* Research *informally* published *over the last week*
  - with notes on research *performed* last week

# Query examples

## PubMed/ PMC

* https://www.ncbi.nlm.nih.gov/pubmed/?term=%22last+7+days%22%5BPDat%5D
* https://www.ncbi.nlm.nih.gov/pubmed/?term=%22last+7+days%22%5BEDat%5D
* https://www.ncbi.nlm.nih.gov/pmc/?term=(%22viruses%22%5BMeSH+Terms%5D+OR+%22viruses%22%5BAll+Fields%5D+OR+%22virus%22%5BAll+Fields%5D)+AND+(%222018%2F10%2F03%22%5BPDat%5D+%3A+%222018%2F10%2F10%22%5BPDat%5D)&cmd=DetailsSearch

## Twitter

* keyword search
  - https://twitter.com/search?f=tweets&vertical=default&q=%28%28doi%20AND%2010%29%20OR%20doi.org%20OR%20pmid%20OR%20pmcid%20OR%20pubmed%20OR%20%28ncbi%20AND%20pmc%29%20OR%20arxiv%29%20AND%20%28published%20OR%20new%20OR%20paper%20OR%20journal%20OR%20article%20OR%20preprint%20OR%20today%20OR%20yesterday%20OR%20week%29
    - a Twitter search can be turned into a weighted feed ([example](http://tweetedtimes.com/v/10350))
* lists
  - https://twitter.com/EvoMRI/lists/labwatching
    - a Twitter list can be turned into a weighted feed ([example](http://tweetedtimes.com/v/1065), based on [this list](https://twitter.com/EvoMRI/lists/biodiversity))  
* dedicated accounts  
  - https://twitter.com/arXiv_trend
    - re-use https://www.technologyreview.com/s/612233/the-best-of-the-physics-arxiv-week-ending-october-6-2018/
  - https://twitter.com/ISPM_ZOAP
  - https://twitter.com/sgclabnotebooks

## Google

* via ORCID: https://www.google.com/search?num=100&ei=z4C5W63BPIKCwgSKmZuoCA&q=site%3Aorcid.org+%22oct+2018%22+doi
* Scholar: https://scholar.google.com/scholar?hl=en&as_ylo=2018&as_yhi=2018&q=%22october+2018%22&btnG=

## Plazi

* Today's new taxa: http://tb.plazi.org/GgServer/static/newToday.html

## Wikidata

*Here's the query for research published this week last year. Adapting it to this year is left as an exercise to the reader.*

```SPARQL
SELECT DISTINCT 
?work 
?title 
?date_time 
# ?topiclabel
WHERE {
  VALUES (?earliest) {("2017-10-03T00:00:00Z"^^xsd:dateTime)}
  VALUES (?latest) {("2017-10-10T00:00:00Z"^^xsd:dateTime)}
  ?work wdt:P577 ?date_time .
  hint:Prior hint:rangeSafe true .
  FILTER (?date_time >= ?earliest)
  FILTER (?date_time <= ?latest)
  ?work wdt:P1476 ?title.
  { ?work wdt:P356 [] } UNION { ?work wdt:P698 []} UNION { ?work wdt:P932 []}

#  ?work wdt:P921 ?topic.
#  ?topic rdfs:label ?topiclabel.
#  FILTER(LANG(?topiclabel) = "en").
#  VALUES ?topic { wd:Q11081 wd:Q7892 }

} 
ORDER BY DESC(?date_time)
LIMIT 10000
```

* [Try it!](https://query.wikidata.org/#SELECT%20DISTINCT%20%0A%3Fwork%20%0A%3Ftitle%20%0A%3Fdate_time%20%0A%23%20%3Ftopiclabel%0AWHERE%20%7B%0A%20%20VALUES%20%28%3Fearliest%29%20%7B%28%222017-10-03T00%3A00%3A00Z%22%5E%5Exsd%3AdateTime%29%7D%0A%20%20VALUES%20%28%3Flatest%29%20%7B%28%222017-10-10T00%3A00%3A00Z%22%5E%5Exsd%3AdateTime%29%7D%0A%20%20%3Fwork%20wdt%3AP577%20%3Fdate_time%20.%0A%20%20hint%3APrior%20hint%3ArangeSafe%20true%20.%0A%20%20FILTER%20%28%3Fdate_time%20%3E%3D%20%3Fearliest%29%0A%20%20FILTER%20%28%3Fdate_time%20%3C%3D%20%3Flatest%29%0A%20%20%3Fwork%20wdt%3AP1476%20%3Ftitle.%0A%20%20%7B%20%3Fwork%20wdt%3AP356%20%5B%5D%20%7D%20UNION%20%7B%20%3Fwork%20wdt%3AP698%20%5B%5D%7D%20UNION%20%7B%20%3Fwork%20wdt%3AP932%20%5B%5D%7D%0A%0A%23%20%20%3Fwork%20wdt%3AP921%20%3Ftopic.%0A%23%20%20%3Ftopic%20rdfs%3Alabel%20%3Ftopiclabel.%0A%23%20%20FILTER%28LANG%28%3Ftopiclabel%29%20%3D%20%22en%22%29.%0A%23%20%20VALUES%20%3Ftopic%20%7B%20wd%3AQ11081%20wd%3AQ7892%20%7D%0A%0A%7D%20%0AORDER%20BY%20DESC%28%3Fdate_time%29%0ALIMIT%2010000)
  - visualize results in a word cloud, e.g. via https://www.wordclouds.com/

## Astrophysics Data System

* weekly: myADS Personal Notification Service for arXiv
  - http://adsabs.harvard.edu/myADS/cache/278851069_PRE.html
  - http://adsabs.harvard.edu/myADS/cache/324115336_PRE.html
* daily: RSS feed for the above http://adsabs.harvard.edu/cgi-bin/exec_myads2/all?id=324115336&db_key=DAILY_PRE&rss=2.1

# See also 

* [FORCE-2018.md](FORCE-2018.md)
* [Bims: Biomed news](http://biomed.news/)
* [Today's publications](https://github.com/fnielsen/scholia/issues/513)


# Notes

* Twitter 
  - lists
  - hashtags
  - search
* Google alerts
  - generic search
  - Google Scholar
    - https://scholar.google.ch/scholar_alerts?view_op=list_alerts&hl=en
* library workflows
  - subject librarian/ liaison
  - Discover tools
    - Primo: e.g. https://hollis.harvard.edu/primo-explore/search?vid=HVD2&sortby=rank&lang=en_US
    - Summon: https://syracuse.summon.serialssolutions.com/search?q=test#!/search?ho=t&l=en&q=test 
  - systems librarian
    - PIDs, e.g. ORCID
* RSS
* PubCrawler
* LSHTM
* Not mentioned yet: journal TOC alerts
* Questions
  - gaming the metrics via publication date
  - revert workflows altmetric
  - discovery service
    - primo / 
  - goal post
  - ORCIDSs making things simpler?
    
