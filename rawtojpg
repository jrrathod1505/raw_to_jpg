import os
from PIL import Image

# Function to convert RAW images to JPEG
def convert_raw_to_jpg(raw_image_path, output_dir):
    # Open the raw image
    with open(raw_image_path, 'rb') as raw_file:
        # Create Image object from raw data
        img = Image.open(raw_file)
        
        # Convert to JPEG format
        output_path = os.path.join(output_dir, os.path.splitext(os.path.basename(raw_image_path))[0] + ".jpg")
        img.convert('RGB').save(output_path, "JPEG")
        print(f"Converted {raw_image_path} to {output_path}")

# Function to iterate through a directory and convert all RAW images
def convert_all_raw_to_jpg(input_dir, output_dir):
    # Ensure output directory exists
    os.makedirs(output_dir, exist_ok=True)

    # Iterate through files in the input directory
    for filename in os.listdir(input_dir):
        filepath = os.path.join(input_dir, filename)
        if os.path.isfile(filepath):
            # Check if the file is a RAW image (you may need to adjust this check based on the specific raw image formats you're dealing with)
            if filename.lower().endswith(('.raw', '.cr2', '.nef')):
                convert_raw_to_jpg(filepath, output_dir)

# Example usage
if __name__ == "__main__":
    
    input_directory = input("Enter raw Directory path : ")
    output_directory = input("Enter Output Directory path : ")
    convert_all_raw_to_jpg(input_directory, output_directory)
