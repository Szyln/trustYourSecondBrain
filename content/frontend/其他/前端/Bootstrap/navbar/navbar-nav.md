# navbar-nav
- 細項群組（會被收起來的）

## 寫法
- `ul.navbar-nav` > `li`.[[nav-item]]> `a`.[[nav-link]]
-  `div.navbar-nav` > a.[[nav-link]]

```html
<ul class="navbar-nav me-auto mb-2 mb-lg-0">
	<li class="nav-item">
		<a class="nav-link active" aria-current="page" href="#">Home</a>
	</li>
</ul>
```

![[navbar-toggler#collapse 跟 navbar-collapse class]]

>[srolling（收起來的內容的滾動效果）](https://bootstrap5.hexschool.com/docs/5.0/components/navbar/#scrolling)
>加入一個選填的屬性 `.navbar-scroll` 來設置 `max-height`


#bs/component/navbar 