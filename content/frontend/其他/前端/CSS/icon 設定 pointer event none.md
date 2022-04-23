288章 JS setup

按鈕裡面只點得到icon 但點不到 btn，
```css
i {
	pointer-event: none;
}
```
可以這樣解決
這樣就不會點到 i 了，會直接穿透點到 btn