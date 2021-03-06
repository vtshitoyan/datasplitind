# datasplitind
Matlab function generating indices to split data to approximately equal parts. 
One of the main uses is cross-validation for machine learning applications. 
This is an alternative to [crossvalind](https://uk.mathworks.com/help/bioinfo/ref/crossvalind.html) from bioinformatics toolbox, so it will be especially handy if you don't have this toolbox.
Performance-wise, it seems to be on average **50% faster** than crossvalind.

usage: 
```matlab
regions = datasplitind( m, n, rnd_flag );
```
where `m` is the length of your data, `n` is the number of regions, and if `rnd_flag` is `true` the output will be randomized. If `rnd_flag` is 
false the `regions` will be ordered, with approximately equal lengths of each index. These long/short regions are distributed randomly to avoid any bias.

# plotRegions
A function for visualising the split regions. The syntax is 

```matlab
ph = plotRegions( x, y, regions );
```
The result is a plot where `y` is colored according to `regions`. `x`, `y` and `regions` should have the same length.
