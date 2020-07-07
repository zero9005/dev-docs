# CSS 常用样式

## 控制文字显示行数

- 只显示一行

  ```css
  white-space: nowrp;
  overflow: hidden;
  text-overflow: ellipsis;
  ```

- 显示两行(其它行数更改-webkit-line-clamp的值即可)

  ```css
  text-overflow: -o-ellipsis-lastline;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  ```

  

## 清除浮动

```css
.clearfix::after {
    content: '';
    display: block;
    clear: both;
    visibility: hidden;
    height: 0;
    font-size: 0;
}
```

