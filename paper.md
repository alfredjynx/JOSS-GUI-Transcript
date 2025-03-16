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
    equal-contrib: true
    affiliation: 1
  - name: Minhyuk Park
    affiliation: 2
  - name: Tandy Warnow
    affiliation: 2
  - name: George Chacko
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
This project incorporates the CM Pipeline (*1*) into a graphical user interface (GUI), for the purpose of making the Connectivity Modifier(CM) pipeline accessible to non-expert users who are not comfortable with command line operations.

# The CM Pipeline - 

CM was developed to enforce well-connectedness in clusters generated during a community detection process (*2*) and implemented as a pipeline. Well-connectedness of a cluster is defined by its min-cut, the minimum number of edges (connections between nodes) that need to be discarded in order for the cluster to be split. If the min-cut is above a user-specified threshold, a cluster is considered well-connected. If not, then the min-cut is applied and the products of the cut (two clusters) are re-evaluated until every community is well-connected. The default threshold is the mild standard of $log_{10}n$, with $n$ being the number of nodes in the community. 

# Statement of need -

Clustering has broad applications. In some cases, its practitioners may not have adequate programming skills to use available clustering software. A user-friendly GUI lowers the barrier for entry and allow simple exploratory analysis. This GUI is also intended to be useful as an instructional tool for novice users. 

# The GUI - 

The GUI has support for 4 different clustering algorithms: Leiden-CPM (Constant Potts Model) (*3*) (*4*), Leiden-Modularity (*3*), Infomap (*5*) and SBM (*6*). These algorithms will not be explained in this paper. 

Each one has their own set of parameters that must be specified before running the pipeline. They vary from algorithm to algorithm, with some having more options than others. Each algorithms parameters are explained in the CM Pipeline documentation and in the CM-GUI documentation.

Files can be either uploaded or have their relative file path given. Additionally, the software has it's own toy network for users to experient on, that is the "Default" option in the selection box.

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

6. Peixoto, T., “The graph-tool python library”, figshare. (2014) DOI: 10.6084/m9.figshare.1164194 [sci-hub, @tor]
