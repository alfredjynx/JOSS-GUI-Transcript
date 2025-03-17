---
title: 'CM-GUI: User-Friendly application of the CM Pipeline'
tags:
  - Python
  - Data Science
  - Network Science
authors:
  - name: Joao Alfredo Cardoso Lamy
    orcid: 0009-0005-4744-4754
    equal-contrib: true
    affiliation: 1
  - name: Tomas Alessi
    orcid: 0009-0006-2658-5758
    equal-contrib: true
    affiliation: 1
  - name: Minhyuk Park
    orcid: 0000-0002-8676-7565
    affiliation: 2
  - name: Tandy Warnow
    orcid: 0000-0001-7717-3514
    affiliation: 2
  - name: George Chacko
    orcid: 0000-0002-2127-1892
    affiliation: 2
affiliations:
 - name: Insper Instituto de Ensino e Pesquisa, Sao Paulo, Brazil
   index: 1
 - name: Siebel School of Computing and Data Science, University of Illinois Urbana-Champaign, IL 61801, USA
   index: 2


date: 7 March 2025
bibliography: paper.bib
---

# Introduction -
This project incorporates the CM Pipeline [@Ramavarapu2024] into a graphical user interface (GUI), for the purpose of making the Connectivity Modifier(CM) pipeline accessible to non-expert users who are not comfortable with command line operations.

# The CM Pipeline - 

CM was developed to enforce well-connectedness in clusters generated during a community detection process [@park2023wellconnectedcommunitiesrealworldsynthetic] and implemented as a pipeline. Well-connectedness of a cluster is defined by its min-cut, the minimum number of edges (connections between nodes) that need to be discarded in order for the cluster to be split. If the min-cut is above a user-specified threshold, a cluster is considered well-connected. If not, then the min-cut is applied and the products of the cut (two clusters) are re-evaluated until every community is well-connected. The default threshold is the mild standard of $log_{10}n$, with $n$ being the number of nodes in the community. 

# Statement of need -

Clustering has broad applications. In some cases, its practitioners may not have adequate programming skills to use available clustering software. A user-friendly GUI lowers the barrier for entry and allow simple exploratory analysis. This GUI is also intended to be useful as an instructional tool for novice users. 

# The GUI - 

![GUI Setup for Leiden-CPM with File Upload. \label{fig:Leiden-CPM}](./imgs/Leiden-CPM.png)

The GUI has support for 4 different clustering algorithms \autoref{fig:Algorithms}: Leiden-CPM (Constant Potts Model) [@traag2019louvain; @traag2011narrow] \autoref{fig:Leiden-CPM}, Leiden-Modularity [@traag2019louvain], Infomap [@Rosvall2008] and SBM [@peixoto_graph-tool_2014]. These algorithms will not be explained in this paper. 

![GUI Algorithms. \label{fig:Algorithms}](./imgs/Algorithms.png)

Each one has their own set of parameters that must be specified before running the pipeline. They vary from algorithm to algorithm, with some having more options than others. Here are example images setup for File Upload for each algorithm.

![GUI Setup for Leiden-MOD with File Upload. \label{fig:Leiden-MOD}](./imgs/Leiden-MOD.png)

![GUI Setup for Infomap with File Upload. \label{fig:Infomap}](./imgs/Infomap.png)

![GUI Setup for SBM with File Upload. \label{fig:SBM}](./imgs/SBM.png)


 Each algorithms parameters are explained in the CM Pipeline documentation and in the CM-GUI documentation.

Files can be either uploaded or have their relative file path given \autoref{fig:File-Settings}. 

![GUI File settings. \label{fig:File-Settings}](./imgs/FileReadOptions.png)

Additionally, the software has it's own toy network for users to experient on, that is the "Default" option in the selection box.

The results can be downloaded at the end of the run by clicking the "Download data as CSV" button. 

# Running the GUI

The GUI consists of a front-end and a back-end. This was set up this way to enable remotedly hosting the GUI, making it a website. This is also why there is an option to . This, however, does not mean the GUI is hosted currently. 

The front-end is implemented in streamlit, and the back-end in FastAPI. Those packages where chosen because of their ease of use and modularity.

To run the GUI, the user must clone the repository and run both the front-end adn the back-end locally. Specified instructions and setup are explained in detail in the documentation for the GUI.

After the setup is done, the user can run the CM Pipeline through the front-end.


# Future Installments

Next steps include the containerization of the GUI usiung Docker. This way, a single command is needed to run it, making it easier for local usage.


# References

1. Ramavarapu et al., (2024). CM++ - A Meta-method for Well-Connected Community Detection. Journal of Open Source Software, 9(93), 6073, https://doi.org/10.21105/joss.06073

2. Park, M. et al. (2024). Identifying Well-Connected Communities in Real-World and Synthetic Networks. In: Cherifi, H., Rocha, L.M., Cherifi, C., Donduran, M. (eds) Complex Networks & Their Applications XII. COMPLEX NETWORKS 2023. Studies in Computational Intelligence, vol 1142. Springer, Cham. https://doi.org/10.1007/978-3-031-53499-7_1

3. Traag, V. A., Waltman, L., & Van Eck, N. J. (2019). From Louvain to Leiden: guaranteeing well-connected communities. Scientific reports, 9(1), 1-12.

4. Traag, V. A., Van Dooren, P., & Nesterov, Y. (2011). Narrow scope for resolution-limit-free community detection. Physical Review E—Statistical, Nonlinear, and Soft Matter Physics, 84(1), 016114.

5. Rosvall, M., & Bergstrom, C. T. (2008). Maps of random walks on complex networks reveal community structure. Proceedings of the national academy of sciences, 105(4), 1118-1123.

6. Peixoto, T., “The graph-tool python library”, figshare. (2014) DOI: 10.6084/m9.figshare.1164194
