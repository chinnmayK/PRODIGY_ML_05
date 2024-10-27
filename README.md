
---

# Food Image Classification with ResNet50 - Project Setup

This README provides detailed steps to download, prepare, and structure the Food-101 dataset for image classification using a modified ResNet50 model. 

## Prerequisites

1. **Python**: Ensure you have Python 3.x installed.
2. **Kaggle API**: We’ll use the Kaggle API to download the dataset. Make sure you have a Kaggle account and API access.

## Step 1: Downloading the Dataset

The dataset is available on Kaggle at [this link](https://www.kaggle.com/datasets/dansbecker/food-101).

### 1.1 Install the Kaggle API

If you haven't already, install the Kaggle API by running:
```bash
pip install kaggle
```

### 1.2 Set Up Kaggle API Access

1. Log in to your Kaggle account.
2. Go to **Account** > **API** and click on **Create New API Token**. This will download a `kaggle.json` file.
3. Place the `kaggle.json` file in the appropriate directory:
   - **Linux / Mac**: `~/.kaggle/kaggle.json`
   - **Windows**: `C:\Users\<Your Username>\.kaggle\kaggle.json`

   > Ensure the file has the correct permissions for security:
   ```bash
   chmod 600 ~/.kaggle/kaggle.json
   ```

### 1.3 Download the Dataset

Run the following command to download the Food-101 dataset:
```bash
kaggle datasets download -d dansbecker/food-101
```

This will create a ZIP file named `food-101.zip` in your current directory.

### 1.4 Unzip the Dataset

Unzip the downloaded file using:
```bash
unzip food-101.zip
```

This will create a folder named `food-101` with the following substructure:

```
food-101/
├── images/
└── meta/
```

## Step 2: Setting Up Folder Structure

To work with the provided code, we’ll create specific folders for training and testing subsets. Here’s how to proceed:

### 2.1 Create Folders

1. Create the following directory structure in the main project folder:
   ```
   Food-101-Classification/
   ├── train/
   └── test/
   ```

### 2.2 Move Files to `train` and `test` Folders

1. Inside `food-101/images`, select a subset of classes as needed for your project. For example, if you're only using five classes, let’s say `apple_pie`, `baby_back_ribs`, `beef_carpaccio`, `beef_tartare`, and `breakfast_burrito`.
2. Copy these folders into the `train` and `test` folders created above, following the structure below:

   ```
   Food-101-Classification/
   ├── train/
   │   ├── apple_pie/
   │   ├── baby_back_ribs/
   │   ├── beef_carpaccio/
   │   ├── beef_tartare/
   │   └── breakfast_burrito/
   └── test/
       ├── apple_pie/
       ├── baby_back_ribs/
       ├── beef_carpaccio/
       ├── beef_tartare/
       └── breakfast_burrito/
   ```

3. In each class folder, randomly allocate around 80% of the images to the `train` folder and the remaining 20% to the `test` folder.

## Step 3: Verify the Folder Structure

Your final folder structure should look like this:

```
Food-101-Classification/
├── train/
│   ├── apple_pie/
│   ├── baby_back_ribs/
│   ├── beef_carpaccio/
│   ├── beef_tartare/
│   └── breakfast_burrito/
└── test/
    ├── apple_pie/
    ├── baby_back_ribs/
    ├── beef_carpaccio/
    ├── beef_tartare/
    └── breakfast_burrito/
```

Each class folder should contain images in `.jpg` format. This setup will ensure that the `ImageDataGenerator` in the provided code can load images properly.

## Step 4: Install Required Libraries

Make sure to install the required libraries by running:
```bash
pip install tensorflow matplotlib numpy
```

## Step 5: Running the Code

Once the folder structure is in place, and the dataset is organized correctly, you can run the code without additional modifications. Make sure the path references in the code match this structure, as shown in `train_data_dir` and `test_data_dir` variables.

---