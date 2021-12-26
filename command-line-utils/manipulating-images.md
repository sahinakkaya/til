You can use `convert` to crop or resize your images. Let's say you have an image with size of `800x600` and you want to crop 100 px from left, 100 px from right and then resize it to `200x200`. Here are the commands you would run:

```bash
convert original.jpg -crop 700x600+100+0 cropped.jpg # Crop from left. 100+0 is offset from top left corner.
convert cropped.jpg -crop 600x600+0+0 cropped.jpg 
convert cropped.jpg -resize 200x200 final.jpg
```
