
Analysis scripts of calcium imaging in locomoting mice 
==============================

The repository contains custom written Python scripts used to extract calcium transients during forced locomotion. 

The here published python scripts implement the steps and calculation to obtain **locomotion fluorescence** as depicted in Fig. 3 
 of the publication below. 


For more details, please refer to :

**Jinn Bao, Michael Graupner, Guadalupe Astorga, Thibault Collin, Abdelali Jalil, Dwi Wahyu Indriati, Jonathan Bradley, 
Ryuichi Shigemoto and Isabel Llano (2020).**
***Synergistic action of metabotropic and ionotropic glutamate receptors in cerebellar molecular layer interneurons in vivo.*** 


Individual analsyis steps and scripts 
-----------

Experiments were done on **four different animals** in **five different recording sessions**. All animal specfic settings and analysis 
parameters are stored in the ```animalSettings.py``` file. 

### Alignment of images : ```python alignImages.py```

This scripts uses the average image before and after drug application. 

```python
python alignImages.py
```

Change parameters and re-produce Figures
-----------

**PNAS 2012:**
The parameter values for the stimulation protocol can be changed in `Graupner2012PNAS_FigXX.py` (with XX=2,3 or 4B). Equivalently, the parameters of the plasticity model implementation can be changed in  `synapticChange.py` . The png and pdf versions of the figures can be produced by running the scripts
```python
python Graupner2012PNAS_Fig2.py
python Graupner2012PNAS_Fig3.py
python Graupner2012PNAS_Fig4B.py
```

**J Neurosci 2016:** The data has to be first calculated by running `irregularPairs_Ca-Model.py` for the linear calcium dynamics model and `irregularPairs_nonlinear-Ca-Model.py` for the nonlinear calcium dynamics model. For the linear calcium dynamics model, the calcium integral is calculated semi-analytically in a C++ program, which has to be compiled first by running `make` in the `timeAboveThreshold` directory. The compound figures are subsequently generated by the scripts `Graupner2016JNeurosci_linearCaModel.py` and `Graupner2016JNeurosci_nonlinearCaModel.py`. In other words, the png and pdf versions of the linear calcium dynamics figures can be produced by running the following two scripts
```python
python irregularPairs_Ca-Model.py
python Graupner2016JNeurosci_linearCaModel.py
```

Equivalently, for the nonlinear calcium dynamics model
```python
python irregularPairs_nonlinear-Ca-Model.py
python Graupner2016JNeurosci_nonlinearCaModel.py
```

Equivalently, for the calcium dynamics model with short-term plasticity for the somatosensory cortex plasticity data (Markram et al. 1997, Science)
```python
python irregularPairs_stp-Ca-Makram-Model.py
python Graupner2018_STPMarkramCaModel.py
```

Or for the calcium dynamics model with short-term plasticity for the visual cortex plasticity data (Sjoestroem 2001, Neuron)
```python
python irregularPairs_stp-Ca-Sjoestroem-Model.py
python Graupner2018_STPSjoestroemCaModel.py
```

Requires
-----------
Standard python packages such as **numpy**, **scipy**, **pylab**, **time**, **os**,  **sys** and **matplotlib** are required.

License
-----------
This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

