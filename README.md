# Box-drawing Utilities for Labeling Objects Inside your Pictures

Here are some utility python codes that can help you label your pictures. These codes allows you to surround your object with visualized square lables and translate them into the appropriate form for running yolo. Below are simple descriptions of what each python code does.

## Code Descriptions
### 1. 01_main.py
Executes the labeling program.
> How to use :
1. Requires a "class.txt" file that identifies class names in separate lines.
2. Requires an "Examples/demo/" directory that stores 3 demo images(Don't know whether random images work).
3. Once the program appears on screen, specify the directory for your images and hit "Load". You will see your very first image file in the center.
4. Next, select object class and hit "Confirm" for the object you want to label.
5. Click to label. Only 2 clicks are required for labeling an object. Just to be safe, it is recommended that you click from the upper-left corner to the lower-right corner.
6. Delete inserted labels by selecting and hitting "Delete" to delete a selected label, or click "ClearAll" to delete all labels for a single image.
7. Each visualization of label is stored in ".txt" format inside "Labels/{your directory number}/"

### 2. 02_removeEmptyFile.py
Removes redundant images with no label and empty label files.
> How to use :
1. Specify the path to your images and label text files in code. Where to fix is self-evident.

### 3. 03_Labels2Formal.py
Converts labels to appropriate form for feeding yolo network.
> How to use :
1. Specify the path to your label text files and path to save the converted labels.

### 4. 04_trainTestList.py
Creates a list of train set and test set in separate ".list" files. They are named "train.list" and "test.list"
> How to use :
1. Specify the directory where your Label_formal files reside and where your images reside.
2. Specify the percentage to make your test set. [0,100] The remainder will become the train set.

### 5. 05_Formal2Labels.py
In case the original label files are lost, use this code to convert your Label_formal files back to the original label files.
> How to use :
1. Specify path to Label_formal files and the to-be-generated Label files.

### 6. augment.py
Augment your images by adding blur or noise to your images. You can also rotate your image by 180 degrees.
> How to use :
1. Set parameters for augmentation.

### 7. make_list_inorder.py
Create a list of all ".jpg" files resident in the current directory. The files are enlisted in order.
> How to use :
1. Just run the code!

### 8. make_list_random.py
Create a shuffled list of all ".jpg" files resident in the current directory.
> How to use :
1. Just run the code!

### 9. rename.py
Rename files in current directory by replacing a certain expression to another.
> How to use :
1. Modify replace( {src} , {dst} ) and run.

### 10. format_list.sh
Shell script to convert newline from DOS format to UNIX format.
> How to use :
1. In UNIX device : type "./format.sh {your file name}" and hit enter.
2. Name says format_"list".sh, but it actually works on all files. Cheers.


## Couple Notes
1. Strongly advised that Images, Labels, Labels_formal directories be made identically as the provided templates(relative path from source code as well). You can keep things lot simpler this way.
2. Codes without indices (augment, makelist and rename) are meant to be used just before training or testing in darknet. They work for images and corresponding labels residing in the same directory as themselves, so they should be copied to the path to your darknet dataset before use. Be sure that non-relevant .jpg or .txt files are not included in the directory(Otherwise they will be considered a part of your training / test sets).
3. Might have to convert DOS codes to UNIX codes before use. 