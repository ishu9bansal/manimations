## Creating an animation video locally
Say we have our scene in `test.py` with class name `SquareToCircle`
run below in terminal
```bash
manim -ql test.py SquareToCircle
```
you will see the resulting video in the `media/videos` folder
(this folder is git ignored in this repo)

`-ql` here means to render the scene in low quality