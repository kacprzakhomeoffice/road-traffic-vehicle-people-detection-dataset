# road-traffic-vehicle-people-detection-dataset (Computer Vision Annotation)

## 📌 Project Overview
This repository contains a hand-annotated image dataset designed for training Computer Vision models for road traffic detection, smart mobility, and autonomous driving scenarios. 

The primary goal of this project was to construct a high-quality, noise-free dataset for object detection by applying strict data labeling guidelines, managing edge cases (e.g., occlusion, background crowds), and structuring outputs into standard machine learning formats.

---

## 🛠️ Tools & Technologies Used
* **Annotation Tool:** [makesense.ai](https://www.makesense.ai/) (Browser-based open-source annotation software)
* **Annotation Type:** 2D Bounding Boxes (Object Detection)
* **Supported Export Formats:** 
  * `YOLO Format` (`.txt` files with normalized coordinates)
  * `COCO JSON` (`annotations.json` single structured file)

---

## 🏷️ Defined Classes & Dataset Structure

The dataset focuses on common urban road users divided into eight distinct classes:

| Class ID | Class Name | Description |
| :---: | :--- | :--- |
| **0** | `Car` | Passenger cars, sedans, SUVs, and vans. |
| **1** | `Pedestrian` | Individual walking/standing pedestrians. |
| **2** | `Bus` | Public transit buses and coaches. |
| **3** | `Two-Wheeler` | Combined category for bicycles, scooters, and motorcycles. |
| **4** | `Truck / Tram` | Trams and big trucks. |
| **5** | `Group_of_People` | People that are hard to be separated from each other. |
| **6** | `Group_of_Cars` | Cars, sedans, vans and SUVs hard to be separated from each other. |
| **7** | `Person` | Individuals out of the street or on bicycles, scooters, and motorcycles. |

---

## 📐 Annotation Guidelines & Quality Control Rules

To ensure high **Inter-Annotator Agreement (IAA)** standards and consistency across the dataset, the following rules were strictly applied:

1. **Tight Bounding Boxes:** Boxes are closely fitted around the boundaries of the visible object, avoiding excessive empty space or clipped features (lights, mirrors, wheels).
2. **Handling Occlusion:** Partially occluded vehicles and pedestrians were individually annotated only if at least **30–50% of the object** was clearly recognizable.
3. **Handling Crowds & Background Noise:** 
   * Some dense, highly pixelated background crowds or unidentifiable distant vehicles were excluded to avoid introducing data noise for model training.
   * Grouped vehicles in the foreground/mid-ground were separated individually as long as structural edges remained discernible.
4. **Class Aggregation:** Bicycles, scooters, and motorcycles were aggregated into the `Two-Wheeler` class to optimize bounding box balance across lower-sample categories.

---

## 📁 Repository Structure

```text
├── images/               # Raw JPEG/PNG image files
├── labels_yolo/          # YOLO format annotation files (.txt) + classes.txt
├── annotations_coco/     # COCO JSON format export (annotations.json)
└── README.md             # Project documentation
