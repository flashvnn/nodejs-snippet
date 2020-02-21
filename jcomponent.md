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
 // SET for update object property
    SET('obj.name', 'Name 1!');
 }, 1000)

 setTimeout(()=>{
    SET('obj.name', 'Name 2!');
    SET('obj.val',  50);
 }, 2000)

 setTimeout(()=>{
 // UPDATE for update whole object
    obj.name = 'Name 3!';
    obj.val = 70;
    UPDATE('obj');
 }, 3000)

 setTimeout(()=>{
    SET('obj.val',  120);
 }, 4000)
</script>

```

## Use exist jComponent


```html
<div data---="textbox__form1.firstname__required:true;placeholder:Имя;icon2:pencil;error:Please input name" class='mb10'>Name</div>

```

This is a short entry describing the component and its properties:

`textbox`- name of the component, displays inputfor data entry  
`form1.firstname` - the path to the property of the model, it is the value of this property that will change  
`required:true;placeholder:Имя;icon2:pencil;error:Введите ваше имя` - component configuration and settings  
`Name` - in this component will be displayed as a labeldescriptioninput  

Long define:  
```html
<div data-jc="textbox" data-jc-path="form1.email" data-jc-config="placeholder:Email;icon2:envelope-o;required:true;type:email;" class='mb10'>Email</div>

```

## Data scope

```html
<div data-scope="users.form">
    <div data---="textbox__?.firstname">Name</div>
    <div data---="textbox__?.age">Age</div>    
</div>


<div data-scope="PATH__OPTIONS__DEFAULT_VALUE">

</div>

EXAMPLE:

<div data-scope="users.form__init:users_form_init__{}">
    - method "users_form_init" will be evaluated if the scope will be initialized
    - {} will be a default value for "users.form"
</div>

```
