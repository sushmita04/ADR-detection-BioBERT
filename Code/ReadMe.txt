The above files are designed to be run in Google Colab.
Please follow the following steps to execute the programs:
1. Upload the contents of one of the folders present in this folder to Google Drive.
2. Open the .ipynb in Google Colab
3. Change the path in cell 5 to match the destination where the file(s) have been uploaded in Google Drive.
4. If text preprocessing is required, please make sure the file 'meddra_all_se.tsv' is uploaded to the specified path. The file is
   is present in the same folder as ReadMe.txt
5. Use the cells below the text section "Loading the needed csv files into a pandas dataframe" to change the files used
   for Training as per requirements
6. If a different file from the ones used in the original project are used, please follow the following steps(ignore
   if the same files are being used)
	i:if text preprocessing is required, find the cell below the text section 'Detecting the ADRs in the given text reviews', and
  	  change the 'Rating' value to the name of the column that contains the text reviews as per requirements. The file can then be 
	  saved by running the cell with the title 'Saving the text reviews with ADRS.'
	ii:if text preprocessing is not required, find the cell below the text section 'If text has already been preprocessed and ADRS
	   have been generated...', Change "Rating" to match the name of the column containing text reviews as per requirements.'
7. If a different file from the ones used in the original project are used, please follow the following steps(ignore
   if the same files are being used)
	i:In the section 'Utility functions to get the BIO sequence Labeling', Please change the 'Rating' value in get_tags to match 
	  the name of the column in your file containing the text data.
8. In the section 'Performing Train Validation Split and making dataloaders for the respective train and validation datasets', change 
   the value of test_size to change the ratio of train-test split as per requirements.(default value is set to 0.1)
9. In the main cell used for training the network (found after utility functions for training and testing one epoch), make the following
   changes as per requirements:
	i.: Change the value of 'lr' in optimizer to change the learning rate (default set is 0.00001)
	ii.: Change the value of 'weight_decay' in optimizer to change the weight decay rate (default set is 0.0001)
	iii.: Change the value of 'epochs' to change the number of epochs in training.
	iv.: Change the value passed to save_checkpoint in the last line to change the name with which the network will be saved and
	     the location where it will be stored.(default path is the path initialized in step 3 and names have been given in each of
	     the files based on the data on which the network was trained.)
10. In Testing, in the 'Loading the test datasets section', make changes as per requirements if different file(s) are to be loaded in
    for testing.
11. If text preprocessing and ADR detection is required for the test dataset, run the cell below the text section 'Text preprocessing 
    and ADR detection on training data'. Change the 'Review' column to match the column containing the text reviews in the test dataset.
    The user can then save the preprocessed test data along with their respective ADRS by running the cell with the title 'Save the
    preprocessed data with ADRS to save time during repeated execution of the program.'
12. If text preprocessing and ADR detection has already been done for the test dataset, we can run the cell with the title 'If text 
    is preprocessed and ADRS have already been detected.' Change 'Rating' to match the name of the column containing text reviews in 
    the testing dataset.
13. In the section 'Utility functions for BIO sequence labeling' in the testing part of the code, Please change the 'Rating' value in
    get_tags to match the name of the column in your file containing the text data.
14. If the testing code is being run separately, we can load a pre trained neural network by running the cell below the cell containing
    the function containing the definition of the 'valid' utility function. Change the value passed to 'load_checkpoint' to match the
    name and path where the trained model was stored.
15. In the section 'storing the results in a csv file', change the path and filename passed to 'df.to_csv()' as per requirements to save
    the predicted results.