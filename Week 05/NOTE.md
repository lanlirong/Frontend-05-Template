学习笔记

## 拖拽技巧

* mousemove, mouseup监听在document上，这样即使移出浏览器范围，仍能监听到，也防止拖拽过快，出现拖断。
* div translate的值为baseX + event.clientX - startX，baseY + event.clientY - startY。event.clientX为移动时鼠标的位置，startX为mousedown时鼠标的位置， baseX 为div初始位置
* 拖拽的骨架代码
```
let dragable = document.getElementById('dragable')
        let baseX = 0, baseY = 0
        dragable.addEventListener('mousedown', function (event) {
            let startX = event.clientX, startY = event.clientY
            let up = (event) => {
                baseX = baseX + event.clientX - startX
                baseY = baseY + event.clientY - startY

                document.removeEventListener('mousemove', move)
                document.removeEventListener('mouseup', up)

            }
            let move = (event) => {
                dragable.style.transform = `translate(${baseX + event.clientX - startX}px,${baseY + event.clientY - startY}px)`

            }
            document.addEventListener('mousemove', move)
            document.addEventListener('mouseup', up)

        })
```

## getBoundingClientRect()

* Element.getBoundingClientRect() 方法返回元素的大小及其相对于视口的位置。

* 如果是标准盒子模型，元素的尺寸等于width/height + padding + border-width的总和。如果box-sizing: border-box，元素的的尺寸等于 width/height。

## document.createRange()

* 返回一个 Range 对象。

```
var range = document.createRange();

range.setStart(startNode, startOffset);
range.setEnd(endNode, endOffset);
```
* Range 对象: Range 对象表示文档的连续范围区域，如用户在浏览器窗口中用鼠标拖动选中的区域。
