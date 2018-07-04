## 关于样式的一些tips，包括但不限于CSS


### 正文

[css规范](http://nec.netease.com/standard/css-sort.html)

1: 盒模型。  
(1)盒模型分为两种，IE盒模型(border-box)和W3C盒模型(content-box).  
(2)盒模型的要素：内容(content)，填充(padding)，边框(border)，外边界(margin)，
(3)两种盒子的区别：IE盒子在设置宽度时，会将padding值和border值算进去，而W3C盒子设置宽度只是设置content的宽度。
`Exp:
  .border-box{
    /* IE盒子 */
    box-sizing: border-box;
    width: 100px;
    border: 1px solid 1px;
    padding: 10px;  
  }
  .content-box{
   /* W3C盒子 */
   width: 100px;
   border: 1px solid 1px;
   padding: 10px;
  }
  `