# elevation-profile

This program performs elevation profile approximation using two interpolation methods – Lagrange and spline – and allows making a cursory comparison, taking processing time and result accuracy into account.

As an input program takes text file describing elevation profile of some route. The file contains rows with data in the form of: distance<space>height, e.g.:
0 12
2 12.3
4 10.7

From the input a given number of reference samples is taken. Then, from among those samples, the program chooses a given number of interpolation nodes. Based on interpolation nodes, the set of new (approximated) values is generated.
Results are saved into text file, similar to that containing input. The additional Python script uses those results to generate graphs showing the original and the approximated routes.
  
Following parameters are adjustable:
  •	number of reference samples (rows) taken from the input file – defined by #define SAMPLES
  •	input files – paths to the files are stored in const char* data_sets[4]; data must answer the description introduced above
  •	intervals between interpolation nodes – defined in int intervals[4] array
  
By default 4 sets of values are generated for one method – each set created with different number of interpolation nodes.
