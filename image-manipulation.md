### 2-dimensional iteration - image manipulation

#### RGB Color Model

The amount of each color, sometimes called the **intensity** of the color, allows us to have very fine control over the resulting color.

The minimum intensity value for a basic color is 0. For example if the red intensity is 0, then there is no red in the pixel. The maximum intensity is 255. 

| Color       | Red  | Green | Blue |
| ----------- | ---- | ----- | ---- |
| **Red**     | 255  | 0     | 0    |
| **Green**   | 0    | 255   | 0    |
| **Blue**    | 0    | 0     | 255  |
| **White**   | 255  | 255   | 255  |
| **Black**   | 0    | 0     | 0    |
| **Yellow**  | 255  | 255   | 0    |
| **Magenta** | 255  | 0     | 255  |

```python
import image
```

**`image`** module has two classes: `Image` and `Pixel`. 

There are methods to work with images pixel-per-pixel.

| Method Name  | Example          | Explanation                              |
| ------------ | ---------------- | ---------------------------------------- |
| Pixel(r,g,b) | Pixel(20,100,50) | Create a new pixel with 20 red, 100 green, and 50 blue. |
| getRed()     | r = p.getRed()   | Return the red component intensity.      |
| getGreen()   | r = p.getGreen() | Return the green component intensity.    |
| getBlue()    | r = p.getBlue()  | Return the blue component intensity.     |
| setRed()     | p.setRed(100)    | Set the red component intensity to 100.  |
| setGreen()   | p.setGreen(45)   | Set the green component intensity to 45. |
| setBlue()    | p.setBlue(156)   | Set the blue component intensity to 156. |

Methods to worth with image class:

| Method Name         | Example                         | Explanation                              |
| ------------------- | ------------------------------- | ---------------------------------------- |
| Image(filename)     | img = image.Image(“cy.png”)     | Create an Image object from the file cy.png. |
| EmptyImage()        | img = image.EmptyImage(100,200) | Create an Image object that has all “White” pixels |
| getWidth()          | w = img.getWidth()              | Return the width of the image in pixels. |
| getHeight()         | h = img.getHeight()             | Return the height of the image in pixels. |
| getPixel(col,row)   | p = img.getPixel(35,86)         | Return the pixel at column 35, row 86.   |
| setPixel(col,row,p) | img.setPixel(100,50,mp)         | Set the pixel at column 100, row 50 to be mp. |

### nested iteration

**Image processing** refers to the ability to manipulate the individual pixels in a digital image. In order to process all of the pixels, we need to be able to systematically visit all of the rows and columns in the image. The best way to do this is to use **nested iteration**.

```python
for i in range(5):
    for j in range(3):
        print(i, j)
```

```python
for row in range(img.getHeight()):
    for col in range(img.getWidth()):
        # do something with the pixel at position (col,row)
```

