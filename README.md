# uno_recognition_computervision
Computer vision software able to identify UNO cards in images and camera streams.

CHANGELOG:

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






