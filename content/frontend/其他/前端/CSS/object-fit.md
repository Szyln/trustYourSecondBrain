# object-fit
https://developer.mozilla.org/ja/docs/Web/CSS/object-fit


|狀態|填滿|出血|不變形|
|-|-|-|-|
|cover|O|O|O|
|fill|O|X|X|
|contain|X|X|O|
|none|*|*|O|

^1ffb45

## cover
```html
<!-- bs 例子：外框 1x1，內部填滿不出血不變形-->
<div class="ratio ratio-1x1">
	<!-- object-fit: cover -->
	<img src="https://fakeimg.pl/1000x2000" class="fit-cover" alt="">
</div>
```

## scale-down
The content is sized as if `none` or `contain` were specified, whichever would result in a smaller concrete object size.
