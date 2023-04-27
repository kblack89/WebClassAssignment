<script>

  import { redirect,} from "@sveltejs/kit";
  import { blank_object,} from "svelte/internal";

</script>
<!DOCTYPE html>
<html lang="en">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
    margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

.topnav {
  overflow: hidden;
  background-color: black;
}

.topnav a {
  float: left;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

.topnav a:hover {
  background-color: white;
  color: black;
}
footer {
  background-color: #779;
  padding: 100px;
  text-align: center;
  color: white;
}

/* Column container */
.row {  
  display: flex;
  flex-wrap: wrap;
}
/* Create two unequal columns that sits next to each other */
/* Sidebar/left column */
.side {
  flex: 10%;
  background-color: #f1f1f1;
  padding: 20px;
}


.topcontent {
  flex: 70%;
  background-color: #777;
  padding: 80px;
  text-align: center;
  color: white;
}
.fakeimg {
  background-color: #aaa;
  width: 100px;
  padding: 20px;
}

</style>
</head>
<body>

<div class="topnav">
  <a href="#page.svelte">Home</a>
  <a href="#news">News</a>
  <a href="#contact">Contact</a>
  <a href="#about.svelte">About</a>
</div>
<div class="row">
<div class="side">
  <h2>About Me</h2>
  <h5>Photo of me:</h5>
  <div class="fakeimg" style="height:100px;">Image</div>
  <p>Some text about me in culpa qui officia deserunt mollit anim..</p>
  <h3>More Text</h3>
  <p>Lorem ipsum dolor sit ame.</p>
  <div class="fakeimg" style="height:60px;">Image</div><br>
  <div class="fakeimg" style="height:60px;">Image</div><br>
  <div class="fakeimg" style="height:60px;">Image</div>
</div>
<div class="topcontent">
  <h2>TITLE HEADING</h2>
  <h5>Title description, Dec 7, 2017</h5>
 
  <p>Some text..</p>
  <p>Sunt in culpa qui officia deserunt mollit anim id est laborum consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.</p>
  <br>
  <h2>TITLE HEADING</h2>
  <h5>Title description, Sep 2, 2017</h5>
  <div class="fakeimg" style="height:200px;">Image</div>
  <p>Some text..</p>
  <p>Sunt in culpa qui officia deserunt mollit anim id est laborum consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.</p>
</div>
</div>

<footer>

</footer>
</body>
</html>
