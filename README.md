# Handwritten Line Text Recognition using Deep Learning with Tensorflow
### Description
Use Convolutional Recurrent Neural Network to recognize the Handwritten line text image without pre segmentation into words or characters. Use CTC loss Function to train.

### Why Deep Learning?
![Why Deep Learning](images/WhyDeepLearning.png?raw=true "Why Deep Learning")
> Deep Learning self extracts features with a deep neural networks and classify itself. Compare to traditional Algorithms it performance increase with Amount of Data.

# Requirements
1. Tensorflow 1.8.0
2. Flask
3. Numpy
4. OpenCv 3
5. Spell Checker `autocorrect` >=0.3.0 ``pip install autocorrect``

#### Dataset Used
* IAM dataset download from [here](http://www.fki.inf.unibe.ch/databases/iam-handwriting-database)
* Only needed the lines images and lines.txt (ASCII).
* Place the downloaded files inside data directory  

###### The Trained model is available and download from this [link](https://drive.google.com/file/d/10HHNZPqPQZCQCLrKGQOq5E7zFW5wGcA4/view?usp=sharing). The trained model CER=8.32% and trained on IAM dataset with some additional created dataset.


To Train the model from scratch
```markdown
$ python main.py --train

```
To validate the model
```markdown
$ python main.py --validate
```
To Prediction
```markdown
$ python main.py
```

Run in Web with Flask
```markdown
$ python upload.py
Validation character error rate of saved model: 8.654728%
Python: 3.6.4 
Tensorflow: 1.8.0
Init with stored values from ../model/snapshot-24
Without Correction clothed leaf by leaf with the dioappoistmest
With Correction clothed leaf by leaf with the dioappoistmest
```
**Prediction output on IAM Test Data**
![PredictionOutput](images/IAM_dataset_Prediction_Output.png?raw=true "Prediction Output On Iam Dataset")

**Prediction output on Self Test Data**
![PredictionOutput](images/PredictionOutput.png?raw=true "Prediction Output on Self Data")

<i>See the project [Devnagari Handwritten Word Recognition with Deep Learning](https://github.com/sushant097/Devnagari-Handwritten-Word-Recongition-with-Deep-Learning) for more insights.</i>
# Further Improvement
* Using MDLSTM to recognize whole paragraph at once [Scan, Attend and Read: End-to-End Handwritten Paragraph Recognition with MDLSTM Attention](https://arxiv.org/abs/1604.03286)
* Line segementation can be added for full paragraph text recognition. For line segmentation you can use A* path planning algorithm or CNN model to seperate paragraph into lines.
* Better Image preprocessing such as: reduce backgoround noise to handle real time image more accurately.
* Better Decoding approach to improve accuracy. Some of the CTC Decoder found [here](https://github.com/githubharald/CTCDecoder)  

Feel Free to improve this project with pull Request.


*This is part of my last semester project of Computer Engineering From Tribhuvan University. July 2019*
