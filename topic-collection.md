- sampling needs differ
  - training vs. validation vs. application representative
  - e.g. calibration training => uniform sampling good heuristic (ref IIRC Tom's NIRS book)
  - calibration samples to span large range => need much variance, no blending
  - application question (e.g. theobromine in Peruvian cocoa) needs representative for e.g. fermentation box => physical averaging (milling & mixing) good
  - validation -> validation paper?

   
- Which samples -> DoE
  - nested designs, variance components
  	- thinned out designs -> keep (some) increments separate
  	- chemometrics/stats: do we have weighting methods that allow flexible combining of pooled samples and samples that are single increments?
  	- trade-off sample size as in volume/mass vs. more small increments <-> ToS
  - sequential schemes, e.g. start with ≈ 40 % of experimental effort -> model -> refine DoE
  - uniform: select in spectra space similar samples to pool
  - use preliminary calibration (last harvest, initial few samples), and select samples for pooling from concentration space
  - other selection criteria: pool small (large) seeds => maybe higher/lower analyte concentration
  	- anyways good to check/know
  	- carefully consider application needs: need to detect high concentration independent of seed size ./. application allows to use size information for prediction
  - validation: what are the right samples/sample groups/subpopulations to probe?
  	- (good) validation samples sometimes hard to get, e.g. in authentication
  	- how valid is the assumption that training heterogeneity/variance is representative for production use
  	  - obvious deviation: lab-prepared calibration samples for method to be used in e.g. industrial production environment
  	  - ref: semi-supervised paper
  - sometimes we can design samples, e.g. lab-prepared (spiked) calibration samples
  - sometimes we can select suitable samples for reference analysis from a large set that is anyways spectroscopically measured
  - sometimes all one can do is to take what is available
  - augmentation / in.-silico sampling?
  	- simulate influence of known effects (e.g. Raman wavelength shift due to laser diode temp)
  	- machine/deep learning community uses this for training,
  	- for validation compare bolstering
  	- use existing data-bases (@Marina; @Jean-Michel: spectra transfer)
  - calibratino range recommendations, e.g. 1 order or magnitude, or target ± 20 %
  - are there any differences in recommendations for full-spectrum measurements vs. a few wavelengths only?
  	- particular DoEs/sampling considerations for selecting (few) wavelengths?
  - randomization/blocking/stratification

- How many -> DoE & ToS
  - heuristic: for measuring/monitoring variance, better have duplicates of more primary samples rather than many replicates for few samples
  - duplicates every so often typically sufficient for monitoring. 
  - for reducing variance uncertainty in analysis results => number of replicates
  - trade-off: sample/portion/increment size vs. number of replicates
  - training: sample size relative to model complexity and number of variates relevant
  - verfication & validation: absolute number of tested cases relevant
  	- classification proportions: variance mathematically tied to value and number of test cases in denominator, allows back-of-the-envelope calculation => sample size planning.
  	- other figures of merit, regression: variance uncertainty can only be calculated after the experiment.
- How to get representative samples -> ToS
  - optical geometry of sensors: spectroscopic sensors may measure in a way that is inherently not ToS compliant, e.g. signal depends on location/distance from sensor
  - Volume difference between NDSS and (wet) macro reference analysis
  - (may only be possible to outline unsolved problem)
  - check with data fusion paper
  - if spectroscopic measurement volume << reference method volume:
  	- "pooled" samples will have average content => do not span spectrosopcic calibration range
  	- how to trade off higher error of reference method for smaller ("too" small sample) but better overlap wiht spectroscopic measurement?
  	- some applications do not need "full"/proper quantitation, e.g. breeding: selection of elite group still possible if prediction is only proportional to reference method (e.g. micro extraction vs. water vapor destillation )
	- process monitoring: similar in time: we may have different time resolution for reference and spectroscopy
	- resolution has two components, "spot" size and "spot" spacing
	- how well is the alignment reference <-> spectrum (for all: image, PAT, "single" samples)
  - can NDSS be used to assess heterogeneity ?
  	-  spectra/image collection is fast, much more increments can be acquired, without measuring any analyte it will nonetheless be possible to explore spectra variability which can highlight regions of higher variability which may indirectly reflect heterogeneity and thus guide where to do the refrence analysis Many
  	- spectroscopic variogram?
- Application scenarios
  - Information on heterogeneity available
  - Information on heterogeneity not available
  - use particle size –ToS→ minimum increment size -> guesstimate no. of FS increments -> keep separate to obtain heterogeneity estimate as result
  - sampling of leaves/flowers/fruits, remaining parts to be kept undisturbed & plant stays alive
    - example: spilanthes
  - Crushing/grinding and/or mixing not possible
    - example: cacao beans, caraway (?)
  - Restriction on total volume of field sample increments
    - heuristic: more smaller (but within ToS-compliant minimum) increments better
    - cacao beans
  - obtaining calibration/validation sample sets spanning wide calibration range
    - we deliberately want as heterogeneous a sample set as possible since that gives wide calibration range/good coverage of input space
    - at the same time, we want to answer application question, thus need good representative samples of application. They tend to be more average.
    - NDSS typically measure small volume => subject to high heterogeneity. 
    - reference analysis often requires large volume => average sample of many NDSS measurement volumes => closer to average
    - So how (which) to combine small (NDSS) increments into large reference sample? 
      - Select clusters of spectroscopically similar increments (?)
      - Pre-calibration needed? when?
  - Many samples measured with NDSS, few can go to reference analysis
    - how to choose
    - how to split for training / validation


jasenka: 
- training validation -> micro instruments -> lab vs field -> accuracy differences, less data
- in situ vs lab -> non destructive vs. preparation

vincent:
- sampling step at laboratory
Ok, so I will write my suggestion.I think the paper has to demonstrate that NDSS are an elegant solution totackle sampling issue
To do that, we have to explain what sampling is and how NDSS are more suitable to take into account the heterogeneity of the samples
For me, "sampling" is different than "sample selection"
Sampling is the procedure to pick up sample from a batch
ample selection is the choose of sample to calib ou valid a method
[12:08] Vincent BAETEN (Gast)
    This is from our side
[12:08] Vincent BAETEN (Gast)
    In the paper we have to define clearly the aim of the paper
(1 „Gefällt mir“-Angaben)

beatriz
- field: how to sample a plot/field representatively
- harvest: how to sample

tassos:
- decide(?) do we tackle industry/government scale sampling or research studies?
  Beatriz says sensorFINT wants industry. Claudia says, industry does small scale studies as well. 
-  teaching module on food analysis -> sampling for chemistry
- 20 kg mozzarella for pizza -> bring into lab -> ASK students to do sampling -> complex problem
- need high level structure






