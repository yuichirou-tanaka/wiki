# onload
- https://into-the-program.com/attr-img-src/

```js
    let charax = 0;
    function _t_MouseClick() {
        console.log("mouse click");
    }
    function _t_mouseover(){
        console.log("mouseover");
    }
    function _t_mousedown(){
        console.log("mousedown");
    }
    function _t_mouseup(){
        console.log("mouseup");
    }
    function _t_mouseenter(){
        console.log("mouseenter");
    }
    function _t_mouseout(){
        console.log("mouseout");
    }
    function _t_mouseleave(){
        console.log("mouseleave");
    }
    function _t_mousemove(e){
        console.log("mousemove");
    }
    function _t_wheel(){
        console.log("wheel");
    }
    
    let button = document.getElementById('_id');
    button.addEventListener('click', _t_MouseClick);
    button.addEventListener('mousedown', _t_mousedown);
    button.addEventListener('mouseup', _t_mouseup);
    button.addEventListener('mouseover', _t_mouseover);
    button.addEventListener('mouseenter', _t_mouseenter);
    button.addEventListener('mouseout', _t_mouseout);
    button.addEventListener('mouseleave', _t_mouseleave);
    button.onmousemove = _t_mousemove;
    button.addEventListener('wheel  ', _t_wheel);
```
