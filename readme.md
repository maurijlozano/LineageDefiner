Lineage Definer
===============
Version: 1.0
Developed by Mauricio J. Lozano

#Description
Define phylogenetic lineages based on distance and branch support cutoffs.

Lineage Definer uses ETE3 API to traverse phylogenetic trees and define clusters based on the distance of nodes to the root. The algorithm traverses nodes selecting always the child with more descendants. A new lineage is defined for the nodes with a distance to the root greater than a minDist (set by the user). Each time a lineage is defined minDist is incremented for successive lineages definition. 
An argument for flexibilization of the distance is included.


#Usage

usage: LineageDefiner.py [-h] -i FILE (-o OFILE) (-pp PP) (-bs BS) -mdist MINDIST (-fmdist MINDISTPERCENT) (-bnmdist MINDISTBN) (-lp LINEAGEPREFIX) (-plotTree PLOTT)

##Script arguments

Required Arguments:
-i	Input newick tree file
-mdist	Required (Decimal Number): Minimal distance from node to leaf for lineage definition.
  
Optional Arguments
-o	Output file base name,
-pp (Decimal Number from 0 to 1)	Branch support cutoff. Bayes Posterior Probability (>0.70 recommended).
-bs (Integer)	Branch support cutoff. Bootstrap cutoff value (> 70% Default)
-fmdist (Percent of minDist)	Flexible Minimal distance from node to leaf for lineage definition. Allows a % variation for minDist. e.g. For -mdist 1 -fmdist 10 => Lineages will be also defined for distances from the root of 0.9, 1.9 and so on.
-bnmdist (Percent of minDist)	Minimal distance between lineage nodes. i.e. Only will define a new lineage if the distance to the previously defined lineage is greater than a percentage of mdist set by the user. e.g. For -mdist 1 -bnmdist 10, the distance between successive lineages will be required to be greater than 0.1.
-lp (string)	Lineage prefix. Prefix used for lineage naming.
-plotTree (Boolean)	If true Plot pdf and svg figures. Values = T or F(Default).


