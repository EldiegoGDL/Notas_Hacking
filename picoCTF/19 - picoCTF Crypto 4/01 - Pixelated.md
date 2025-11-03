## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png)
## Solución
```python
from PIL import Image

def combine_images(image1_path, image2_path, output_path):
    # Open the images
    image1 = Image.open(image1_path)
    image2 = Image.open(image2_path)

    # Ensure both images have the same size
    if image1.size != image2.size:
        raise ValueError("Images must have the same size")

    # Combine the images using a simple averaging technique
    combined_image = Image.blend(image1, image2, alpha=0.5)

    # Save the combined image
    combined_image.save(output_path)

if __name__ == "__main__":
    # Provide the paths of the input images and the desired output path
    image1_path = "scrambled1.png"
    image2_path = "scrambled2.png"
    output_path = "combined_image.png"

    combine_images(image1_path, image2_path, output_path)


```

picoCTF{1b867c3e}
## Notas adicionales
+ con wget descargamos las imagenes que nos proporcionaron y al abrirlas solo vemos pixeles de colores
+ al tener dos images probamos combinandolas con un codigo
+ despues usamos una pagina para ver cada pixel de la imagen combinada
## Referencias
https://29a.ch/photo-forensics/#forensic-magnifier