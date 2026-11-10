**# Image Slide Show App By Python**



**from itertools import cycle**

**from PIL import Image, ImageTk**

**import time**

**import tkinter as tk**



**root = tk.Tk()**

**root.title("Image Slideshow Viewer")**

**root.geometry("800x600")**



**# List of Image Paths**



**image\_paths = \[]**



**image\_size = (600, 400)**



**images = \[Image.open(path).resize(image\_size) for path in image\_paths]**



**photo\_images = \[ImageTk.PhotoImage(image) for image in images]**



**label = tk.Label(root)**

**label.pack()**



**# Create slideshow cycle**

**slideshow = cycle(photo\_images)**



**def update\_image():**

&#x20;   **photo\_image = next(slideshow)**

&#x20;   **label.config(image=photo\_image)**



**def start\_slideshow():**

&#x20;   **update\_image()**

&#x20;   **root.after(2000, start\_slideshow)**



**# Play Button**

**play\_button = tk.Button(**

&#x20;   **root,**

&#x20;   **text="Play Slideshow",**

&#x20;   **command=start\_slideshow**

**)**

**play\_button.pack()**



**root.mainloop()**

