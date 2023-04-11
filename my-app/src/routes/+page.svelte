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

.topcontent {
  background-color: #777;
  padding: 800px;
  text-align: center;
  color: white;
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

<div class="topcontent">
</div>
<footer>

</footer>
</body>
</html>
