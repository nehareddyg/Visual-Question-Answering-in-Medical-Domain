Authors: G Neha (nehareddyg) & Meghana Kotagiri (meghanakotagiri) 

As mentioned in our report:
Training Dataset=VQAMed2018Train
Test Dataset=VQAMed2018Valid
of ImageCLEF 2018.

Steps to run the code:
1) Download tensorflow version of VGG model that will be used for feature extraction by the file below.
   Link: https://drive.google.com/file/d/0B2vTU3h54lTyaDczbFhsZFpsUGs/view.

2)"feature_extraction.ipynb": Run this code once for images in the training dataset and once for test
   dataset. The filenames have to be changed accordingly (please see the comments for help). This script should generate pickle file withe extracted image features for given dataset.

3)"Preprocessing Q&A.ipynb": This script preprocesses the text (Question and answers) and create other 	  auxilary datastructures (word_to_idx etc.). It takes input: 'VQAMed2018Train-QA.csv' and  
  'VQAMed2018Valid-QA.csv'. The output of this code should generate 6 files:
   i)   train_df_final.pkl : Preprocessed Q/A of training dataset
   ii)  image_feature_train.pkl : Preprocesses features of training dataset
   iii) word_to_idx.pkl : Dictionary that maps word to its index in vocabulary
   iv)  idx_to_word.pkl : Dictionary that maps index in vocabulary to the word
   v)   image_feature_test.pkl : Preprocesses features of test dataset
   vi)  test_df_v_final.pkl : Preprocessed Q/A of test dataset

4)"Model.ipynb": Takes as input all the above 6 files. Contains code for buling, training and testing  
   the model. It finally outputs BLEU score on test dataset.
