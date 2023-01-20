To adapt the template for stackdriver data collection and analysis, the fields to be changed are:

1. accountName: Account Name or Integrator Name configured for Data Source in ISD
2. filterKey: In the example, the distinguishing element between baseline and canary is pod identifier.
3. responseKeywords: The element in stackdriver record referring to actual log line. e.g. textPayload, log, message etc.
