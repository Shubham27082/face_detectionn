# Face Detection & Recognition

A Python library for detecting and recognizing faces in images and video, built on top of [dlib](http://dlib.net/).

## Features

- Detect face locations in images (HOG or CNN model)
- Identify 68 facial landmarks (eyes, nose, mouth, jawline, etc.)
- Generate face encodings for comparison
- Compare faces with a tolerance threshold
- Batch processing support
- Works with webcam, video files, and static images

## Installation

```bash
pip install -r requirements.txt
pip install .
```

> Requires Python 3.5+ and `dlib` with its dependencies.

## Quick Start

```python
import face_recognition

# Load images
image = face_recognition.load_image_file("photo.jpg")

# Find face locations
locations = face_recognition.face_locations(image)

# Get face encodings
encodings = face_recognition.face_encodings(image)

# Compare two faces
results = face_recognition.compare_faces([known_encoding], unknown_encoding)
```

## API

| Function | Description |
|---|---|
| `load_image_file(file)` | Load an image from disk |
| `face_locations(img)` | Find all face bounding boxes in an image |
| `batch_face_locations(images)` | Find faces in a batch of images (GPU) |
| `face_landmarks(img)` | Get 68 facial landmark points |
| `face_encodings(img)` | Generate 128-dimension face encodings |
| `compare_faces(known, unknown)` | Compare a face against a list of known faces |
| `face_distance(encodings, face)` | Get numeric distance between faces |

## Examples

The `examples/` folder contains scripts for common use cases:

- `find_faces_in_picture.py` — detect faces in a static image
- `facerec_from_webcam.py` — real-time recognition from webcam
- `facerec_from_video_file.py` — recognition from a video file
- `face_recognition_knn.py` — KNN-based classifier
- `face_recognition_svm.py` — SVM-based classifier
- `digital_makeup.py` — apply digital makeup using landmarks
- `blur_faces_on_webcam.py` — blur detected faces in webcam feed

## Requirements

See `requirements.txt` for the full list. Key dependencies:

- `dlib >= 19.7`
- `numpy`
- `Pillow`
- `Click >= 6.0`
- `face_recognition_models >= 0.3.0`

## License

MIT
