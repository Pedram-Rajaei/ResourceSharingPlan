<h1>Multi-Modal Dynamical Coherence Analysis (MDCA)</h1>

<h2>Description:</h2>
  Numerous studies of brain activity across a wide range of cognitive tasks and conditions suggest that rhythmic neural activity is organized precisely and context-dependently at multiple scales. Data analysis methods that capture network-level rhythmic dynamics are crucial for advancing our understanding of both healthy and pathological brain functions. To support this, we developed the LDCM toolbox.

  In developing LDCM, we hypothesized that neural circuits can be identified by examining the full cross-spectral matrix (CSM) between neural sources—either through explicit or implicit characterization—and by identifying a small set of eigenvectors that serve as proxies for functional circuits. These eigenvectors capture the majority of co-variability in the data. The resulting estimated circuit structure is termed the "functional eigenmodes" of the system, with the associated eigenvalues characterizing the degree of engagement or disengagement of each circuit during cognitive tasks or in response to stimuli.

  LDCM is an open-source toolbox written in Python, offering a comprehensive modeling pipeline that includes model selection, simulation analysis, model identification, and validation processes. To facilitate analysis, LDCM provides multiple step-by-step examples that align modeling hypotheses with their implementation in the code. Additionally, the toolbox includes a manual explaining the theoretical foundations of each modeling approach and providing detailed instructions for using the functions.

  LDCM is valuable for both experimental and theoretical neuroscientists, as well as researchers interested in studying brain function in conjunction with cognition and information processing. It also offers tools for clinicians and scientists investigating the connection between the brain and pathological states. While a basic understanding of neuroscience, dynamical systems, and functional connectivity is recommended, we strive to integrate this knowledge within the explanations of every example included in the toolbox.

<h2>Quick start:</h2>
  In the MDCA project, we provide different methods that we develop to characterize and analyize brain signals. We applied our methodologies on real data and parts of results are provided here. In the below, a short description foreach methods that is presented.

<h3>State Space Coherence:</h3>
    In State Space Coherence (SS-Coh) project, we provide mor robust algorithm for estimating Global Coherence (GCoh). To understand some aspects of SS-Coh modelling, you can read EMBC-2019 and bioRxiv-2020. In the RO1 proposal, we provide more complete modelling of SS-Coh. The complete description of the experimental protocol can be found in Purdon et al.

<h4>Data</h4> 
  To assess SS-Coh model, we use EEG data from human patients under general anesthesia. The data set was collected in Emery Brown’s laboratory.

  The complete description of the experimental protocol can be found in Purdon et al .. Briefly, ten consenting human volunteers of ages 18-36 years were impaneled for the study approved by the MGH Human Research Committee. For each subject, the induction and emergence from propofol anesthesia were studied by administering a computer-controlled (StanPump) infusion of propofol using the target control protocol based on the Schnider pharmacokinetic-pharmacodynamic model, while the subject executed a behavioral task to identify the points of loss and recovery of consciousness. Neural activity was recorded from 64 channels of EEG at a 250 Hz sampling rate. The anesthesia data is publicly available at the following link: Anesthesia Data.

Using this dataset, we will study the causal relationship between propofol blood concentration, level of consciousness, and spatio-temporal patterns of functional connectivity. Spectrograms, sliding window GCoh, and LDCM will be applied to identify network modes and their changes associated with loss of consciousness.

<h4>Results</h4> 
In the below we provide some results of SS-Coh model when we run it on the Anesthesia data set. In these results, We applied the SS-GCoh model to the anesthesia data (Fig. 1); the inferred results suggest that the functional circuit changes during different phases of the experiment reliably encode underlying consciousness states. The inferred functional connectivity using SS-GCoh along with its temporal changes not only corroborates the empirical results in Purdon et al ., but also tracks the dynamics with a finer temporal resolution

**SS-GCoh analysis in Alpha band for anesthesia EEG data and its correspondence with empirical results.**
A) Inferred unconsciousness state estimation over 2 hours of anesthesia. The latent state represents the unconsciousness level; the state transition is modeled by a random-walk model. B) Scalp heat-map of the dominant eigenmodes for 3 different time points during the experiment. The result using SS-GCoh and empirical measures are similar to each other. C) Empirical GCoh and inferred GCoh using SS-GCoh. Not only the inferred coherence matches the empirical one; it attains it at a finer temporal resolution. With SS-GCoh, we also derive higher-order statistics of the coherence such as confidence interval.

**Goodness-of-fit analyses and maximum likelihood (ML) curve**
A) Whitening transformation in the anestheisa shown for a pair of channels given initial settings of model parameters. (B) Whitening transformation shown for the pair of channles shown in (A) with trained model. It is clear that the model has captured dynamics present in data. (C) ML curve – or maximum of Q function – for different iterations of EM. The curve grows per iteration getting to a local maximum.

<h4>Implementation</h4> 
To get similar results, you can run provided code. After running GMM code, you will obtain the same result that we provide in above figures
<h3>Latent Dynamical Coherence Model:</h3>
In our previous work, we demonstrated a latent dynamical modeling framework called state-space global coherence, which characterizes spectral measures to capture slow-changing dynamics in network-level coherence. In this research, we develop a more general class of the state-space coherence model, that can capture fast and switching changes in the network-level rhythmic dynamics. For this framework, we assume both continuous and discrete latent processes derive the network-level rhythmic dynamics; this modeling assumption, will help us to build a more flexible model structure that can capture sophisticated dynamics present in the neural data. Below figure shows how we combine both continuous and switching dynamics in the model.

<h4>Data</h4>
To assess SS-Coh model, we use EEG data from human patients under general anesthesia. The data set was collected in Emery Brown’s laboratory.

The complete description of the experimental protocol can be found in Purdon et al . . Briefly, ten consenting human volunteers of ages 18-36 years were impaneled for the study approved by the MGH Human Research Committee. For each subject, the induction and emergence from propofol anesthesia were studied by administering a computer-controlled (StanPump) infusion of propofol using the target control protocol based on the Schnider pharmacokinetic-pharmacodynamic model, while the subject executed a behavioral task to identify the points of loss and recovery of consciousness. Neural activity was recorded from 64 channels of EEG at a 250 Hz sampling rate. The anesthesia data is publicly available at the following link: Anesthesia Data.

Using this dataset, we will study the causal relationship between propofol blood concentration, level of consciousness, and spatio-temporal patterns of functional connectivity. Spectrograms, sliding window GCoh, and LDCM will be applied to identify network modes and their changes associated with loss of consciousness.
<h4>Results</h4>
  Below figure shows how using of switching mechanism in the LDCM improves the accuracy of estimation in compareison with SS-Coh model.

  **LDCM Application in Anesthesia Data .**
  **A)** These figures show the inferred GCoh by SS-Coh, LDCM with 2 switches, and LDCM with 3 switches. The time intervals of different switches are shown with blue, red, and greeen colors for the first, second, and third switch, respectively. The black line shows the empirical GCoh. The inferred GCOh using LDCM with 3 switches follows the empirical GCoh with a higher level of accuracy, where we can observe a clear bias in the SS-Coh. The scatter plots on the right, predicted GCoh vs empirical GCoh, also show this bias in SS-Coh, which is compensated as we embed switching process in our modeling of coherence dynamics. In each scatter figure, the correlation is shown. The best score is for LDCM with switches and it shows the better performance of this model. **B)** The scalp heatmap using the dominant eigenvector of CSM at time 45 minutes of experiments derived using empiricial, SS-Coh, LDCM with 2 switches, and LDCM with 3 switches, from left to right. The empirical one shows a strong frontal activity in (Alpha) band through the transition from consciousness to unconsciousness; the result in LDCMs with 2 and 3 switches are significantly close to the empiricial one, where the SS-Coh inferred functional modes do not resemble the empirical one.

  <h4>Implementation</h4> 
To get similar results, you can run provided code. After running GMM code, you will obtain the same result that we provide in above figures
<h3>Switching Dynamic:</h3>

<h3>Stringer Data:</h3>

<h3>Amygdala Data:</h3>

<h2>Philosophy:</h2>
  Our core effort in developing this toolbox is to promote open science. Open science fosters transparency, accessibility, and collaboration in research by encouraging the open sharing of data, methodologies, and results. By making scientific knowledge freely available, enhancing reproducibility, and fostering a more inclusive and collaborative scientific community, open science aligns with our goals for the MDCA toolbox. We aim to contribute to democratizing science, improving research quality, and involving the public in scientific endeavors. In particular, we have focused on the following aspects in our tool development:

  <h3>Ease of use:</h3> End-users of MDCA may come from diverse backgrounds with limited focus on stochastic and statistical modeling. To address this, we provide clear explanations of the science behind each function in simple terms, along with visual and step-by-step instructions in the manual and code examples. This approach aims to increase the usability of the toolset for a broader audience.
  
  <h3>Scalability:</h3> Brain activity is captured through various modalities, and as science and technology advance, the size and resolution of these recordings grow. Consequently, we emphasize building tools that can scale effectively as data size and modalities increase. We discuss how the toolset can be run on cloud platforms and provide modeling mechanisms, including parcellation and bootstrapping techniques, to handle large datasets.

  <h3>Integration with Other Tools:</h3> Many toolsets are developed with objectives similar to ours, and others are used for source representation, data cleaning, and augmentation. Through examples, we demonstrate how our modeling pipeline can work in tandem with other tools, enhancing its usability and scalability.
  
  <h3>Connection with Data Repositories:</h3> NIH has made significant investments in open science, including publicly available datasets. Our toolbox includes utility functions for compatibility with data formats used in these repositories and generates results that can be transferred to these environments. We also discuss how our toolset can be integrated with other analysis platforms for easier translation and use.
  
  <h3>Linking with Visual Results:</h3> Visualization plays a critical role in neuroscience research. We are developing utility functions to integrate visualization tools into our toolbox, allowing results to be demonstrated effectively. Additionally, functions will be included to save results in formats compatible with other visualization tools.

  <h3>Scientific Dissemination:</h3> We will present the toolset at various conferences, including but not limited to SFN. Demo videos will be made publicly available on our GitHub repository and platforms like YouTube. We will publish our modeling theories and any related scientific discoveries in scientific journals and conferences.
  
<h2>Demo:</h2>

<h2>More information:</h2> For further information about the toolbox or to provide suggestions, please contact Ali Yousefi at aliyousefi@uh.edu.

<h2>Contribution:</h2> This toolbox was developed through the collaborative efforts of the Yousefi Lab at the University of Houston, the Eden Lab at Boston University, and the Emery Brown Laboratory at MIT.

<h2>Acknowledment:</h2> This research was supported by NIH grant XXXX. We would like to thank our research collaborators for their contributions in evaluating the toolset and providing insightful feedback. Our research collaborators are:
1.	Catherine J. Chu, Mass. General Hospital and Harvard Medical School
2. Mark Richardson, Mass. General Hospital and Harvard Medical School
3. Alik S. Widge, University of Minnesota
4. Earl K. Miller, MIT
5. Mriganka Sur, MIT
6. Christopher I. Moore, Brown

<h2>Future work:</h2> This is ongoing research, and we are seeking collaborations to expand our efforts. For potential collaborations or to share comments and feedback, please reach out to Ali Yousefi at aliyousefi@uh.edu.
