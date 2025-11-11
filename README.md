# Mango-willow
It's always a good time to travel through time

![buh](https://github.com/nicolasbaez/Mango-willow/blob/main/xp056.gif)
```javascript
setup = (_) => createCanvas((w = 500), w);
k = 0;
draw = (_) => {
  clear();
  k += 0.01;
  for (i = 0; i <= w; i += 10)
    for (j = 0; j <= w; j += 50) {
      fill(
        noise(i, j, k) * map(sin(k), -1, 1, 0, 255),
        noise(k, i, j) * 255,
        noise(k, i, j) * map(cos(k), -1, 1, 0, 255)
      );
      rect(i, j, 10, 50);
    }
  if (k == 0.01) saveGif("xp056.gif", 1500, { delay: 0, units: "frames" });
};
