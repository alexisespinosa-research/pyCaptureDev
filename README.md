# pyCaptureDev

This repository is for the development of python tools for estimating **particle capture in aquatic systems**. These tools use results from the research performed by: Alexis Espinosa-Gayosso, Marco Ghisalberti, Greg Ivey, Nicole Jones and Jeff Shimeta.

This repository has been published as complementary information of the manuscript:

```
Espinosa-Gayosso A., Ghisalberti M., Shimeta J. & Ivey G.N.
"On predicting particle capture rates in aquatic systems"
Submited to PLOSOne on September2020.
Response to Reviewers submitted on September2021.
```
## The "pyCapture" package
This package is under the directory `pyCapture`. It contains the database generated from the CFD simulations described in the manuscript. It also contains the function for estimating the capture efficiency by direct interception:

```
pyCaptureDB.captureEfficiencyDI
```
The function can give estimates of capture efficiency for `0<=Rey<=1000` and `0<=rp<=1.5`. Estimates are generated by interpolating the values within the mentioned CFD database. Its usage is described in the **example scripts** and it is also utilised in the Graphic User Interface: **calculatorGUI**.

## The "pyCapture_ExampleScripts" directory
Two scripts with examples on how to use the package `pyCapture` and the function `pyCaptureDB.captureEfficiencyDI` are provided in the directory `pyCapture_ExampleScripts`.
The script `basicUse.py` provides a basic explanation of use.
The script `totalBiomassOptimisation_Fig-10.py` provides a practical example and reproduces the analysis from the manuscript about the optimal use of biomass of capturing structures of aquatic organisms (Fig-10).

## The Grafical User Interface: "calculatorGUI"
The directory `pyCapture_CalculatorGUI` contains an interactive tool for estimating capture efficiency and rates of capture in aquatic systems.
This is a simple Graphic User Interface built with Tkinter. By executing the `calculatorGUI.py`, users can input different variables or parameters for obtaining estimates of Capture Efficiency and Particle Capture Rate. The tool uses the `pyCaptureDB.captureEfficiencyDI` function.

## Python dependencies
#### Dependencies needed by pyCapture package
- `numpy`
- `scipy`

#### Additional dependencies needed by the example scripts
- `matplotlib`

#### Additional dependencies needed by the calculatorGUI
- `tknter` is used, but this package is part of the basic installation of python-3, so no additional installation is needed

## Installation

#### For Mac or Linux:
1. Install Python 3 on your computer. (Look for instructions elsewhere, although at the time of writing, the following instructions worked fine: [Python 3 installation on mac]https://www.freecodecamp.org/news/python-version-on-mac-update/)
2. Install a GIT client on your computer. (Look for instructions elsewhere.)
3. Clone this repository into your computer. If using the command line, use:
```bash
$ git clone https://github.com/alexisespinosa-research/pyCaptureDev
```

4. Install all the Python dependencies. We have used `pip3` for the installation of the dependencies. For example (from a command prompt in mac):
```bash
$ pip3 install numpy scipy matplotlib
```


#### For Windows:

1. Install Python 3 on your computer (look for instructions elsewhere). [Python releases for windows.](https://www.python.org/downloads/windows/).
2. Install a GIT client on your computer (look for instructions elsewhere). We recommend to use the tool: "GitHub Desktop".
3. Clone this repository into your computer. If using the command line, use:
```dos
$ git clone https://github.com/alexisespinosa-research/pyCaptureDev
```

4. Install all the Python dependencies indicated above. We have used `pip` for the installation of the dependencies. For example (from a command prompt in windows):
```dos
$ py -m pip install numpy scipy matplotlib
```


## Use

#### Calculator GUI
1. cd into the directory where the calculator program is:
```bash
$ cd <Path>/<To>/pyCaptureDev/pyCapture_CalculatorGUI
```
2. Execute the `calculatorGUI.py` to obtain estimates.
```bash
$ python3 calculatorGUI.py
```
then a graphic interphase calculator will pop into screen. (wait a few seconds if this is the first time you execute it.)

Note that the tool displays error on pop-up mwssages, but some other errors are displayed on the secondary Python screen that will open when executing the tools.

#### Example scripts

For reading the scripts we usually open them with the Python Integrated Development Tool: IDLE. And execute them from the IDLE Run menu.
You can also execute the scripts directly from the command line. For example:

```bash
$ cd <Path>/<To>/pyCaptureDev/pyCapture_ExampleScripts
$ python3 totalBiomassOptimisation_Fig-10.py
```

If the script sends a message/error, it will be displayed on the Python screen that will open when executing the script.

#### pyCaptureDB.captureEfficiencyDI function

Its usage is described in the scripts within the **example scripts** directory. This function is also utilised in the Graphic User Interface: **calculatorGUI**.

## Setting the path for the pyCapture package

Currently, the tools/scripts provided will find the right path of the package `pyCapture` as a relative path to the scripts in the repository. This is performed with the use of the function `sys.path.append` within the scripts. This allow the scripts/tools to find the package and work properly. Nevertheless, the `pyCapture` package has not been installed as a package ready to be used by any other python application.  

If you decide to change the relative paths between the package and the scripts, for example when writing your own python tool that will make use of pyCapture, then you will need to re-define the path of the pyCapture package inside your script. You can also make use of the different methods available to allow python scripts to find and import packages. For example, we recommend the use of a [path configuration file.](https://docs.python.org/3/library/site.html)

