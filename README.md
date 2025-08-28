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

**Proposed Method**: Use a histogram (np.histogram) to help determine the optimal ground level and update the `get_ground_level()` function accordingly.

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

# Task 2: DBSCAN Clustering (Optimal Eps)

**Goal**: Find an optimized value for the eps parameter for DBSCAN clustering.

**Proposed Method**: 
1. Plot an elbow curve to help determine the optimal eps value.
2. Extract the optimal value from the elbow plot.
3. Apply DBSCAN again with the new eps value.

**Requirements**:
1. For both datasets, report the optimal eps value in the README of your GitHub project.
2. Add the elbow plots to the README of your GitHub project.
3. Add the cluster plots (using the optimized eps) to the README of your GitHub project.

## Task 2 Results

**Method:** This code uses the K-Nearest Neighbors (NearestNeighbors) function with K=5 to calculate the distance from each point of *pcd_above_ground* to its 5th nearest neighbor. These distances are then sorted and displayed in an elbow chart. 

The y-axis of the chart represents the sorted distances to the 5th nearest neighbor. The 'twisting point' or 'elbow' in this chart, where the curve's slope changes significantly, provides an estimated optimal value for the eps parameter used in DBSCAN clustering.

### Dataset 1

Optimal EPS: 1.25

Elbow Chart of Dataset 1:

<img width="866" height="547" alt="image" src="https://github.com/user-attachments/assets/32cfbd71-08c4-4bf1-93f6-ad58668fe031" />

Result:

<img width="855" height="868" alt="image" src="https://github.com/user-attachments/assets/7777f77b-74f8-4aa1-93ad-f980ae07aa45" />

### Dataset 2

Optimal EPS: 1

Elbow Chart of Dataset 2:

<img width="833" height="547" alt="image" src="https://github.com/user-attachments/assets/f841ceb4-65df-4506-a190-defc27500c2c" />

Result:

<img width="846" height="868" alt="image" src="https://github.com/user-attachments/assets/82b24b06-35d2-466f-8a83-095232e2f20d" />

