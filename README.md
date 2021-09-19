# When expertise gone missing: uncovering the loss of prolific contributors in Wikipedia

Source code for the paper accepted at ```ICADL,2021```. The work is contributed by Paramita Das, Bhanu Prakash Reddy, Debajit Chakraborty, Soumya Sarkar and Animesh Mukherjee.

## Overview - The abstract
Success of planetary-scale online collaborative platforms such as Wikipedia is hinged on active and continued participation of its voluntary contributors. The phenomenal success of Wikipedia as a valued multilingual source of information is a testament to the possibilities of collective intelligence.
Specifically, the sustained and prudent contributions by the experienced prolific editors play a crucial role to operate the platform smoothly for decades. However, it has been brought to light that growth of Wikipedia is stagnating in terms of the number of editors that faces steady decline over time. This decreasing productivity and ever increasing attrition rate in both newcomer and experienced editors is a major concern for not only the future of this platform but also for several industry-scale information retrieval systems such as Siri, Alexa which depend on Wikipedia as knowledge store. In this paper, we have studied the ongoing crisis in which experienced and prolific editors withdraw. We performed extensive analysis of the editor activities and their language usage to identify features that can forecast em prolific Wikipedians, who are at risk of ceasing voluntary services. To the best of our knowledge, this is the first work which proposes a scalable prediction pipeline, towards detecting the prolific Wikipedians, who might be at a risk of retiring from the platform and, thereby, can potentially enable moderators to launch appropriate incentive mechanisms to retain such `would-be missing' valued Wikipedians.

The paper can be accessed here - ```TODO-ADD PAPER LINK```

## List of Active and Missing Editors
As mentioned in our work we have collected 1146 unique missing editors who have not edited in the year 2020 and 2569 active editors who are still active, and editing on different articles. The list of missing editors can be accessed [here](https://github.com/debajit15kgp/Missing-Active-Wikipedians/blob/main/data/missing_editors.json) and active editors [here](https://github.com/debajit15kgp/Missing-Active-Wikipedians/blob/main/data/active_editors.json)

## Feature Table Description
### Activity Features

<h4 align="center">

<table>
    <thead>
        <tr>
            <th>Feature Names</th>
            <th>Division of Features</th>
            <th>Aliases</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=4>Count of edits in different namespaces of Wikipedia</td>
            <td>Article pages- main (namespace 0)</td>
            <td>F1</td>
        </tr>
        <tr>
            <td>Article talk pages (namespace 1)</td>
            <td>F2</td>
        </tr>
        <tr>
            <td>Administrative main pages- Wikipedia (namespace 4)</td>
            <td>F3</td>
        </tr>
        <tr>
            <td>Administrative main pages- Wikipedia talk (namespace 5)</td>
            <td>F4</td>
        </tr>
        <tr>
            <td rowspan=2>Count of edits in major and minor categories</td>
            <td>major edits</td>
            <td>F5</td>
        </tr>
        <tr>
            <td>minor edits</td>
            <td>F6</td>
        </tr>
        <tr>
            <td rowspan=4>Average length of the edits added/deleted (in bytes)</td>
            <td>edits added in major edits</td>
            <td>F7</td>
        </tr>
        <tr>
            <td>edits deleted in major edits</td>
            <td>F8</td>
        </tr>
        <tr>
            <td>edits added in minor edits</td>
            <td>F9</td>
        </tr>
        <tr>
            <td>edits deleted in minor edits</td>
            <td>F10</td>
        </tr>
        <tr>
            <td rowspan=2></td>
            <td>Span (in months) to complete latest contributions</td>
            <td>F11</td>
        </tr>
        <tr>
            <td>ORES score of the edits</td>
            <td>F12</td>
        </tr>
    </tbody>
</table>

### Quality Features
- Count of reverted edits 				
- Admin score of an editor

### Linguistic Features
- Distribution of different POS Tags
- Distribution of different Empath categories
- Sentence vector

### Feature groups with Aliases
<table>
    <thead>
        <tr>
            <th>Feature Group</th>
            <th>Aliases</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Activity Features</td>
            <td>G1</td>
        </tr>
        <tr>
            <td>POS Tags + Empaths</td>
            <td>G2</td>
        </tr>
        <tr>
            <td>Sentence Vector</td>
            <td>G3</td>
        </tr>
        <tr>
            <td>Admin score</td>
            <td>G4</td>
        </tr>
        <tr>
            <td>Count of reverts</td>
            <td>G5</td>
        </tr>
    </tbody>
</table>

## Feature Collection Methods
We have used crawlers on the following pages and used the following API's for making our dataset.
- [XTools API](https://www.mediawiki.org/wiki/XTools/API)
- [Sample Yearly edit counts of editors](https://xtools.wmflabs.org/api/user/month_counts/enwiki/Jimbo_Wales)
- [Non-automated Edits and Activity features](https://xtools.wmflabs.org/api/user/nonautomated_edits/en.wikipedia/Jimbo_Wales/all)
- Quality Features
    - [Admin score](https://xtools.readthedocs.io/en/3.1.6/tools/adminscore.html)
    - [Reverts](https://xtools.wmflabs.org/topedits/en.wikipedia.org/Majorly/0/Cheadle_Hulme)
- [Linguistic Features-Example of talk page](https://en.wikipedia.org/wiki/User:Majorly)

## Citation
Please consider citing this project in your publications if it helps your research.
```TODO-ADD CITATION```
