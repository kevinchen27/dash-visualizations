# Dash Visualizations of ICD 11 Network Data

This summer, I interned at NIH's Big Data 2 Knowledge Center at UCLA. My research lab’s work consisted of working with WHO’s International Classification of Diseases 11 (ICD 11) data to create a web application which can be used by medical professionals for further analysis.  This project’s main goal is to further ICD 11’s purpose, which is to “[provide] a common language that allows health professionals to share health information across the globe”. I was excited to join this project because aside from the glamorous world of consumer tech products, I am extremely hopeful of the technology's potential in the field of healthcare. Coming from India, where healthcare services are inadequate for millions of people in the country, I feel a personal connection to the advancement of healthcare technology and was eager to learn more about the current landscape of disease research and contribute to furthering research efforts

## The Data

ICD 11 data is in the form of a network graph, which is very similar to that of a binary tree. In ICD 11, there are 26 “roots”, or 26 base diseases and defects.  Each of these 26 root nodes has several levels, with each level containing multiple nodes that “descend” from the root node. Each node apart from the “leaf” or lowermost node has “edges” that connects it to other nodes. Additionally, each root had its own subtree, with all the subtrees connected together through a common "ICD 11" Node that we created

The purpose of the network graph data structure and node attributes is to allow the user to better understand disease causes and relationships that fall under a larger category. For example, the node “External Causes of Morbidity and Mortality has several children, one of them being “Unintentional land transport road traffic injury event”. 

## Tree Creation and Data Manipulation

My work on ICD 11 Data was done using Python and Jupyter Notebook. To create a network graph, I first studied network structures and algorithms and trained myself in NetworkX, a Python package meant specifically for creating, manipulating and investigating network data. When creating nodes, I preserved the attributes of the nodes, namely ID, Title, Children, and Parents, which was saved as a Python dictionary in NetworkX. 

![Tree Creation](https://github.com/kevinchen27/dash-visualizations/blob/master/tree%20creation.png)
