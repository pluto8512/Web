### subway实现原理

\#\#\#\#\#\#indexOf

```javascript
 <script>
    console.log("Blue Whale".indexOf("Blue"));
    Array.prototype.indexOf = Array.prototype.indexOf ||
        function (what, index) {
            index = index || 0;
            var L = this.length;
            while (index < L) {
                if (this[index] === what) return index;
                ++index;
            }
            return -1;
        }
    </script>
```





