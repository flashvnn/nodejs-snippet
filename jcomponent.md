# jComponent cheatsheet

## Data bidding syntax
```html
<div data-bind="path.to.property__command1:exp__command2:exp__commandN:exp"></div>
```

Example

```html

<p>Name <span data-bind='obj.name__text:value__class:bold'><span></p>
<p>Value: <span data-bind="obj.val__html:value__invisible:value > 100"></span></p>

<script>
var obj = {'name': '', 'val': 10};

 setTimeout(()=>{
    SET('obj.name', 'Name 1!');
 }, 1000)

 setTimeout(()=>{
    SET('obj.name', 'Name 2!');
    SET('obj.val',  50);
 }, 2000)

 setTimeout(()=>{
    obj.name = 'Name 3!';
    obj.val = 70;
    UPDATE('obj');
 }, 3000)
 //изменение 4
 setTimeout(()=>{
    SET('obj.val',  120);
 }, 4000)
</script>

```
