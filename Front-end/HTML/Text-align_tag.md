해당 엘리먼트가 차지하는 영역에서 **정렬**할 수 있는 태그

```html
<style>
	div {text-align: right;}
	span {text-align: right;}
</style>
```

- div의 경우 width 100%를 차지하고 있기 때문에 우측 정렬 됨
- span의 경우 해당 엘리먼트가 차지하는 영역이 글씨가 쓰여져있는 공간과 동일해서 정렬 효과가 없음

<br>

### span을 정렬하기 위해서

1. display: block
2. float: right