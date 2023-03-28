# RemoveBG [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/reirualluap/RemoveBG/blob/main/RemoveBG.ipynb])
Remove backgroup from multiple images in a few

# Require : 
!pip install rembg

# Use : 

1 - Select your images via an files.upload()

2 - rembg extract image component and remove background

3 - Download the output via an files.download()

# CODE 

```
from rembg import remove
import cv2
from google.colab import files

uploaded = files.upload()
input_paths = list(uploaded.keys())

for input_path in input_paths:
  name = input_path.split('.')[0]
  output_path = f"{name}.png"

  input = cv2.imread(input_path)

  output = remove(input)

  cv2.imwrite(output_path, output)

  files.download(output_path)

```
