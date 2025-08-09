#### Searching the web:

- abundance of data continuously growing to search from, content appearing and dissapearing,  the search string does not exactly match the text, spam data appearing, hyperlink text corpus of enormous complexity
- goal: identify most relevant pages i.e authorities
- dosent necessarily need to contain search string, or frequency of search string does not reflect relevance cause spam
- assumption: link structure leads to good results cause it is based off of human rating 
- problems: an authority that does not contain the search string will not appear, and frequently hyperlinked pages become authority on any topic
- introducing hubs which are authorities for the authorities

### HITS (hyperlinked-induced topic search) Algorithm
- given is a search query $\theta$ from a broad topic, goal is to find a high priority pages
Compute a basic graph $S_\theta$  with properties
- relatively low in size
- has relevant pages
- has high authority pages
we start with a simple root graph $R_\theta$ with a text based search algorithim where first two properties are met
the probabilty is high that pages that point to $R_\theta$ may contain high authority pages if not $R_\theta$ we extend the graph by the immediate outside neighbours of  $R_\theta$ limiting the set of new entries by  d to keep the size low, we now have the base graph $S_\theta$ 
(the algorithim continued on notes...)


[past paper questions](https://chatgpt.com/share/688e723b-eedc-8005-8e3f-9253215496d3)
