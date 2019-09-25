# web-code-snippet-garden
一些web、H5、canvas相关的特效demo

## 目录


## canvas 图片展现效果(类似百叶窗)

**原文**： [http://slicker.me/javascript/image_transition_effect.htm](http://slicker.me/javascript/image_transition_effect.htm)

**demo**: [https://codesandbox.io/s/canvas-image-flood-effect-jqiox](https://codesandbox.io/s/canvas-image-flood-effect-jqiox)

<a target="_blank" href="./canvas-image-flood-fill/1.mp4">截图效果</a>

实例代码：

```html
<html>
<body>
<canvas id="myCanvas" width="600" height="373"></canvas>
<script>
let image = new Image();
image.src = "example1.jpg";
let canvas = document.getElementById("myCanvas");
let context = canvas.getContext("2d");
let row, imageWidth, imageHeight;

image.onload = function() {
  imageWidth = image.width;
  imageHeight = image.height;
  row = imageHeight;
  requestAnimationFrame(animate);
};

function animate() {
  context.drawImage(image, 0, row, imageWidth, 1, 0, 0, imageWidth, row);
  if (row > 0) row--;
  else
    row = imageHeight;
  requestAnimationFrame(animate);
}

</script>
</body>
</html>
```
