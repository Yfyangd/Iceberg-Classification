# Iceberg-Classification
It is my final project of Udacity (Capstone). The object of my research is to classify icebergs and ships from the satellite image. During the winter and spring, drifting icebergs in the North Atlantic ocean present threats to navigation and activities in areas such as offshore of the east coast of Canada. It poses a risk to people's lives and oil and gas equipment, as well as present challenges to shipping and other activities. The Current method for monitoring iceberg conditions is aerial reconnaissance, supplemented by platform and vessel-based monitoring. However, in remote areas with particularly harsh weather, these methods are not feasible, and the only viable monitoring option is via satellite. The data in this paper was detected by synthetic aperture radar (SAR) from Sentinel-1,which is a space mission funded by the European Union and carried out by the ESA within the Copernicus Programme. After detection, additional processing is needed to distinguish between ships and icebergs. The discrimination between the two classes is carried out through feature extraction and target classification steps.


This study proposes the application of Convolutional Neural Networks (CNN) for ship-iceberg discrimination in high resolution Sentinel-1 StripMap images. The data was collected from Kaggle - iceberg classifier challenge. The CNN model is compared with a Random Decision Forests/Support Vector Machine (SVM)/Adaptive Boosting/eXtreme Gradient Boosting, and the result indicate a superior classification performance of the proposed method.

## Data Description
* `Iceberg Classification.ipynb`: My research in jupter notebook, include of EDA, feature extraction, data visualization, model training
* Forder of `Input`: The image with json file. Due to capacity limitations, the original data was not put in.

## Evaluation Metrics
This study used three indexes to calculate performance of the model: precision, recall, and F-score. The final result will be decided by the F-score with β = 0.5.

## Experiment Design
* Data Pre-process: Dropping the missing data, normalizing numerical features, and transforming skewed continuous features.
* Initial Model Evaluation: Before data engineering, we will properly evaluate the performance of each model (SVM, Adaboost, XGBoost, CNN).
* Feature Extraction: In CNN, the feature can be extracted in convolution process. In supervised learning (SVM, Adaboost, XGBoost), the feature will be extracted by statistics.
* Model Tuning: To improve performance, we will use GridSearchCV by Scikit-learn to find the optimization parameters in each supervised learning model.
* Data Augmentation: We added more data to train set by simple way including horizontally and vertically flipped data.

Finally, based on the above processes, we will evaluate the performance of each model and choose the best as the result of this study.

## Result
Compare with 4 methodologies, beyond all doubt, the CNN model is the best classifier in the Iceberg classification problem, even that the CNN performance in initial model (0.9172) is good than all the final supervised learning model (around 0.81~0.85). The final test show that the F-score of CNN is 0.9304, this is higher than what I expected.

| Methodology | Benchmark Model | Data Preprocess | Data Extraction | Data Augmentation/Optimized Model |
| :--: | :--: | :--: | :--: | :--: |
| SVM | 0.7331 | 0.6514| 0.5805 | **0.8424** |
| AdaBooster | 0.7331 | 0.7711| 0.7860 | **0.8105** |
| XGBooster | 0.7331 | 0.7933 | 0.8248 | **0.8501** |
| CNN | 0.7331 | 0.9172 | 0.9172 | **0.9304** |
