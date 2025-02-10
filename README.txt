# Face Detection Project

## Libraries Used with Versions

- **NumPy version**: 1.26.4  
- **scikit-learn version**: 1.5.2  
- **scikit-image version**: 0.24.0  
- **Matplotlib version**: 3.8.4  
- **OpenCV version**: 4.10.0.84  
- **Python version**: 3.9.13  
- **pip**: 22.0.4  

- **Jupyter**: 1.1.1  
- **Jupyter-server**: 2.14.2  
- **Notebook**: 7.2.2  

**Processing Time**: Between 30 seconds and 2 minutes per image (generally around 5 hours in total).  

---

## How to Run the Code

### A.) Files with Numbers (Executable)

1. **Task1 and Task2**:  
   - Files with numbers in their names should be executed in numerical order. For example:  
     - `1_obtine_rezultate.ipynb`  
     - `2_dad_result.ipynb`  
     - `3_deedee_result.ipynb`  
     - `4_dexter_result.ipynb`  
     - `5_mom_result.ipynb`  
   - Notebooks named after characters make predictions for those characters, while `1_obtine_rezultate.ipynb` processes all faces.  
   - If the computer's memory allows, these notebooks can be run in parallel.  
   - In each notebook, the last cell contains a variable:  
     ```python  
     test_img_path='./test_daria_custom/images/'  
     ```  
     This should be changed to the path of the test file. No other modifications are needed; the notebooks can be run entirely.  

2. **Bonus Task**:  
   - The `YOLO.ipynb` notebook contains the code for YOLO predictions. The first cell contains:  
     ```python  
     test_images_dir = Path("./validare/validare/")  
     ```  
     This should be changed to the directory containing the test images. All predictions will be saved in the folders:  
     - `351_Pirvulescu_Daria/task1_bonus`  
     - `351_Pirvulescu_Daria/task2_bonus`  

---

### B.) Files Without Numbers (Non-Executable)

Files without numbers represent data processing, descriptor extraction, and SVC training. These are not meant to be executed and serve as proof of the project's progression.  

1. **Task1 and Task2**:  
   - `extrage_patch_poz.ipynb`: Takes training images and annotations, then groups cropped faces into different geometric shapes (square, rectangle, tall rectangle) based on aspect ratio.  
   - `descriptori.ipynb`: Creates both positive and negative descriptors.  
   - `antreneaza.ipynb`: Trains 3+12 SVCs with an RBF kernel.  

2. **Bonus Task**:  
   - `YOLO_prepare_data.ipynb`: Prepares training data for YOLO in a supported format.  

---

### If You Want to Run Non-Executable Files

1. **extrage_patch_poz.ipynb**:  
   - Modify the first 4 lines of the last cell to point to the training files.  

2. **descriptori.ipynb**:  
   - For negative descriptors, change the first 4 lines of cell 6 to the training images folder path.  
   - For positive descriptors, run `extrage_patch_poz.ipynb` first.  

3. **antreneaza.ipynb**:  
   - Run the above two notebooks before executing this one.  

4. **YOLO_prepare_data.ipynb**:  
   - The first two commented cells process validation data. Only 20 validation images were used, so modify the functions as follows:  
     ```python  
     scrie_img_pt_YOLO -> for file in files[:20]:  
     scrie_labels_pt_YOLO_task2 -> # if img_name=='021.jpg': return  
     ```  
   - The last commented cell represents the training done on Kaggle. Modify the path to `data.yaml`.  

---

For more details, refer to the [documentation](link_to_documentation_file_in_repository).
