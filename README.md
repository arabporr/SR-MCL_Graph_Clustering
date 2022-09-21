# Identifying overlapping functional modules of protein interactions graph
In this project, I tried implementing one of the most efficient algorithms for large graphs clustering, the SR-MCL, in python and checked how it works on both big and small graphs.

The SR-MCL algorithm is an improvement to the MCL (Markov Clustering Algorithm). The MCL is a practical algorithm for clustering biological networks, for instance, clustering protein-protein interaction (PPI) networks to identify functional modules. But it has some limitations and problems with bridge nodes.

A few years later, the R-MCL (Regularized MCL) [introduced by Yu-Keng Shih and Srinivasan Parthasarathy in 2010](https://www.researchgate.net/publication/221611395_Markov_Clustering_of_Protein_Interaction_Networks_with_Improved_Balance_and_Scalability) solved some of the MCL problems and improved execution time. However, still, the problem with bridge nodes remains. Two years later, [the same people came up with the new idea of SR-MCL](https://academic.oup.com/bioinformatics/article/28/18/i473/243788?login=true). The main idea behind it was to make the R-MCL algorithm not focus on bridges by softening the weights of the canonical flow matrix after each step.

The implemented code was then run on a real-world dataset, weighted yeast proteins interactome, to check how long it takes to reach an end and converges with a graph of size 1e3 nodes and 1e4 edges!

## Testing on Random Graph
- After testing its performance to see how it works, I created a random graph with 50 nodes and some edges between them. 

![RandomGraph](https://github.com/arabporr/SR-MCL_Graph_Clustering/blob/e2f2d3c16aff30066d4921857c660c093e03e99d/RandomGraph.png)

- Then by running the algorithm on them, I colored each cluster a different color, But the bridge nodes colored yellow to be identified!

![ClusteredRandomGraph](https://github.com/arabporr/SR-MCL_Graph_Clustering/blob/e2f2d3c16aff30066d4921857c660c093e03e99d/ClusteredRandomGraph.png)

## Reference
- [Markov Clustering of Protein Interaction Networks with Improved Balance and Scalability](https://www.researchgate.net/publication/221611395_Markov_Clustering_of_Protein_Interaction_Networks_with_Improved_Balance_and_Scalability)
- [Identifying functional modules in interaction networks through overlapping Markov clustering](https://academic.oup.com/bioinformatics/article/28/18/i473/243788?login=true)
