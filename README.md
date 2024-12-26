# Complex Systems Topic Network (ver. December 2024)
## Hiroki Sayama (sayama@binghamton.edu)

<img src="complex-systems-topic-network-rev.png" alt="Complex Systems Topic Network" width=400 align="right" />

This repository provides the data and the Mathematica codes I used to generate the complex systems topic network (as of December 2024), which is a long-overdue update of the [complex systems keyword diagram](https://en.wikipedia.org/wiki/File:Complex_systems_organizational_map.jpg) which I generated back in 2010. In so doing, I have collected information about relevant keywords from the following multiple sources:
   * (a) collective feedback posted on several social media (Twitter/X, Facebook, LinkedIn, etc.; more than 130 responses were received) (e.g., [link](https://x.com/HirokiSayama/status/1605664684962619394))
   * (b) several recent reference books on complex systems- and network science-related topics
   * (c) several online resources on complex systems
   * (d) keyword search hits obtained using [OpenAlex](https://openalex.org/)

The data (a), (b) and (c) were used to incorporate the research community's internal perceptions of the relevant topics, whereas the data (d) was used to obtain more objective measurements from publications made in complex systems science. In (a)-(c), relevant keywords were manually selected and curated by myself. In (d), the keyword search hits were obtained using the OpenAlex API for individual keywords as well as pairs of keywords. The overall relevance of each keyword was characterized by the total search hit multiplied by its [visibility boost](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0038747) when searched together with "complex systems" OR "complexity science".

To improve the quality of network reconstruction, I also went through the entire relevant keyword list and manually curated the possible associations of the pairs of keywords from the viewpoint of complex systems science and engineering. The edge weights between a pair of associated keywords were then calculated according to the OpenAlex search hit of the pair, multiplied by each keyword's relevance values. The four communities of topics were obtained by using the [Louvain method](https://iopscience.iop.org/article/10.1088/1742-5468/2008/10/P10008) with modularity maximization just to aid the visibility and organization. Those communities are visualized with the following colors and can be interpreted roughly as:
   * Orange: Nonlinear dynamics
   * Yellow: Computational modeling
   * Purple: Biological/ecological/evolutionary/learning/social systems
   * Green: Networks and systems

Here are more details of the contents of this repository:
   * all-topics-keywords.txt: master keyword list (sources of information are also indicated in this file)
   * word-analysis-OpenAlex.nb: Mathematica code that reads all-topics-keywords.txt and uses OpenAlex API to generate the following data files:
      - OAcountresultsBaseline.csv: baseline search hit counts of keywords
      - OAcountresults.csv: search hit counts of keywords with "complex systems" OR "complexity science"
      - relevance-scores.csv: relevance scores of keywords
      - OAlinkresults-all-at-once-12142024.csv: search hit counts of pairs of keywords with "complex systems" OR "complexity science"
   * keyword-associations-cleaned.txt: manually curated list of possible keyword associations
   * network-reconstruction-rev.nb: Mathematica code that reads the above data files and generates the following network visualizations:
      - complex-systems-topic-network-rev.png
      - complex-systems-topic-network-rev.pdf
      - complex-systems-topic-network-communities-rev.png
      - complex-systems-topic-network-communities-rev.pdf

Questions? Comments? Email sayama@binghamton.edu
