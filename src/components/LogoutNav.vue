<template>
    <ul class="main-nav">
        <li id="btn-logout"><a href="#"><b>Logout</b></a></li>
    </ul>
</template>

<script>
export default {

}
</script>

<style>
.main-nav {
    margin-top: 35px;
    float: right;
    list-style: none;
    margin-right: 50px;
}
  
.main-nav li {
    display: inline-block;
    margin-left: 40px;
    
}
  
.main-nav li a:link,
.main-nav li a:visited {
    padding: 8px 0;
    color: #fff;
    text-decoration: none;
    font-size: 90%;
    font-weight: 400;
    border-bottom: 2px solid transparent;
    transition: border-bottom 0.2s;
}
  
.main-nav li a:hover,
.main-nav li a:active {
    border-bottom: 2px solid #2487c9;
}
</style>