# face-mesh-ml
Computer Vision model for Face Mesh


### Face Mesh Detection

<hr>

<p align="center">
  <img width="640" height="360" src="https://www.computervision.zone/wp-content/uploads/2021/05/Face-Landmarks-2.jpg">
</p>

<pre>
from infiniai.FaceMeshModule import FaceMeshDetector
import cv2

cap = cv2.VideoCapture(0)
detector = FaceMeshDetector(maxFaces=2)
while True:
    success, img = cap.read()
    img, faces = detector.findFaceMesh(img)
    if faces:
        print(faces[0])
    cv2.imshow("Image", img)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
</pre>