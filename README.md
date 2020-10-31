# xpm2html

Copyright (C) 2020 Korey Hinton. See LICENSE file

## NOTE

This current implementation requires images to be in XPM 3 format as outputted
from mogrify, and the image must have roughly only 90 different colors in it so
that each color is represented by exactly 1 character in the xpm file,
essentially the XPM must also be a true ascii art image.

If the image didn't turn out right, first thing to check is if the legend
inside the xpm file has multiple digits used in the lookup key.

## DEMO

```
# Make sure ImageMagick is installed and in PATH
# Test by running mogrify command

chmod +x xpm2html
PATH="${PATH}:${PWD}"

cd demo/
mogrify -format gif Vampire-Jack-o-Lantern.svg
mogrify -geometry x68 Vampire-Jack-o-Lantern.gif # height=68
mogrify -format xpm Vampire-Jack-o-Lantern.gif
# To see ascii art run:
#     cat Vampire-Jack-o-Lantern.xpm

# xpm to html conversion
cat Vampire-Jack-o-Lantern.xpm | xpm2html > Vampire-Jack-o-Lantern.html

# open img.html in the browser
```

![Demo Screen Capture](demo/Capture.PNG)
