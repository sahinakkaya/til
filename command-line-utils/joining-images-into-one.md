You can join multiple images into one using `convert`:
```bash
# join vertically
convert in1.png in2.png -append out.png

# join horizontally 
convert in1.png in2.png +append out.png
```
