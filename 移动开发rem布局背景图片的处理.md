###移动开发rem布局icon背景图片的处理
我用过的解决方案:
>//加一个span放在目标元素的前面,确定设计稿上面的图标大小,给span同样的大小,然后通过sass里面的变量转rem,最后设置background-size为contain,就完成了布局,大小是"响应式的".javas