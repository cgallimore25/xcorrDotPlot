[![DOI](https://zenodo.org/badge/739522638.svg)](https://zenodo.org/doi/10.5281/zenodo.10463403) 
[![View xcorrDotPlot on File Exchange](https://www.mathworks.com/matlabcentral/images/matlab-file-exchange.svg)](https://www.mathworks.com/matlabcentral/fileexchange/157201-xcorrdotplot)
[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=cgallimore25/xcorrDotPlot&file=README.md)

# xcorrDotPlot
A vectorized, customizable method of plotting correlation dot plots in MATLAB. 
This function creates a dot plot representing a matrix of statistical values, comparable to R's 'corrplot' function for many pairwise/cross correlations. 
More generally, it can be used for any matrix containing results like p-values or statistical tests.

## Syntax:
`xcorrDotPlot(data)`

`xcorrDotPlot(data, Name, Value, ...)`

`h = xcorrDotPlot(_)`

## Input Arguments:
*(Required)*

- **matrix** - A 2D m x n matrix (not required to be square)
               [data type]

## Output Arguments:
*(Optional)*
- **h**    -   Structure array of handles to axes, dots, major/minor grid lines, row/col labels, text overlaying the values, and colorbar
               [structure]

## Name-Value Pair Arguments:
*(Optional; case insensitive)*

- **triangle type** - determines whether to toggle, and whose value `k` serves as an argument to, the `triu()` or `tril()` functions.
                      The `'full'` input can be passed with no value, as it requires no specification of diagonals above/below the main to keep. 
                      The value `k` can be any integer scalar in range [`-size(matrix, 1) size(matrix, 2)`], depending on the specified triangle type.
                      [`'lower'` | `'upper'` | `'full'`]

- **'majorgrid'** -   toggles black lines encasing all points in the matrix. 
                      [`1` (`true`) | `0` (`false`)]

- **'minorgrid'** -   toggles light gray lines intersecting data pts.
                      [`1` (`true`) | `0` (`false`)]

- **'dotscale'** -    a positive scalar controlling the size of plotted dots.
                      [scalar]

- **'rowlabels'** -   n-by-1 or 1-by-n string array.
                      [string]

- **'collabels'** -   same as `'rowlabels'`.

- **'alpha'** -       non-negative numeric scalar in the closed interval [0-1] indicating opacity of the plotted dots.

- **'overlayvals'** - specifies text overlay for numeric values `'all'` or `'sigonly'`, the latter of which must be followed by a second numeric scalar representing the threshold
                      [`'all'` | `'sigonly'`]

- **'precision'** -   specifies the rounding precision for text labels (i.e. the max number of decimal places to keep)
                      [`0` | `1` | ... `n` | non-negative scalar]

## Examples

### Example 1: Minimum working example

```matlab
% Create some data
data = []; 

% Create plot
figure;
xcorrDotPlot(data);
```
<p align="center">
  <img src="examples/example_001.png">
</p>

### Example 2: Advanced usage

```matlab
% Create some data
data = []; 

% Create plot with custom options
figure;
xcorrDotPlot(data, 'option', value);
```
<p align="center">
  <img src="examples/example_002.png">
</p>

## Catalog of Changes

### Version X.Y.Z
- List of changes
- New features
- Bug fixes
