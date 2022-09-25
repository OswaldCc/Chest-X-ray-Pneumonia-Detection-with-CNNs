# Chest-X-ray-Pneumonia-Detection-with-CNNs

![hello](https://github.com/fredtush/dsc-text-classification-lab/blob/master/images/pneumonia.png)

# Navigation

* [Project Overview](#Project-Overview)
* [Preprocessing](#Preprocessing)
* [Model Analysis](#Model-Analysis)
* [Conclusion and Recommendation](#Model Conclusion and Recommendation)

# Important Links

* [Link to Data](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)

* [Colab Notebook Full Modeling Process](https://colab.research.google.com/github/OswaldCc/Chest-X-ray-Pneumonia-Detection-with-CNNs/blob/main/index.ipynb#scrollTo=gXmIwx8t91uE)


# Project Overview
Pneumonia is a serious lung condition that can be brought on by bacteria, viruses, or fungus. When someone has pneumonia, the alveoli (air sacs) are filled with fluid and pus, which makes breathing unpleasant, difficult, and restricts oxygen intake (reduced oxygen saturation). According to the WHO, pneumonia caused 14% of all deaths among children under the age of five in 2019. Both young people and the elderly are susceptible. A patient's clinical examination is used to diagnose pneumonia.

Machine learning in healthcare reduces the possibility of doing an improper examination. Therefore, putting in place a methodology that would enable pneumonia detection more precisely utilizing chest X-ray pictures, is vital. A machine learning algorithm sift through a vast amount of data to learn the most likely diagnosis, this would give patients more confidence in the diagnosis they receive.


# Preprocessing

In order to preprocess the images, use of Keras' ImageDataGenerator to rescale the images' pixels (to a scale of 0 to 1), and resized the images to 156 x 156 px. Even though the x-rays seem to be in grayscale, their actual sizes have all 3 layers of a colored photograph (rbg). Thus, they remain untouched instead of converting them to grayscale. Below are two of the preprocessed images.
                  
    
## Metric Used

The algorithm will be considered a success if the predictions made by it have a:

1. Recall above 95%
2. Accuracy of 90% - 96%

The task is to build a model that can classify whether a given patient has pneumonia given their chest x-ray image.

Since this is an Image Classification problem, Deep Learning is the ideal solving method.


## Model Validation
After running 3 iterations, it becomes easier to pick a final model to work with.

Here are the perfomance scores for the final model:

        Runtime = 36.481 seconds

        Recall: Train - ~98.9%, 

        loss: Train - 0.0689, 

        Accuracy:  ~79%, 
                   
Visualizations of the final model scores are as below:
   
![finalmodel](https://github.com/fredtush/dsc-text-classification-lab/blob/master/images/finalmodel.png)


Using transfer learning to challenge the solution the following scores were obtained:

        Runtime = 144.021 seconds

        Recall: Train - ~97%, 

        loss: Train - 0.1059, 

        Accuracy:  ~95.86%, 

The scores can be visualized as below:

![avvgmodel](https://github.com/fredtush/dsc-text-classification-lab/blob/master/images/avvg.png)

## Model Conclusion and Recommendation

The sensitivity of detecting pneumonia by emergency medicine specialists and radiologists <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6377225/#:~:text=Sensitivity%20of%20plain%20chest%20radiography,radiation%20(9%2C%2010).">this paper</a> is 83%, therefore:

Given that the model has 98% sensitivity, interpretation of chest x-rays using this Convolutional Algorithm might help in improving the diagnostic accuracy of pneumonia.
The algorithm is fast (36s) hence will increase efficiency considering the current understaffing in the Hospital.

Based on the scores above the model can be deployed for use in the hospital.
