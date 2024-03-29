# machine-learning-in-LiDAR-3D-point-clouds

This project is an implementation of the paper of F. Patricia Medina & Randy Paffenroth, [machine-learning-in-LiDAR-3D-point-clouds](https://arxiv.org/abs/2101.09318).

### Objective:
I tried to replicate the work done by F. P. Medina et al. to get a better understanding of the Lidar data 

### Data:
I used IGN (French National Geographic Institute) [LidarHD data](https://geoservices.ign.fr/lidarhd) from Côtes d'Armor (West of France).

### Steps:
For this short project, I went through the following steps :
- Exploration of the dataset
- Preprocessing of a sample of the dataset (500 000 points) and feature engineering like described by F. P. Medina et al. (including nearest neighbors concatenation, sdandard scaling, normalizing and dimension reduction with PCA)
- Training and evaluating of a Random Forest Classifier model
- Training and evaluating of a simple two-layer deep neural network model

### Results:
The random forest seems to perform better than the neural network while the results in the paper show the contrary. This difference may be explained by different reasons :
- My dataset and theirs are different
- F. P. Medina et al. use the features return_number and number_of_returns while In my dataset, I have nan values for these features. It could be interesting to study the impact of the different features on the prediction.


I noted an important effect of the unbalance of the dataset so I tried to undersample dominant categories. I happens that it has an overall negative effect on the main metrics (precision, recall, f1) for both the random forest and the neural network. 

### Note: 
Please note that since this projet was a simple way for me to get a better understanding of the Lidar data, I did not try all the things the authors tried (for instance deep auto-encoder to do dimension reduction as it was indicated that it performed worse than PCA) 
