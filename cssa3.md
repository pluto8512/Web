\#\#\#风扇旋转

```css
.rotaryAnim{
    -webkit-animation: rot 1s linear infinite;
    animation: rot 1s linear  infinite;
}
@keyframes rot {
    from {
        -webkit-transform: rotate(0deg);
        transform: rotate(0deg);
    }

    to {
        -webkit-transform: rotate(360deg);
        transform: rotate(360deg);
    }
}
```





