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
      
      
