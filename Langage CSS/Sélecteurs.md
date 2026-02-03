
The selector designate all the elements in a document

Exemple : 

 ```CSS
	 p{
	 }
	 span{
	 }
	 section{
	 }
 ```

We can make declaration in selector like :

```CSS 
section {
	color : red;
}
```

When multiple selectors share the same declarations, they can be grouped together into a comma-separated list.

```CSS
section,span {
	color : red;
}
```

The selector can be an ID , class or property , it's defined on html :

``` HTML
	<p id="myId" class="myClass"> simplon </p>
```

implement CSS :

```CSS
 #myId{
	 color : red;
 }
 .myClass{
	 color : red;
 }
 [property]{
	 color : red;
 }
```


