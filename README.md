# Dash Visualizations of ICD 11 Network Data

This summer, I interned at NIH's Big Data 2 Knowledge Center at UCLA. My research lab’s work consisted of working with WHO’s International Classification of Diseases 11 (ICD 11) data to create a web application which can be used by medical professionals for further analysis.  This project’s main goal is to further ICD 11’s purpose, which is to “[provide] a common language that allows health professionals to share health information across the globe”. I was excited to join this project because aside from the glamorous world of consumer tech products, I am extremely hopeful of the technology's potential in the field of healthcare. Coming from India, where healthcare services are inadequate for millions of people in the country, I feel a personal connection to the advancement of healthcare technology and was eager to learn more about the current landscape of disease research and contribute to furthering research efforts

## The Question

So why is this all important? Well, we can answer a number of questions using graph data that could provide interesting insight into disease relationships. For example, if a node, say stomach pain is common to two other disease nodes, can medical professionals use that information to identify patterns? Can we train machine learning models to pick up these patterns and help disease diagnoseis? These are very promising questions and highlight the potential of network graphs.

## The Data

ICD 11 data is in the form of a network graph, which is very similar to that of a binary tree. In ICD 11, there are 26 “roots”, or 26 base diseases and defects.  Each of these 26 root nodes has several levels, with each level containing multiple nodes that “descend” from the root node. Each node apart from the “leaf” or lowermost node has “edges” that connects it to other nodes. Additionally, each root had its own subtree, with all the subtrees connected together through a common "ICD 11" Node that we created

The purpose of the network graph data structure and node attributes is to allow the user to better understand disease causes and relationships that fall under a larger category. For example, the node “External Causes of Morbidity and Mortality has several children, one of them being “Unintentional land transport road traffic injury event”. 

## Tree Creation and Data Manipulation

My work on ICD 11 Data was done using Python and Jupyter Notebook. To create a network graph, I first studied network structures and algorithms and trained myself in NetworkX, a Python package meant specifically for creating, manipulating and investigating network data. When creating nodes, I preserved the attributes of the nodes, namely ID, Title, Children, and Parents, which was saved as a Python dictionary in NetworkX. 

![Tree Creation](https://github.com/kevinchen27/dash-visualizations/blob/master/tree%20creation.png)

The network trees were appended to a list. My next step was to extract the number of levels and the number of nodes per level in each tree. In addition, I also created a separate data.frame which sums the total number of nodes under each root disease. Both these data sets were exported as CSV files so that they can be used to create visualizations. Another question I wanted to explore that could prove useful was the number of nodes shared by two root diseases. This is another piece of information that could help researchers explore disease relationships. 

![Disease Depth](https://github.com/kevinchen27/icd11-dash-visualizations/blob/master/nodes%20per%20level.png)

## Visualizations with Dash

Dash is a dashboard visualization module by Plotly. Dash incorporates HTML and CSS components but in a Python-friendly manner which doesn’t require knowledge of the former. Its advantage over other Python visualization libraries like Plotly and Matlpotlib is that Dash enables you to create interactive graphics which can be integrated with Flask for a web application. Dash also requires the server to always be running so that visualizations can be updated according to the user's choice of selection. If there's one thing I learned from Dash's tutorials: you don't have to be an expert in memorizing Dash, but its more important to be an expert in looking up its documentation!

One of the dashboards I created was a bar plot which shows the number of nodes per level for a selected root. As mentioned, the fun part about Dash is you can update the graph according to your choice, hence the implementation of a dropdown menu for my barplot that allows you to select which root tree you want to investigate. 

![Barplot](https://github.com/kevinchen27/icd11-dash-visualizations/blob/master/dash1.png)
![Barplot 2](https://github.com/kevinchen27/icd11-dash-visualizations/blob/master/dash2.png)

The most difficult dashboard graph I created was what is known as a Circos plot. Its difficulty was down to the complexity and length of its documentation and data format. A circos plot is useful because it shows you relationship between categories. In this case, the graph connects root nodes that have common nodes. This could give us an interesting preliminary insight which we might want to explore further. The thicker the bands, the greater the number of nodes in common.

![Circos](https://github.com/kevinchen27/icd11-dash-visualizations/blob/master/circos.png)
