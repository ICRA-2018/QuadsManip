# QuadsManip
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/icra2018/quadsmanip.svg)](https://hub.docker.com/r/icra2018/quadsmanip)
<a href="#how-to-run-with-docker"><img src="https://img.shields.io/badge/Docker-instructions-brightgreen.svg"></a>

**Cooperative Manipulation using Multiple Quadrotors without Communication**

Click to watch demo video:

<a href="https://www.youtube.com/embed/MYOgharJuoY" target="_blank"><img src="https://img.youtube.com/vi/MYOgharJuoY/0.jpg" 
alt="cla" width="240" height="180" border="10" /></a>

This repository contains the simulation code of the following <a href="https://msl.stanford.edu/sites/default/files/wang.singh_.pavone.ea_.icra18.pdf" target="_blank">ICRA 18 paper</a>:

Z. Wang, S. Singh, M. Pavone, and M. Schwager, “Cooperative object transport in 3D with multiple quadrotors using no peer communication,” In Proc. International Conference on Robotics and Automation (ICRA), Brisbane, Australia, 2018


Code author: <a href="http://web.stanford.edu/~zjwang/" target="_blank">Zijian Wang</a>, Stanford University


## Quickstart and Demo

```
python demo_main.py
```
```
python demo_single_quad.py
```
```
python demo_traj_opt.py
```
```
python demo_traj_opt_time.py
```

The code has been tested in Mac OS 10.11 and Ubuntu 16.04.

This repo does not contain rviz visualization as used in the paper in order to minimize dependency and ease the use of the code. Instead, `matplotlib` is used for visualization.


## Python Dependencies
- **Python 2.7**

- numpy: v1.11.3

- matplotlib: v2.0.0

- (optional) cvxpy: v0.4.11


## Citation

If you find our work useful in your research, please consider citing:

    @inproceedings{WangEtAlICRA18MultiQuadManipulation,
    author = {Z. Wang and S. Singh and M. Pavone and M. Schwager}, 
    title = {Cooperative Object Transport in 3D with Multiple Quadrotors using No Peer Communication},
    booktitle = {Proc. of the International Conference on Robotics and Automation (ICRA)},
    year = {2018}
    }

## License

Our code is released under MIT License (see LICENSE file for details).

For any technical issues, please contact Zijian Wang <zjwang_AT_stanford_DOT_edu>, or open an issue in Github.

# How to Run with Docker
## Linux
Tested on Ubuntu 16.04.6 with Docker 18.06.1-ce.

1. Open a terminal and run the command:
```
docker run --rm -p 8888:8888 -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix  icra2018/quadsmanip:latest
```
2. Run a web browser and open the link: [http://localhost:8888/lab/tree/README.ipynb](http://localhost:8888/lab/tree/README.ipynb)

## macOS
#### Prerequisites
* [XQuartz](https://www.xquartz.org/):
  - Activate the option `Allow connections from network clients` in XQuartz settings
  - Quit & restart XQuartz (to activate the setting)
  - Open a terminal and run the command:<br/> `xhost + localhost`

Tested on macOS Mojave 10.14.3 with XQuartz 2.7.11 and Docker Desktop 2.0.0.3 (engine: 18.09.2).
1. Open a terminal and run the command:
```
docker run --rm -p 8888:8888 -e DISPLAY=host.docker.internal:0 -v /tmp/.X11-unix:/tmp/.X11-unix  icra2018/quadsmanip:latest
```
2. Run a web browser and open the link: [http://localhost:8888/lab/tree/README.ipynb](http://localhost:8888/lab/tree/README.ipynb)

## Windows
### Prerequisites
* [VcXsrv](https://sourceforge.net/projects/vcxsrv/) or another X Windows Server
  - Run `Xlaunch` from the Start menu
  - Select `Multiple windows`, `Start no client`, and set `Disable access control`

Tested on Windows 10 Education wih VcXsrv 1.20.1.4 and Docker Desktop 2.0.0.3 (engine: 18.09.2).
1. Open a Windows PowerShell and run the command:
```
docker run --rm -p 8888:8888 -e DISPLAY=host.docker.internal:0  icra2018/quadsmanip:latest
```
2. Run a web browser and open the link: [http://localhost:8888/lab/tree/README.ipynb](http://localhost:8888/lab/tree/README.ipynb)
