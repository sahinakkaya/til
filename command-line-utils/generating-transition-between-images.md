I have lots of images of a scene from sunrise to sunset and my wallpaper is automaticatilly set to one of them based on the hour of the day. But you know what? I LOVE customizing my machine and I WANT MORE! I want the transition to be smooth af. To make this possible I need to generate images. And here is the result of literally 5 minutes of google search:

```
convert A.jpg B.jpg -morph 10 out.jpg
```

This will generate 10 images between A and B. Mind blown! Of course you can generate gifs. Just set the output format to `.gif`! In case you need more examples, see [here](https://legacy.imagemagick.org/Usage/anim_mods/#morph) and [here](http://www.imagemagick.org/script/command-line-options.php#morph).

