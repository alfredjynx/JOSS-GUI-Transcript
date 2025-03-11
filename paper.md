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
    affiliation: 2
  - name: Tomas Alessi
    equal-contrib: true
    affiliation: 2
  - name: Minhyuk Park
    affiliation: 1
  - name: George Chacko
    affiliation: 1
affiliations:
 - name: Department of Computer Science, University of Illinois Urbana-Champaign, IL 61801, USA
   index: 1
 - name: Insper Instituto de Ensino e Pesquisa, Sao Paulo, Brazi
   index: 2

date: 7 March 2025
bibliography: paper.bib
---

# Introduction -
This projects incorporates the CM Pipeline into a user-friendly graphic user interface (GUI), aiming to simplify the usage of the CM Pipeline to the end user. The CM Pipeline was created to guarantee well-connectedness in networks during a clustering/community detection process. This is a graph partitioning problem, with a network being inputted and the main objective is separating nodes into communities, which may also be reffered as clusters. *(Should I quote Park et al., 2023?)*

The well-connectedness of a community is measured by the min-cut, the minimum number of edges (connections between nodes) that need to be discarded in order for the cluster to be split. If the min-cut is above a threshold, the community is considered well-connected. If it's not, then the community is split and the clustering process continues untill every community is well-connected. The user of the CM Pipeline can specify a min cut threshold, deciding what should count as a well connected community. For this GUI, this option has not been implemented, setting the min-cut threshold as $log_{10}n$, with $n$ being the number of nodes in the community. 

# Statement of need -

Clustering, as a concept, can be beneficial in various ways and in various different settings. A researcher in biology can use clustering to be able to map out the relationships between different species. Another, in a medical field, can map out the spread of diseases in a certain subset of a population. 

In those cases, the researchers are not in a tech-centered field of study, so they might not have programming knowledge. This may prohibit them from using already available clustering software. The GUI serves as a way of negating this problem for the CM Pipeline specifically.

Also, this may be an introduction to clustering to many who don't have data science experience.

# The GUI - 

The GUI has support for 4 different clustering algorithms: Leiden-CPM (Constant Potts Model), Leiden-Modularity, Infomap and SBM. These algorithms will not be explained in this paper. 

Each one has their own set of parameters that must be specified before running the pipeline. They vary from algorithm to algorithm, with some having more options than others. Each algorithms parameters are explained in the CM Pipeline documentation and in the CM-GUI documentation.

Files can be either uploaded or have their relative file path given. Additionally, the software has it's own toy network for users to experient on, that is the "Default" option in the selection box.

The results can be downloaded at the end of the run by clicking the "Download data as CSV" button. 

- Go over the main use cases, example usage
- Have figures showing the GUI and most options, have explanations of possible combinations

# Running the GUI

The GUI consists of a front-end and a back-end. This was set up this way to enable remotedly hosting the GUI, making it a website. This is also why there is an option to . This, however, does not mean the GUI is hosted currently. 

The front-end is implemented in streamlit, and the back-end in FastAPI. Those packages where chosen because of their ease of use and modularity.

To run the GUI, the user must clone the repository and run both the front-end adn the back-end locally. Specified instructions and setup are explained in detail in the documentation for the GUI.

After the setup is done, the user can run the CM Pipeline through the front-end.

- Explain how to run the GUI locally, and how it can be setup as a split application (back and front-end)

# Future Installments

Next steps include the containerization of the GUI usiung Docker. This way, a single command is needed to run it.

- Having the GUI be entirelly localized and containerized

# Acknowledgements


# References

1. Ramavarapu et al., (2024). CM++ - A Meta-method for Well-Connected Community Detection. Journal of Open Source Software, 9(93), 6073, https://doi.org/10.21105/joss.06073

2. Park, M. et al. (2024). Identifying Well-Connected Communities in Real-World and Synthetic Networks. In: Cherifi, H., Rocha, L.M., Cherifi, C., Donduran, M. (eds) Complex Networks & Their Applications XII. COMPLEX NETWORKS 2023. Studies in Computational Intelligence, vol 1142. Springer, Cham. https://doi.org/10.1007/978-3-031-53499-7_1