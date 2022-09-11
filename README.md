# Face Synthesis with Demographics Background
This repository comprises the Face Synthesis with Demographics Background implementation. The repository is sorted as follows

* Data labels: we provide the 70,000 labels used for training the models
* Embeddings: comprising the IR-SE-50 model that generates the latent space
* Face Synthesis: it has a pre-trained models to synthetize faces in a jupyter file

1. Data labeling

We labeled the [FFHQ](https://github.com/NVlabs/ffhq-dataset) dataset using four main ethnic groups to separate the data. The process was manually done estimating the person's age, gender and ethnicity. We kept the original data structure and create a CSV file with the labels. 

| File      | Gender | Age | Ethnicity |
|-----------|--------|-----|-----------|
| 00070.png | M      | 1   | Latin     |
| 00619.png | M      | 60  | White     |
| 04916.png | F      | 22  | Asian     |
| ...       |        |     |           |
| 07553.png | M      | 7   | Black     |

The labels can be downloaded from here: [URL](https://drive.google.com/drive/folders/1cUHLpnaJqzMsoI_JgQF9fi31LozIyDy1) (FFHQ_Demographics.csv)

2. Embaeddings

We provide the code to generate the [IR-SE-50](https://github.com/ZhaoJ9014/face.evoLVe) feature space and run the embedding evaluations. The code to generate the plots from the training FID observed in the process is also included. We also provide the code to train the synthesizer. The sample figure below shows the feature space using T-SNE.

<img src="https://github.com/kopepod/DemographicFaceSynthesis/blob/main/TSNE_FFHQ_IRSE50.png" width="1300" height="380" />

From left to right the TSNE Embedding using labels: gender, ethnicity and age. The code to generate the plots is avaiable here: [URL](https://drive.google.com/drive/folders/1cUHLpnaJqzMsoI_JgQF9fi31LozIyDy1) (Embedding.ipynb). 

3. Face Synthesis

We provide a virtual environment in colab using conda to synthesize a face from the trained models. It is also given the framework to generate other faces from the labeled ethnic groups by only replacing the respective models' files. The jupyter file is available here: [URL](https://drive.google.com/drive/folders/1cUHLpnaJqzMsoI_JgQF9fi31LozIyDy1) (FaceSynthesis.ipynb). The figure below shows an example of face generated from a supervised group Latin Females.

<img src="https://github.com/kopepod/DemographicFaceSynthesis/blob/main/GFL.png" width="256" height="256" />



