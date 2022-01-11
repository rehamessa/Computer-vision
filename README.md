# Computer-vision
OpenCV(OpenSourceComputerVision),across-platformandfreetouselibraryoffunctionsisbasedonreal-timeComputerVisionwhichsupportsDeepLearningframeworksthataidsinimageandvideoprocessing.InComputerVision,theprincipalelementistoextractthepixelsfromtheimagetostudytheobjectsandthusunderstandwhatitcontains.BelowareafewkeyaspectsthatComputerVisionseekstorecognizeinthephotographs
### NUMPYLIBRARY
Numpyis a very popular library for easily creating single, multidimensional array and matrices. It has a large collection of the mathematical function for performing an operation on these arrays.
       
    #creat array
    import numpy as np 
    arr=np.array([[1,2,3],[4,5,6]])
### OPENCV LIBRARY
OpenCVisahugeopen-sourcelibraryforcomputervision,machinelearning,andimageprocessing.OpenCVsupportsawidevarietyofprogramminglanguageslikePython,C++,Java,etc.Itcanprocessimagesandvideostoidentifyobjects,faces,oreventhehandwritingofahuman.Whenitisintegratedwithvariouslibraries,suchasNumpywhichisahighlyoptimizedlibraryfornumericaloperations.
### READING/WRITING AN IMAGE FILE
An image is a multidimensional array; it has columns and rows of pixels, and each pixel has a value. For different kinds of image data, the pixel value may be formatted in different ways.

     #create a 3x3 square black image using a 2d Numpy array
     img= np.zeros((3,3),dtype=np.unit8)
     
     #convert this image into RGB 
     cv2.cvtColor(img,cv2.COLOR_GRAY4BGR)
### IMAGE READING
The imread() function loads image from the specified file and returns it.

     cv2.imread("image')
     #reading image with grayscale mood
     cv2.imread("image",IMREAD_GRAYSCALE)
     
     #using imread for reducing size
     cv2.imread(image,cv2.IMREAD_REDUCED_COLOR_2)
     CV2.IMREAD(IMAGE,cv2.IMREAD_REDUCED_GRAYSCALE_8)
### DISPLAYING CAMERA FRAMES IN A WINDOW
    
    if event == cv.EVENT_LBUTTONUP
## Image Processing
###### CONVERT FROM GRAY TO BINARY

      cv2.threshold(grayimage,127,255,cv2.THRESH_BINARY)
###### BGR TO RGB
      
      cv2.cvtcolor(image,cv2.COLOR_BGR2RGB
   
###### split

      B,G,R=cv2.split('image')
###### split HSV
      
     hue=[:,:,0]
     saturation=[:,:,1]
     value=[:,:,2]
###### resizing
      half = cv2.resize(image, (0, 0), fx = 0.5, fy = 0.5)
      bigger = cv2.resize(image, (1050, 1610))
      stretch_near = cv2.resize(image, (780, 540),interpolation==cv2.INTER_NEAREST)           
 ### LOW PASS FILTER
 ##### BLURRING
 ###### average
 
        cv2.blur(image,(5,5))
 ###### Gaussian     
       
        cv2.GaussianBlur(image, (7, 7), 0)
 ###### Median Blur
 
       cv2.medianBlur(image, 5)
 ###### Bilateral
       
       cv2.bilateralFilter(image, 9, 75, 75)
### HIGH PASS FILTER
###### smooth filter
      filterkernel1 = np.array( [[0.04, 0.04, 0.04, 0.04, 0.04],[0.04, 0.04, 0.04, 0.04, 0.04],[0.04, 0.04, 0.04, 0.04, 0.04],[0.04, 0.04, 0.04, 0.04, 0.04],[0.04, 0.04, 0.04, 0.04, 0.04]])
      cv2.filter2d(img, -1, kernel1)
###### sharp filter
      filterkernel2 = np.array([[-1, -1, -1],[-1, 9, -1],[-1, -1, -1]])
      ndimage.convolve(img, kernel2)
## EDGE DETECTION
######   CUSTOM KERNEL
    ndimagekernel_3x3 = np.array([[-1, -1, -1],[-1, 8, -1],[-1, -1, -1]])
    ndimage.convolve(img, kernel_3x3)
###   DERIVATIVES
###### laplacian
       cv2.Laplacian(img, cv2.CV_64F)
###### sobel and scharr
      sobelx = cv2.Sobel(img, cv2.CV_64F, 1, 0, ksize=5)
      sobely = cv2.Sobel(img, cv2.CV_64F, 0, 1, ksize=5)
      cv2.add(sobelx, sobely)
###### CANNY
      cv2.Canny(img, 200, 300)
## Contours

can be explained as the curve joining all the continuous points along the boundary which are having the
same color or intensity .
#### Applications of Contours detection:
shape Analysis
object detection
Object recognition
###### 1
For better accuracy , we use binary image for finding the contours so first we are going to generate the
binary image

      cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
 ###### 2
 apply threshold mentioned in the previous
section to be able to detect corners by adding this code

       ret , thresh = cv2.threshold(grayimage ,127,255,0)
###### 3
find out contours

      cv2.findContours()
###### 
retrieve the entire hierarchy of external and internal contours
       
       cv2.RETR_TREE
 ######
 retrieve the most external contours
 
       cv2.RETR_EXTERNAL
back to the code sample, note that the findContours function returns two elements: the contours and their
hierarchy. We use the contours to draw green outlines on the color version of the image
       
       contours , hierarchy = cv2. f indContours( thresh, cv2.RETR_TREE,cv2.CHAIN_APPROX_NONE)
## Detecting lines
### HoughLines & HoughLinesP
HoughLines
returns a representation of each line as a single point and an angle, without information about endpoints.
HoughLinesP
returns the two endpoints of each detected line segment
 ###### HoughLinesP
 ###### 1
 search for lines that are separated by as little as 1 pixel and 1 degree.
       
       rho=1 and theta=np.pi/180.0
threshold
represents line is discarded
         
         cv2.HoughLinesP(image,1,np.pi/180,20,minLineLength,maxLineGap)
         
 ## Detecting Circles
 ### HoughCircles
 It works in a very similar fashion to HoughLines
 
 HoughCircles has a minimum distance between a circle's centers, as well as minimum and maximum values for a circle's radius
 
    cv2.HoughCircle(image,cv2,Hough_Gradient,1,np.pi/180,20,minRadius=0,maxRadius=0)
 
 
