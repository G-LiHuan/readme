
JS部分

1: event.x与event.y问题
  IE下，event对象有x，y属性，但没有pageX，pageY属性；
  FireFox下，event有pageX，pageY，但没有x，y属性。

  解决方法：mX(mX=event.x ? event.x : event.pageX);

2: window.location.href问题
  IE或者Firefox2.0下，可以使用window.location.href或者window.location，
  Firefox。5.x下，只能使用window.location

3：frame问题
  
  一下面的frame为例：
  <frame src="xxx.html" id="frameId" name="frameName" />

  (1)访问frame对象
    IE： 使用window.frameId或者window.frameName来访问这个frame对象，frameId和frameName可以同名
    FireFox：只能使用window.frameName来访问frame对象；
    解决方案：使用document.getElementById('frameId')获取该对象
  
  (2)切换frame内容
  在IE和FireFox中都可以使用window.document.getELementById('frameId').src = 'xxx.html'或者是window.frameName.location="xxx.html"


4: 父元素的区别

  IE： obj.parentElement
  FireFox： obj.parentNode

  解决方案： 都是用obj.parentNode

5：表单元素的获取

  IE：可以使用document.formName.item('itemName')或者document.formName.elements['elementName']
  FireFox：只能使用document.formName.elements['elementName'];

  解决方案：都是用document.formName.elements['elementName'];

6: event对象的target属性

  IE: event对象有srcElement属性，但没有target属性
  FireFox：event有target属性，但没有srcElement属性

  解决方案：使用 srcObj = event.srcElement ? event.srcElement : event.target;

7: 事件监听
  IE: 使用attachEvent监听事件，且事件名前要加上"on"，注销事件是用detachEvent
  FireFox: 使用addEventListener监听事件，注销事件使用removeEventListener


CSS部分

1: cursor:hand Vs cursor:pointer
  IE: 支持pointer和hand，
  FireFox: 不支持hand

2： 透明度

  IE: filter: alpha(opacity=80);

  FireFox: opacity:0.6;

  解决方案： 两个都写

3: margin加倍问题

  IE: div在设置为float的情况下，margin会加倍
  解决方案: 将div设置为display:inline;

4: a标签样式被覆盖
   
   解决方案： 按照顺序写 => link, visited, hover, active
   
5: ul列表编剧属性不统一

   IE: 使用margin属性
   FF: 使用padding属性
   解决方案： 将margin和padding进行初始化

