# DIY hyperspectral imaging via polarization-induced spectral filters

This repo provides code and notebooks for convenience in reproducing the method of "DIY hyperspectral imaging via polarization-induced spectral filters." Katherine Salesin, Dario Seyb, Sarah Friday, and Wojciech Jarosz. Proceedings of ICCP. 2022.

## Setting up your environment

### install rawpy
普通はpip install rawpyで良いはず。できなかった場合の話。
https://pypi.org/project/rawpy/
```
git clone https://github.com/letmaik/rawpy
cd rawpy
pip install numpy cython
pip install .
```

### install matlabengine
はじめにmatlabのインストールをしておいてください。
https://jp.mathworks.com/help/matlab/matlab_external/install-the-matlab-engine-for-python.html

for M1 mac
```
cd /Applications/MATLAB_R2023b.app/extern/engines/python
pip install .
```

### install matlab optimization toolbox

Matlabを起動しアドミンからインストール

## File guide

The Jupyter notebooks in `notebooks/` provide sample code for the algorithms and calibration procedures presented in our paper. You will not be able to use the interactive elements (sliders, plotly graphs, etc.) using the notebook viewers in Visual Studio Code or Github; the notebooks must be downloaded and run locally.
In the terminal, run:
```
cd notebooks
jupyter notebook
```
to start the notebooks. We recommend starting with the notebook `filter_playground` to play with the transmission spectra of our filters!

* **birefringence_calibration_real_world_plots**: load real-world birefringence calibration images and visualize the relationship between rotation of the analyzer and measured intensity
* **birefringence_calibration_sim**: use the method of [\[Belendez et al. 2009\]](https://physlab.lums.edu.pk/images/3/30/Cellophane2.pdf) to solve for birefringence under ideal conditions using simulated data
* **birefringence_calibration**: load real-world birefringence calibration images and use the method of [\[Belendez et al. 2009\]](https://physlab.lums.edu.pk/images/3/30/Cellophane2.pdf) to solve for birefringence
* **choose_optimal_filters**: our algorithm which chooses a discrete set of filters from a continuous space
* **filter_playground**: play with the transmission spectra of our filters!
* **recover_real_world_color_checker**: load real-world ColorChecker images, run white balance to recover an estimate of lighting and sensor response spectra, and reconstruct the reflectance spectrum of each ColorChecker squares
* **recover_real_world_scene**: load real-world images, run white balance to recover an estimate of lighting and sensor response spectra, and reconstruct the reflectance spectrum of each pixel