<!-- CSS Styling-->
<style>
 h1.white{
    color:white;
 }   

 h1.red{
    color:red;
 }  
 
 p.white
 {
    color: white;
 }

 p.red
 {
    color:red;
 }

</style>
<!--JavaScript-->
 <script>

 let count =0;
 let className = "white";
 let ClassNameTwo = "white"

 function incrementCount()
 {
    count ++;
    if(count == 1)
        className = "red";
    else if(count == 2)
        ClassNameTwo ="red";
 }

 function font_change()
 {

 }

 </script>
<!-- HTML Styling-->
<button on:click={incrementCount}>

    Clicked {count} {count ===1 ? 'time' :'times'} 

</button>
<h1 class="{className}">Welcome to Svens </h1>
<p class ="{ClassNameTwo}">Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
