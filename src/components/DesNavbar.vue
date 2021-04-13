<template>
  <header class="center-content">
    <div class="mycontainer nav_wrapper">
    <p class="logo"> 
        <img src="../assets/logo.png" alt="">
    </p>
    <nav>
      <ul class="nav_links">
        <li><a href="#">Experience</a></li>
        <li><a href="#">Competitive</a></li>
        <li><a href="#">Projects</a></li>
      </ul>
    </nav>
    <a href="#" class="cta"><button>Contact</button></a>
    </div>
    
  </header>
</template>

<script>
export default {

}
</script>

<style scoped>
header{
  position: absolute;
  z-index:100;
  width:100vw;
  top:0;
  left:0;
  padding:20px 10%;
}
.nav_wrapper {
  display: flex;
  justify-content: flex-end;
  align-items: center;
}
li,a,button{
  font-weight: 500;
  font-size: 1rem;
  color:#edf0f1;
  text-decoration: none;
}
.logo {
  cursor: pointer;
  margin-right:auto;
}
.logo img{
  height: 55px;
}
.nav_links {
  list-style: none;
}
.nav_links li{
  display: inline-block;
  padding:0px 20px;
}
.nav_links li a {
  transition:all 0.3s ease 0s;
}
.nav_links li a:hover {
  color:#0088a9;
}
button {
  padding:9px 25px;
  background-color: rgba(0,136,169,1);
  border-radius: 50px;
  border:none;
  cursor: pointer;
  transition:all 0.3s ease 0s;
  margin-left:20px;
}
button:hover{
  background-color: rgba(0,136,169,0.8);
}
</style>