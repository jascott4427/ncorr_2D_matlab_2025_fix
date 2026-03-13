# Ncorr: 2D Digital Image Correlation (MATLAB)

Ncorr is an open-source 2D digital image correlation (DIC) software package for MATLAB. This version includes critical updates to ensure compatibility with the WebGL-based graphics engine introduced in MATLAB R2025a, while maintaining full support for all previous versions. Not my software, just fixing a bug in the code.

## Research Citation

If you use this software in your research, please cite the following paper:

J Blaber, B Adair, A Antoniou. Ncorr: open-source 2D digital image correlation matlab software. Experimental Mechanics 55 (6), 1105-1122, 2015.

## Installation and Execution

To install the software, clone the repository using the command below. Once the files are downloaded, navigate to the folder within the MATLAB environment and add the directory to your path. Make sure you have both the Image Processing and Statistics Toolboxes instaled in MATLAB before trying to open Ncorr.

```bash
git clone https://github.com/jascott4427/ncorr_2D_matlab_2025_fix.git
cd ncorr_2D_matlab_2025_fix
addpath(pwd);
savepath; % Optional: keeps ncorr in your path for future sessions
handles_ncorr = ncorr;
```
## MATLAB 2025 Compatibility and WebGL

The transition to MATLAB 2025 replaced the legacy OpenGL-based desktop engine with a modern WebGL engine powered by Chromium. The original source code relied on outdated hardware queries that fail to return data in the new environment, leading to initialization crashes. This updated version addresses the issue by utilizing the rendererinfo function for MATLAB R2025a and newer. This allows the software to correctly identify modern GPU hardware through the WebGL pipeline and map that information to the internal structures Ncorr requires for stable data visualization.

This implementation is designed to be fully backward compatible. It employs a version-check logic that automatically detects your MATLAB release. Users on older versions of MATLAB will still utilize the original legacy OpenGL path, ensuring that graphical stability fixes for older hardware remain intact. For students and researchers on newer machines, the software will leverage the high-performance WebGL interface without the need for manual renderer overrides or hardware-check bypasses.

## Resources and Documentation

For detailed information on the DIC algorithms and advanced usage, refer to the following resources:

* **Original Repository:** [https://github.com/justinblaber/ncorr_2D_matlab](https://github.com/justinblaber/ncorr_2D_matlab)
* **Project Website:** [https://www.ncorr.com](https://www.ncorr.com)
