# Getting text from videogame screenshots

This week I'been playing fallout New Vegas in French to boost up my language skills and have some fun.
I started writing down cool phrases and words that caused me trouble to look them up latter. But dialogues are faster than my handwriting and soon they were outspeeding me. This turned into taking screenshots and looking up translations in google transalate. But soon I had more screenshots that I could handle...

## Test run: Getting text from the image of a receipt
So for a quick and dirty soultion I followed the first example in the tutorial (If anyone reading this is interested in learning a bit of OCR, it is probably better to follow the link):\
https://medium.com/better-programming/beginners-guide-to-tesseract-ocr-using-python-10ecbb426c3d 

* First we pip3 install Pillow and tesserocr.
* We import the file to PIL and preproccess it.
*We use tesserocr to extract the text from the preprocesed image

```python
# (As seen in the tutorial or see notebook)
from PIL import image


column = Image.open('Receip.jpg')

#convert image to greyscale
gray = column.convert('L')

#We maker the grey scale into  black and white
bw = gray.point(lambda x: 0 if x<200 else 255, '1')

#save black and white image
bw.save("recip.jpg")
```

The Image.convert() method returns a converte copy of the image, we can convert to different formats: greyscale “L”, red-blue-green “RGB” and cian-magenta-yellow-balck “CMYK.” \
From the grey scale we further filter pixels converting the image into a black and white one. Image.point() maps the image through a look up table.




