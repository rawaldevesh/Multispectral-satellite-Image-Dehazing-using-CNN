# Multispectral-satellite-Image-Dehazing-using-CNN
we are removing haze from images using CNN 





import os
import cv2
import image_dehazer
from tkinter import *
from tkinter import filedialog

# Function to select a folder containing hazy images
def select_folder():
    global folder_path
    folder_path = filedialog.askdirectory()

# Function to select a folder to save the dehazed images
def select_output_folder():
    global output_folder_path
    output_folder_path = filedialog.askdirectory()

# Function to dehaze images in the selected folder
def dehaze_images():
    # Loop through each file in the folder
    for filename in os.listdir(folder_path):
        # Check if the file is an image
        if filename.endswith(".jpg") or filename.endswith(".png"):
            # Load the hazy image
            hazy_image = cv2.imread(os.path.join(folder_path, filename))

            # Dehaze the image
            dehazed_image, _ = image_dehazer.remove_haze(hazy_image)

            # Save the dehazed image to the output folder
            cv2.imwrite(os.path.join(output_folder_path, "dehazed_" + filename), dehazed_image)

    # Show a message box when the dehazing is complete
    messagebox.showinfo("Dehazing Complete", "Dehazing is complete!")

# Create the main window
root = Tk()
root.title("Image Dehazer")

# Create a button to select the folder containing hazy images
select_folder_button = Button(root, text="Select Folder", command=select_folder)
select_folder_button.pack()

# Create a button to select the folder to save the dehazed images
select_output_folder_button = Button(root, text="Select Output Folder", command=select_output_folder)
select_output_folder_button.pack()

# Create a button to dehaze the images in the selected folder
dehaze_button = Button(root, text="Dehaze Images", command=dehaze_images)
dehaze_button.pack()

# Start the main loop
root.mainloop()

![image](https://github.com/rawaldevesh/Multispectral-satellite-Image-Dehazing-using-CNN/assets/69393586/92e4e133-36c0-46a0-b13c-466efad48eef)




![image](https://github.com/rawaldevesh/Multispectral-satellite-Image-Dehazing-using-CNN/assets/69393586/631e0ac6-42d9-49a2-ada8-32c5820a4e95)

![image](https://github.com/rawaldevesh/Multispectral-satellite-Image-Dehazing-using-CNN/assets/69393586/f078377f-2c24-4b9f-bc68-24e4534337dd)

![image](https://github.com/rawaldevesh/Multispectral-satellite-Image-Dehazing-using-CNN/assets/69393586/77f2dd16-39a3-4077-9737-720149100eef)

![image](https://github.com/rawaldevesh/Multispectral-satellite-Image-Dehazing-using-CNN/assets/69393586/abe7bac4-b96b-4b16-9f35-248c14920b14)


![image](https://github.com/rawaldevesh/Multispectral-satellite-Image-Dehazing-using-CNN/assets/69393586/4f500e34-3344-4caf-b3e2-84322db4afaf)





