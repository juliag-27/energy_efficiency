<h1> Overview </h1>
This project aims to estimate building energy efficiency using publicly available data, including street view images, aerial view images, building footprint, and satellite-derived Land Surface Temperature (LST). For ground truth labels, we rely on the EU’s EPC registry data. If results are reliable, such a model could be used to identify buildings – even general geographical areas – where buildings are energy-inefficient. This would be immensely useful for sustainable building initiatives and decarbonization plans. Such a tool would be immensely useful in quickly and cheaply identifying high-yield retrofits compared with traditional methods like on-site assessments. We chose this paper because of its potential societal benefits and because it would allow us to apply many concepts we’ve covered in class. The paper combines many different modalities of data as well as multiple types of machine learning models, giving us the chance to work across different techniques.


The data used in this study consists of images retrieved from Google Street View (GSV) and Aerial View (GAV), coordinates from OpenStreetMap building footprints, temperatures from Landsat-8 Land Surface Temperature (LST), and EPC ratings from the EU Energy Performance Certificate (EPC) registry.
The coordinate, temperature, and EPC ratings were already compiled in a dataset by the paper’s authors, however, we needed to download and clean the approximately 80,000 images representing 40,000 buildings separately. 


To preprocess these images, we used an embedder to encode them and k-means clustering to remove unhelpful images from the data (e.g., plain walls, obstructed views, unavailable buildings). After cleaning, we concatenated the embeddings with the rest of the structured data for their corresponding buildings.

We calculated the precision, recall, and F1 scores by running the models on the test dataset. The MLP head performed with a loss of 0.5770, precision of 0.6655, recall of 0.6858, and F1 score of 0.6736. On the other hand, the linear head performed with a loss of 0.5194, precision of 0.7163, recall of 0.5804, and F1 score of 0.5886.

Notably, we performed the same cleaning process as the authors on the already-cleaned data, yet were still able to remove about 5,000 images from the training dataset that were unavailable, blurry, or obstructed by foliage.

Link to our images, datasets, and ablation models: [https://drive.google.com/drive/u/1/folders/1bK4DHRNtNRBnrdUUTwhAXYmPOdJoqMPb](https://drive.google.com/drive/folders/1bK4DHRNtNRBnrdUUTwhAXYmPOdJoqMPb?usp=sharing)

![Poster](https://github.com/user-attachments/assets/b682e2a0-5e79-4523-bebf-fa08be70cb57)
