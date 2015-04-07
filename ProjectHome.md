
---

# Project Abstract #

---



We provide an algorithm based on Integer Linear Programming to find highly connected components in Molucular Interaction Maps and we show that how it is useful for visualization after the reducing these highly connected components.


---

# Showcase #

---

### Real Example:P73-mediated cell cycle arrest and apoptosis pathways map ###

---


#### Othogonal Layout ####

MIM Notation supports rectangular drawing of edges and whole layout is assumed like a electrical circuit.

| Original P73 Network | Simplified P73 Network |
|:---------------------|:-----------------------|
| [http://mimilp.googlecode.com/svn/trunk/image/P73/orto\_org\_s.jpg ](http://mimilp.googlecode.com/svn/trunk/image/P73/orto_org.jpg) | [http://mimilp.googlecode.com/svn/trunk/image/P73/orto\_reduced\_s.jpg ](http://mimilp.googlecode.com/svn/trunk/image/P73/orto_reduced.jpg) |
| [Original GML file](http://mimilp.googlecode.com/svn/trunk/data/P73/orto_org.gml) | [Simplifiedb GML file](http://mimilp.googlecode.com/svn/trunk/data/P73/orto_reduced.gml) |

#### Sugiyama Style ####

Although MIM notation is based on Orthogonal drawings, we would like to show how other graph layout algorithms work on the network. See the difference on simplified case of Sugiyama Style drawing.

| Original P73 Network | Simplified P73 Network |
|:---------------------|:-----------------------|
| [http://mimilp.googlecode.com/svn/trunk/image/P73/sugi\_org\_s.jpg ](http://mimilp.googlecode.com/svn/trunk/image/P73/sugi_org.jpg) | [http://mimilp.googlecode.com/svn/trunk/image/P73/sugi\_s.jpg ](http://mimilp.googlecode.com/svn/trunk/image/P73/sugi.jpg) |
| [Original GML file](http://mimilp.googlecode.com/svn/trunk/data/P73/sugi_org.gml) | [Simplified GML file](http://mimilp.googlecode.com/svn/trunk/data/P73/sugi.gml) |


---

### Small Example ###

---


| Original Network | Simplified Network |
|:-----------------|:-------------------|
| [http://mimilp.googlecode.com/svn/trunk/image/example1/readLayoutOriginal\_s.jpg ](http://mimilp.googlecode.com/svn/trunk/image/example1/readLayoutOriginal.jpg) | [http://mimilp.googlecode.com/svn/trunk/image/example1/readLayoutReduced\_s.jpg ](http://mimilp.googlecode.com/svn/trunk/image/example1/readLayoutReduced.jpg) |
| [Original Network GML file](http://mimilp.googlecode.com/svn/trunk/data/example1/readLayoutOriginal.gml) | [Simplified Network GML file](http://mimilp.googlecode.com/svn/trunk/data/example1/readLayoutReduced.gml) |



---

# Experimental Data #

---


Conducted experiments in the paper are available.


---

### Artifical Network Experiments ###

---


| For experiment 1 - 200x200 bipartite graphs contains 20x20,30x30,40x40...,100x100 bicliques with noise levels 0 to 0.05 | [ZIP File](http://mimilp.googlecode.com/svn/trunk/data/experiment1/data.zip) | [TAR GZ File](http://mimilp.googlecode.com/svn/trunk/data/experiment1/data.tar.gz) | Results(available soon) |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|:------------------------|
| For the automated drawing of given small example at the paper| [Original Network GML file](http://mimilp.googlecode.com/svn/trunk/data/example1/readLayoutOriginal.gml) | [Simplified Network GML file](http://mimilp.googlecode.com/svn/trunk/data/example1/readLayoutReduced.gml) |  |


---

### Real Network Experiment ###

---


| For the drawing of real network named P73-mediated cell cycle arrest and apoptosis pathways map| [Original P73 Network GML file](http://mimilp.googlecode.com/svn/trunk/data/P73/orto_org.gml) | [Simplified P73 Network GML file](http://mimilp.googlecode.com/svn/trunk/data/P73/orto_reduced.gml) |
|:-----------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------|


---

# Downloads #

---


This project contains three steps. The first step is to build network. For building a network there are many posibilities. One may need to import a network from SBML file. Another possibilty is to import from GML file. Furthermore, SMIMML and other import options are available. Then we run out methodology for simplification methodology. Next after simplification(for now it is not automated) we run OGDF's orthogonal algorithm(due to MIM notation). We assume that graph is AND/OR graph.

Then, We first publish the automated layout [binary file](http://code.google.com/p/mimilp/downloads/detail?name=Automated_Layout_1.0_Win.zip#makechanges) that is implemented using OGDF C++ library. This file containts an executable that takes the file in our format that is

|(int) // Number of nodes|
|:-----------------------|
|(**char)Node\_name1 (int)width1 (int)height1**|
|(**char)Node\_name2 (int)width2 (int)height2**|
|...|
|(int) // Number of edges|
|Node\_name1 Node\_name2 // source node name, target name node|
|...|

and returns the layout in Orthogonal(Force directed and Sugiyama as well). The zip file contains a password for now please contact committer melihsozdinler.

The methodology that we use also requires CPLEX, Integer Linear Programming solver. Hence, first you should have a licensed CPLEX. All the experimental coding is inside
[the archive file](http://code.google.com/p/mimilp/downloads/detail?name=mimilp_1.0_Linux.zip#makechanges). You can recompile simply using _run.sh_. We require Linux operating system with g++ compiler. The sample inputs are given in _README_ file. Finally, to perform the experiment in the paper, download [input file](http://mimilp.googlecode.com/svn/trunk/data/experiment1/data.zip) and then run
```
./runExperiment1.exe data
```

Next, for the BIMAX algorithm and CPLEX method two file is created, _bimax.txt_, _cplex.txt_. This file contains the total running time of 200x200 bipartite graphs
with 20x20 to 100x100 complete bipartite graphs and noise from 0.00 to 0.05. Rows are complete biparte cases, columns are noise ratio in the 200x200 bipartite graphs.


---
