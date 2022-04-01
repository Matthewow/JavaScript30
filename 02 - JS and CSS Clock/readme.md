### Notes:

1. **`transform-origin`**, **`transition-timing-function`**
   
   can be modified in chrome developer tools, including cubic-bezier curves.

2. **Error Fix**
   
   此处存在一个小瑕疵，当秒针旋转一圈之后回到初始位置，开始第二圈旋转，角度值的变化时 444° → 90° → 96° .... 这个过程中，指针会先逆时针从 444° 旋转至 90°，再继续我们期望的顺时针旋转，由于秒针变换时间只有 0.05s，所以呈现的效果就是秒针闪了一下，如果想要观察细节，可以将 .second 设为 transition: all 1s。