# CiliaryLength
This project automates the detection and measurement of **flagella in microscopy images** using a combination of **Meta AI’s Segment Anything Model (SAM)** and **classical image processing techniques** such as skeletonization, Hough circle detection, and morphological analysis. It provides accurate flagella segmentation, associates each with a cell center, and computes total flagella lengths per cell in pixels.

## How It Works

If you're using Google Colab Change the Runtime to **T4 GPU**
1. **Input**: Microscopy images (RGB or grayscale).  
2. **Segmentation**: SAM detects potential flagella regions.  
3. **Processing**: Each region is skeletonized, smoothed, and filtered.  
4. **Cell Detection**: Cell centers are detected using Hough Circles and clustered with DBSCAN.  
5. **Length Calculation**: Flagella are connected to center of the cell and total lengths are measured.  
6. **Output**: A visual overlay showing detected cells, flagella, and computed lengths.

## Technologies Used

- **Python 3.9+**
- **OpenCV** – image processing  
- **Segment Anything (SAM)** – mask generation and segmentation  
- **scikit-image** – skeletonization and morphology  
- **scikit-learn (DBSCAN)** – clustering of detected centers  
- **SciPy** – B-spline smoothing and distance computation  
- **Matplotlib** – visualization

## Google Colab Setup (GPU Required)

If you are running this project on **Google Colab**, make sure to **enable GPU acceleration** before executing the notebook:

1. Go to the menu bar:  
   `Runtime → Change runtime type`
2. Under **Hardware accelerator**, select **T4 GPU**
3. Save changes and reconnect the runtime.
4. Change the file path accordingly
This is required because **SAM uses CUDA GPU** for segmentation, and the code will not run properly on CPU-only runtimes.

## Contributing
If you'd like to contribute to the this project, follow these steps:

1. Fork this repository.
2. Create a branch: git checkout -b your-feature
3. Make your changes and commit them: git commit -m 'your-message'
4. Push to the original branch: git push origin my-changes
5. Create a pull request.
