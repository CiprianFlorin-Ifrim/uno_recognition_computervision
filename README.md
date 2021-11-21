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