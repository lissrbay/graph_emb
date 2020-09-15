# graph_emb
Test task for JBR project

The task is to visualize the graph of interactions between contributors to the "React" repository.

### Data scraping

Run get_data.ipynb to collect information about contributors. Using Github API with basic authentication we can make up to 5000 requests per hour that is not enough to get all the data, so it will take some time. The folder 'users/' will contain the resulting '.txt' of user's modified files. The folder 'data/' will contain the resulting '.csv' all time contributions count with logins.

### Data visualization

In data_visualization.ipynb the data about each user is aggregated into a DataFrame. Next, we can construct a graph, where edges are ('first_contributor', 'second_contributor', intersection of modified files). Now we can move on to visualization. The notebook contain different ways to do this:

1. The simplest: use bitwise vectors of changed files for every user as their embeddings and visualize graph after TSNE.
2. Draw graph using networkx methods.
3. Fit node2vec model to get node embeddings, use TSNE and plot constructed points.

As for me, the second and the third methods are giving more informative plots.

### Used libraries

+ numpy==1.18.1
+ pandas==1.0.3
+ matplotlib==3.2.1
+ sklearn==0.23.1
+ networkx==2.5
+ fastnode2vec==0.0.5
