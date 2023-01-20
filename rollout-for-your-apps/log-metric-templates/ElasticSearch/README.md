To adapt the template for elasticsearch data collection and analysis, the fields to be changed are:

1. accountName: Account Name or Integrator Name configured for Data Source in ISD
2. index: ElasticSearch Index Name
3. filterKey: In the example, the distinguishing element between baseline and canary is pod identifier.
4. responseKeywords: The element in elasticsearch record referring to actual log line. e.g. log, message etc.
