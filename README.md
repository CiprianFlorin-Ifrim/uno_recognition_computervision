# uno_recognition_computervision
Computer vision software able to identify UNO cards in images and camera streams.

CHANGELOG:

Version 0.1 :
- first git push to the respository
- added anti-aliasing with cv2.LINE_AA on all drawn lines and placed text for smoother edges
- changed cv2.rectangle with cv.drawContours for better performance with rotated images
- changed image names for a better understanding
- added colour analysis definition 

Version 0.2 :
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

Version 0.3:
- fixed a bug related to image rotation (some images would get flipped not rotated)
- fixed a bug with the colour recognition section (some images would be recognized as cyan/navy rather than blue, to fix it I reduced the "accuracy", lighter-darker blue = blue)
- fixed a bug where the wrong images were loaded for post-processing because of the same address in memory
- researched pattern recognition and added comments to the document
- added pytesseract in tandem with OpenCV morphology+binarisation for digit recognition
- added more comments

NOTE: PYTESSERACT LIBRARY is now a must install, with a manual location override at the beginning of the file to specify the path.

Version 0.4:
- added digit recognition section with digit extraction as string/int 
- added digit extracted to uno card identification text placement
- modified center cropping coordinates
- changed morphology values used for a better result
- added contour extraction for the image used on digit recognition in order to calculate perimeter/area+vertices and detect reverse, skip, +4,+2 cards
- added extra comments

NOTE: There is currently a problem where if the image is flipped horizontaly, the digit will NOT be recognized. Working on a solution!
