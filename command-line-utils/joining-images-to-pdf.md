You can join multiple images to pdf using `convert`:

```bash
convert *.png out.pdf
```

If you get an error like 
```
convert-im6.q16: attempt to perform an operation not allowed by the security policy `PDF' @ error/constitute.c/IsCoderAuthorized/408.
```

follow the steps below:
```bash
sudo vim /etc/ImageMagick-6/policy.xml
```

and replace the line 
```xml
<policy domain="coder" rights="none" pattern="PDF" />
```
with
```xml
<policy domain="coder" rights="read|write" pattern="PDF" />
```

[source](https://askubuntu.com/questions/1081895/trouble-with-batch-conversion-of-png-to-pdf-using-convert)
