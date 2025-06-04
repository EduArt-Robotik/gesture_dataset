# Gesture Dataset for `ai_tutorial`

This folder contains the datasets used to train the gesture recognition model in the `ai_tutorial` project. The datasets are formatted for training with YOLO-based object detection models.

## Dataset Structure

We provide two versions of the dataset:

---

### Standard Dataset

This dataset contains the following gestures:

- `up`
- `down`
- `left`
- `right`
- `stop`
- `no_gesture`

#### Folder Layout:

- `images/` – All labeled images (unsplit)
- `labels/` – Corresponding YOLO format label files
- `train/` – Training images
- `val/` – Validation images
- `gesture.yaml` – Dataset config file for YOLO training
- `classes.txt` – List of gesture classes

---

### Extended Dataset with `thumbs_up`

This version includes an additional gesture class: `thumbs_up`.

#### Folder Layout:

- `images_with_thumbs_up/` – All labeled images including `thumbs_up`
- `labels_with_thumbs_up/` – Corresponding labels including `thumbs_up`
- `train_with_thumbs_up/` – Training images with `thumbs_up`
- `val_with_thumbs_up/` – Validation images with `thumbs_up`
- `gesture_with_thumbs_up.yaml` – Dataset config file including `thumbs_up`
- `classes_with_thumbs_up.txt` – Updated class list

---

## YOLO YAML Configs

- `gesture.yaml`  
  → Points to the standard `train` and `val` directories and includes the original 6 classes.

- `gesture_with_thumbs_up.yaml`  
  → Points to the `train_with_thumbs_up` and `val_with_thumbs_up` folders and includes 7 classes.

---

## Label Format

Each label file follows the YOLO format.

---

## Notes

- `gesture_detection.ipynb` – Jupyter notebook used for preprocessing, visualization, or testing.

---

## How to Use

  **Train the model using Ultralytics**  
  
   Follow the [official guide](https://docs.ultralytics.com/modes/train/)  
   Terminal command:
   ```
   yolo task=detect mode=train \
   data=<path_to_dataset.yaml> \
   model=yolov8n.pt \
   epochs=50 \
   imgsz=640 \
   patience=10 \
   project=<path_to_logs> \
   name=<name>
   ```
