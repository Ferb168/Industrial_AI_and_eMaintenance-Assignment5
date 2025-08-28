# Assignment 5: LiDAR Data Processing Summary

## 1. Project Overview & Objectives

This assignment uses two semi-processed LiDAR datasets as practice materials. The tasks involve using Python for data processing and the application and tuning of machine learning methods. The objectives are:
- Learn how to process raw/semi-processed LiDAR data using Python.
- Gain experience with data analysis, visualization, and machine learning algorithms (such as DBSCAN clustering).
- Practice documenting a project in GitHub, including workflow, code, and visual results.

## 2. Data & Environment Requirements

- Datasets: `dataset1.npy` and `dataset2.npy` (semi-processed LiDAR data)
- Includes `share.py` for basic code for data handling and operations
- Recommended environment:
  - Python 3.7 or higher at Google Colab
  - Required packages: numpy, scikit-learn, matplotlib, scipy

# Task 1: Ground Level Detection

**Goal**: Find the best value for the ground level in the point cloud data.

**Method**: Use a histogram (np.histogram) to help determine the optimal ground level and update the `get_ground_level()` function accordingly.

**Requirements**:

*   For each dataset, report the found ground level in the README file of your GitHub project.
*   Add the histogram plots to the README of your GitHub project.

## Task 1 Results

**Method:** This code estimates the ground level by calculating a specific percentile of the Z-coordinate values. It then filters the point cloud data to exclude points with Z-coordinate values at or below this estimated ground level. The bar chart (histogram) is used to visualize the distribution of Z-coordinates and help to decide the estimated ground level.

### Dataset 1

Ground level: 62.053

<img width="580" height="455" alt="image" src="https://github.com/user-attachments/assets/180d461b-529a-4d69-8e52-2268a982214d" />

Before filtering out the ground level:

<img width="407" height="399" alt="image" src="https://github.com/user-attachments/assets/b07bab35-3a04-4558-a78a-1769e767d164" />

After filtering out the ground level:

<img width="414" height="399" alt="image" src="https://github.com/user-attachments/assets/5076ef84-6ed7-427e-ac91-916d69951d39" />


### Dataset 2

Ground level: 62.06200000000001

<img width="580" height="455" alt="image" src="https://github.com/user-attachments/assets/ff76123b-a492-4729-ad5c-fd88c20e7755" />

Before filtering out the ground level:

<img width="407" height="399" alt="image" src="https://github.com/user-attachments/assets/4d259166-ae2b-47f2-93cb-a12a55144b09" />

After filtering out the ground level:

<img width="414" height="399" alt="image" src="https://github.com/user-attachments/assets/5f4e1ce3-0e63-4417-82e0-e865ef2a4dd4" />











