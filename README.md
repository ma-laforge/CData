# CData.jl: (C-Data) Analysis/Visualization Suite

"Focus on the analysis itself, not data manipulation"

## Description

CData.jl (C-Data) provides a collection of tools to simplify the analysis of large multi-dimensional datasets & better visualize (*see*) mathematical relationships buried within.

The C-Data toolkit was initially designed to assist with circuit-data (C-Data) analysis.  That being said, C-Data provides a generic toolkit that can also be applied to other scientific fields.

The C-Data toolkit is implemented in the Julia Programming Language.

### Supported Plotting Backends

 - **Grace/xmgrace**: Short load times.  Fastest solution when dealing with small datasets.
 - **Matplotlib/PyPlot.jl**: Longer load times (loading anaconda).  Faster than Grace/xmgrace solution when dealing with larger datasets.
 - **Qwt/guiqwt**: Longer load times (loading anaconda).  Faster than Matplotlib/PyPlot.jl solution when dealing with larger datasets.

<a name="Installation"></a>
## Installation

 1. [Install Julia](https://github.com/ma-laforge/HowTo/tree/master/julia/julia_install.md#Installation)

 1. [Install Anaconda distribution of Python 2.7](https://github.com/ma-laforge/HowTo/tree/master/conda/conda_install.md#Py27Installation)

  - Anaconda is required if one is to render plots with Matplotlib/PyPlot.jl or Qwt/guiqwt.

 1. [Install Grace](https://github.com/ma-laforge/HowTo/tree/master/grace/grace_install.md#Installation) (Optional backend)

 1. [Install PyPlot](https://github.com/ma-laforge/HowTo/tree/master/julia/julia_install.md#PyPlot) (Optional backend)

 1. [Install guiqwt](https://github.com/ma-laforge/HowTo/tree/master/guiqwt/guiqwt_install.md#Py27Installation) (Optional backend)

 1. Install C-Data Julia modules (Please install modules in order shown below to avoid potential issues).

		julia> Pkg.clone("https://github.com/ma-laforge/FileIO2.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/MDDatasets.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/GracePlot.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/EasyPlot.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/EasyPlotGrace.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/EasyPlotMPL.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/EasyPlotQwt.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/EasyData.jl.git")
		julia> Pkg.clone("https://github.com/ma-laforge/SignalProcessing.jl.git")

<a name="SampleUsage"></a>
## Sample Usage

Examples demonstrating the capabilities of the C-Data toolkit can be found under the [SignalProcessing.jl](https://github.com/ma-laforge/SignalProcessing.jl) module [sample/ subdirectory](https://github.com/ma-laforge/SignalProcessing.jl/tree/master/sample).

### Sample Output Gallery

Outputs of said examples, as generated with the EasyPlotGrace.jl module, can be viewed in the [SignalProcessing Gallery](https://github.com/ma-laforge/FileRepo/tree/master/SignalProcessing/sampleplots).

### Generating Sample Output

The plots associated with this sample subdirectory can be generated by running sample/runtests.jl of the SignalProcessing.jl module:

		$ cd [JULIA_PKGDIR]/SignalProcessing.jl
		$ julia
		julia> include("sample/runtests.jl")

**NOTE**: `JULIA_PKGDIR` is easily located from the Julia console:

		$julia
		julia> Pkg.dir()

By default, runtests.jl will render plots using the Grace backend.  To use the PyPlot/Matplotlib backend instead, first set the global variable `plotlist`:

		$ cd [JULIA_PKGDIR]/SignalProcessing.jl
		$ julia
		julia> plotlist = Set([:MPL])
		julia> include("sample/runtests.jl")

## Documentation

Documentation is limited at the moment.  See Github pages of corresponding modules for more detail.

**Documentation for Principal Modules**

 1. **MDDatasets.jl** - Multi-dimensional datasets & operations:
<br><https://github.com/ma-laforge/MDDatasets.jl>.
 1. **SignalProcessing.jl** - Step/pulse responses, Fourier transform/series, PRBS sequences, ...:
<br><https://github.com/ma-laforge/SignalProcessing.jl>.
 1. **EasyPlot.jl** - Simple/Fast Plot Objects:
<br><https://github.com/ma-laforge/EasyPlot.jl>.
 1. **EasyData.jl** - Simple/Fast(+HDF5) {data, plot} &hArr; file:
<br><https://github.com/ma-laforge/EasyData.jl>.

**Documentation for Secondary Modules**

 1. **GracePlot.jl** - Publication-quality plotting for Julia using Grace/xmgrace:
<br><https://github.com/ma-laforge/GracePlot.jl>.
 1. **EasyPlotGrace.jl** - Implements EasyPlot.jl rendering interface using Grace/xmgrace:
<br><https://github.com/ma-laforge/EasyPlotGrace.jl>.
 1. **EasyPlotMPL.jl** - Implements EasyPlot.jl rendering interface using Matplotlib/PyPlot/PyCall:
<br><https://github.com/ma-laforge/EasyPlotMPL.jl>.
 1. **EasyPlotQwt.jl** - Implements EasyPlot.jl rendering interface using Qwt/guiqwt/PyCall:
<br><https://github.com/ma-laforge/EasyPlotQwt.jl>.
 1. **EDAData.jl** - Provides access to data formats used by EDA tools:
<br><https://github.com/ma-laforge/EDAData.jl>.
 1. **CppSimData.jl** - Julia wrapper for 3rd party .tr0 reader:
<br><https://github.com/ma-laforge/CppSimData.jl>.
 1. **FileIO2.jl** - "File Object"-Type Hierarchy:
<br><https://github.com/ma-laforge/FileIO2.jl>.

## Known Limitations

### Compatibility

Extensive compatibility testing of the C-Data toolkit has not been performed.  The module has been tested using the following environment(s):

 - Linux / Julia-0.4.0 (64-bit) / Anaconda 2.1.0 (64-bit w/Python 2.7.8)

## Disclaimer

The C-Data toolkit is not yet mature.  Expect significant changes.

This software is provided "as is", with no guarantee of correctness.  Use at own risk.
