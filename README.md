# Community-Detection-using-Girvan-Newman-Algorithm
This project implements an edge-removal community detection algorithm based on edge betweenness centrality (inspired by the Girvan-Newman Algorithm) on a subsampled Flickr graph using igraph, iteratively removing high-betweenness edges to detect and visualize social communities.

# Problem Statement

<img width="1884" height="125" alt="image" src="https://github.com/user-attachments/assets/ec658129-e98c-4136-8cec-eb335d540bd3" />


# Solution Summary
- Implemented an **edge-removal community detection algorithm** on a subsampled **Flickr graph**, inspired by the **Girvan-Newman Algorithm** and using **edge betweenness centrality**.

- **Technical Workflow**:
  - Loaded `Flickr_sa_edges_pd.csv` (2098 edges) into a Pandas DataFrame, converted to NumPy array.
  - Built **igraph.Graph** object (directed graph) from edge list.
  
- **Core Algorithm**:
  - Custom `betweenness_centrality_of_edges` function:
    1. Identified all node pairs.
    2. Found all shortest paths for each pair.
    3. Counted, for each edge, how many shortest paths it appeared in, divided by total paths for that pair.
    4. Summed across all pairs → **edge betweenness centrality**.
  - Main loop:
    - Calculated edge betweenness centralities.
    - Removed top-k (e.g., 20) highest-betweenness edges.
    - Repeated for `max_iter` (e.g., 100) or until reaching `target_components` (e.g., 30 communities).

- **Visualization & Evaluation**:
  - Used **igraph’s community detection methods** and **RainbowPalette** for visualizing resulting communities.

- **Key Insights**:
  - Demonstrated hands-on implementation of **Girvan-Newman-style edge-removal**.
  - Showcased **igraph** as a powerful library for graph operations and visualization in Python.
  - Iterative edge removal effectively increased **connected components**, splitting graph into clear communities.
  - Achieved **31 communities** on the subsampled Flickr graph.
  - Custom betweenness calculation deepened understanding beyond built-in library functions.

- **Conclusion**:
  - Successfully implemented a community detection algorithm, offering both conceptual insights and practical tools for graph-based social structure analysis.
