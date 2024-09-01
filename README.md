<h1>Multi-Modal Dynamical Coherence Analysis (MDCA)</h1>

<h2>Description:</h2>
  Numerous studies of brain activity across a wide range of cognitive tasks and conditions suggest that rhythmic neural activity is organized precisely and context-dependently at multiple scales. Data analysis methods that capture network-level rhythmic dynamics are crucial for advancing our understanding of both healthy and pathological brain functions. To support this, we developed the LDCM toolbox.

  
  In developing LDCM, we hypothesized that neural circuits can be identified by examining the full cross-spectral matrix (CSM) between neural sources—either through explicit or implicit characterization—and by identifying a small set of eigenvectors that serve as proxies for functional circuits. These eigenvectors capture the majority of co-variability in the data. The resulting estimated circuit structure is termed the "functional eigenmodes" of the system, with the associated eigenvalues characterizing the degree of engagement or disengagement of each circuit during cognitive tasks or in response to stimuli.

  LDCM is an open-source toolbox written in Python, offering a comprehensive modeling pipeline that includes model selection, simulation analysis, model identification, and validation processes. To facilitate analysis, LDCM provides multiple step-by-step examples that align modeling hypotheses with their implementation in the code. Additionally, the toolbox includes a manual explaining the theoretical foundations of each modeling approach and providing detailed instructions for using the functions.

  LDCM is valuable for both experimental and theoretical neuroscientists, as well as researchers interested in studying brain function in conjunction with cognition and information processing. It also offers tools for clinicians and scientists investigating the connection between the brain and pathological states. While a basic understanding of neuroscience, dynamical systems, and functional connectivity is recommended, we strive to integrate this knowledge within the explanations of every example included in the toolbox.

<h2>Quick start:</h2>
  <h3>Example:</h3>

  <h3>Installation/Usage:</h3>

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

<h2>Citting:</h2>

<h2>Acknowledment:</h2> This research was supported by NIH grant XXXX. We would like to thank our research collaborators for their contributions in evaluating the toolset and providing insightful feedback. Our research collaborators are:
1.	Catherine J. Chu, Mass. General Hospital and Harvard Medical School
2. Mark Richardson, Mass. General Hospital and Harvard Medical School
3. Alik S. Widge, University of Minnesota
4. Earl K. Miller, MIT
5. Mriganka Sur, MIT
6. Christopher I. Moore, Brown

<h2>Future work:</h2> This is ongoing research, and we are seeking collaborations to expand our efforts. For potential collaborations or to share comments and feedback, please reach out to Ali Yousefi at aliyousefi@uh.edu.
