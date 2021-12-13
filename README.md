# uno_recognition_computervision
Computer vision software able to identify UNO cards in images or folders and in real time from camera streams.
Available on GitHub at: https://github.com/CiprianFlorin-Ifrim/uno_recognition_computervision.git

Development Time: 110 Hours

The main code "UNO_computer_vision_MAIN" is able to:
- create datasets
- modify datasets
- create pickle classifier file
- replace picle classifier file
- identify uno cards in images
- identify uno cards in folders and tell accuracy on all cards
- identify uno cards live in real time from the camera stream.
All of this is done through a GUI.
Watching the video available in ./_tests_completed/demo.mp4 is recommended to understand how the code works and how to use the interface.

LIMITATIONS: 
- The MAIN code is able to identify ANY COLOURED UNO cards and ANY SHAPE from an image or folder. 
  As long as the card is placed on a surface that does not have extra objects around (the countour would have to be manually changed).
  
- The MAIN/CAMERA code is able to identify ANY SHAPE and BLUE/RED/YELLOW/GREEN colours live in real time from the camera stream. 
  Multiple cards can be identified at the same time.
  BOTH THE CAMERA AND MAIN CODE can recognise images that are both in vertical and horizontal, as well as flipped.
  The code is able to indentify ALL CARDS with a BUSY ENVIRONMENT/BACKGROUND(MANY OBJECTS), but if they are coloured red,yellow,green,blue they should not be close to the camera or big in size.
  The code is able to identify BLACK CARDS as well, however no other black objects should be present in the frame.
  NOTE: In the interface there is a slider called "SENSITIVITY" this should be used depending on the camera is the cards are not detected, or are detected too easily (too many contours for 1 card)
        In the CAMERA code the same process can be done by changing the "area_sensitivity = 8000" on line 6, 3rd cell.
		IT IS IMPORTANT TO NOTE THAT ALL CAMERAS HAVE DIFFERENT FOVs & HSV RANGES. SO MANUAL HSV ALTERATIONS MAY BE NEEDED!
  
- The PYTESSERACT code has been reverted to version 0.6 prior to the introduction of skip/reverse/plus2 cards, and is able to identify accurately digit uno cards from an image.
  Can reach 100% accuracy with vertical/horizontal images.
  Has low accuracy with flipped images compared to what it is expecting.
 
The software is divided into 3 sections:
	- Image UNO shape and colour recognition using Pytesseract;
	- Dataset creation/modification, classifier pickle file training/creation, images/folders/camera UNO cards colour+shape identification;
	- Camera file to be used in tandem with the saved classifier (Pickle) to be used as standalone

LIBRARIES USED: OS, TIME, MATH, OPERATOR, CSV, GLOV, CV2, PICKLE, NUMPY, PANDAS, MATPLOTLIB, TKINTER, PILLOW, SCIPY, SKLEARN, WEBCOLOURS
They should all be available with Anaconda Spyder with the exeption of:
		- WEBCOLOURS: conda install -c conda-forge webcolors
        - PYTESSERACT: conda install -c conda-forge pytesseract or pip install pytesseract combined with https://github.com/UB-Mannheim/tesseract/wiki
NOTE: Specify in the Pytesseract notebook where Pytesseract has been installed: example: pytesseract.pytesseract.tesseract_cmd = 'G:/Program Files/Tesseract-OCR/tesseract.exe'


DESCRIPTIONS for files in the main folder:
- _tests_completed: screenshots and videos of tests performed with UNO cards
	- uno_images_set1 percentage accuracy: screenshot of the Model identifing Eris's cards with accuracy %
	- uno_images_set2 percentage accuracy: screenshot of the Model identifing my cards set1 with accuracy %
	- uno_images_set3 percentage accuracy: screenshot of the Model identifing my cards set2 with accuracy %
- development code: old code used throughout the development process to reach this stage
- extracted_digits: used to check the Pytesseract accuracy
- uno_images_set1: Eris's full set
- uno_images_set2: my full set 1
- uno_images_set3: my full set 2
- dataset.csv: table containing the labels(first column) of the uno cards and their features(the rest 10 columns)
- menu.gif: used for the background of the interface
- randomforest_clf_optimised: Pickle saved trained classifier optimised with random search and grid search
- UNO_computer_vision_CAMERA: standalone code to be used in Jupyer Notebook with the pickle classifier
- UNO_computer_vision_MAIN: full main code able to create datasets, modify datasets, create/replace trained classifiers and identify UNO cards from images/folder/camera stream
- UNO_computer_vision_PYTESSERACT: standalone code to be used in Jupyter Notebook to recongnise cards using the OCR engine called Pytesseract


REFERENCES:
	- https://www.pyimagesearch.com/2021/01/19/opencv-bitwise-and-or-xor-and-not/
	- https://www.pyimagesearch.com/2015/04/06/zero-parameter-automatic-canny-edge-detection-with-python-and-opencv/
	- https://www.pyimagesearch.com/2016/05/30/displaying-a-video-feed-with-opencv-and-tkinter/
	- https://www.pyimagesearch.com/2016/05/23/opencv-with-tkinter/
	- https://www.tutorialspoint.com/using-opencv-with-tkinter
	- https://www.pyimagesearch.com/2016/05/23/opencv-with-tkinter/
	- https://www.pyimagesearch.com/2016/05/30/displaying-a-video-feed-with-opencv-and-tkinter/
	- https://www.geeksforgeeks.org/python-tkinter-messagebox-widget/
	- https://www.geeksforgeeks.org/how-to-use-images-as-backgrounds-in-tkinter/
	- https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74
    - Dr. Eris Chinellato from Middlesex University - OpenCV/SciKit Learn Jupyer Notebooks 
	- StackOverflow**∞


CHANGELOG:
Version 1.6 (12/12/2021):
Final version:
- added a proper interface with Tkinter
- improved certain parameters for random search and grid search
- improved the code and its response time

Version 1.5 (11/12/2021):
- added extra comments
- merged all 4 files into one single file
- added screenshots of text results
- 15 total changes
- fixed camera detection which was broken in 1.4
- improved HSV ranges
- improved accuracy on cards

Version 1.4 (10/12/2021):
- improved every single feature
- improved the colour accuracy
- can now recognise black cards without issues
- 15 total changes
- changed the parameters for the grid search
- retrained the model on 3 different sets to help with brightness levels and noise

Version 1.3 (08/12/2021):
- camera fully working
- improved centre detection
- improved the code and definitions
- added more comments

Version 1.3 (07/12/2021):
- started working on the camera module
- improved the feature space accuracy

Version 1.2 (06/12/2021):
- improved circle detection accuracy
- improved children detection accuracy
- improved colour range for the personally developed patch colour identification, so that it better detects colours, as well as detecting black now
- added a second method for colour detection using OpenCV Mask and Range
- implemented a menu so that the user can choose between the 2 colour identification methods
- tested the trained model on new cards and added them to a folder in the repo
- added random search+grid search optimisation processes to the random forest classifier model, for training accuracy improvement
- changed names of files to be easily identifiable 
- moved old code/files to a new folder called development_code


Version 1.1 (05/12/2021):
- multiple classifiers tested together and individually with their hyperparameters highly modified, both manually, as well as with grid search 
- added Pickle to save the classifier and then load again in the main code for prediction, after a few hours of testing, arrived at 94% highest accuracy

Version 1.0 (03/12/2021):
- feature space fully defined
- dataset csv file created
- testing different ML/NN models to check for the best classifier
- reworked the center cropping by using an ellipse masked feature

Version 0.9 (29/11/2021):
- added hough lines feature
- improved the center cropping
- soon to switch to the ML model fully

Version 0.8 (27/11/2021):
- working on having a fully defined feature space
- WIP accurate center cropping

Update (27/11/2021):
- stopped working on the Pytesseract code, switched fully to Machine Learning
- the Pytesseract code is able to recognise all colours and cards from 0 to 9 quite accurately

Version 0.7 24/11/2021):
- added skip, reverse, +2 cards identification
- better contour center point recognition
	- fixed the center crop issue from versions 0.6 downwards
- added different methods of achieving certain tasks (will be of use later when creating a menu/user interface
- changed/added comments
- added more sections/better code formatting
- WIP +4 card identification (not part of the original image folder)

NOTE: Some bugs with the skip/reverse/+2 if the cards are flipped from the beginning. Working on a fix!

Version 0.6 23/11/2021):
- changed some comments
- added extra comments
- fixed some commands
- flipped the changelog around so that the changelog goes from latest version to oldest

Version 0.5 (23/11/2021):
- fixed the problem where the digit was not recognized if the image was flipped:
	- now the software is "aware" on the orientation of the image and it flips it vertically, horizontaly or both in order to align it to the user origin
		- the flip happens for both the digit extraction image, as well as the user final image for ease of use
- fixed some variable mistakes
- added extra comments
- moved the digit recognition with pytesseract code into a definition which can get recall as needed throughout the code

NOTE: There is currently an error with the center cropping needed for shape identification with certain images! WIP!

Version 0.4 (22/11/2021):
- added digit recognition section with digit extraction as string/int 
- added digit extracted to uno card identification text placement
- modified center cropping coordinates
- changed morphology values used for a better result
- added contour extraction for the image used on digit recognition in order to calculate perimeter/area+vertices and detect reverse, skip, +4,+2 cards
- added extra comments

NOTE: There is currently a problem where if the image is flipped horizontaly or vertically, the digit will NOT be recognized. Working on a solution!

Version 0.3 (22/11/2021):
- fixed a bug related to image rotation (some images would get flipped not rotated)
- fixed a bug with the colour recognition section (some images would be recognized as cyan/navy rather than blue, to fix it I reduced the "accuracy", lighter-darker blue = blue)
- fixed a bug where the wrong images were loaded for post-processing because of the same address in memory
- researched pattern recognition and added comments to the document
- added pytesseract in tandem with OpenCV morphology+binarisation for digit recognition
- added more comments

NOTE: PYTESSERACT LIBRARY is now a must install, with a manual location override at the beginning of the file to specify the path.

Version 0.2 (21/11/2021):
- added separate camera stream file for debugging
- changed Jupyer Notebook cell width based on window resolution (now uses 100% of browser window)
- added Arduino map() definition to python
- imported extra necessary libraries (webcolors is now a required install)
- created a copy of the final pre-processing image in order to have a processing image and a colour analysis image (helps with contour issues)
- added a colour analysis section
- added a colour identification section:
	- the software can now recognite whether the uno card is blue,yellow,red,green
	- the frame around the displayed output will now change based on the card colour
- changed the colour identification from HSV processing to BGR processing
- modified text displacement values to better fit any cropped image
- added a lot of extra comments explaining every process
- added section separation text for a "chapter" view of the code


Version 0.1 (19/11/2021):
- first git push to the respository
- added anti-aliasing with cv2.LINE_AA on all drawn lines and placed text for smoother edges
- changed cv2.rectangle with cv.drawContours for better performance with rotated images
- changed image names for a better understanding
- added colour analysis definition 






