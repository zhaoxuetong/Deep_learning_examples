# 5.GNN_PPI_network
这里大体上是跑通的，但是具体详细的code还是很迷糊

We use the yeast protein-protein interaction network as the dataset. In terms of the model, we utilize the graph neural network, which can be used to learn the node (protein) embedding based on the network topology. To define the interaction from node embedding, we use the inner product of the embeddings of two nodes as the interaction operation. The higher the product is, the more confidently we believe they have an interaction. Since we have already known some interactions within the network, that is, the existing edges, we can train the graph neural network in a supervised way, using the existing edges (and of course, some protein pairs which do not have interactions as the negative training data) as targets and the cross-entropy as the loss function. After running the optimization until the model converges, we can obtain stable node embeddings for each node based on the network topology. Then we apply the interaction operation (inner product) to each pair of nodes. If the result is higher than a certain threshold, we will predict that there is an interaction between the two nodes. We implemented this graph example using Tensorflow. 

Reference:
* [Network biology tutorial from Jure's group](http://snap.stanford.edu/deepnetbio-ismb/)
