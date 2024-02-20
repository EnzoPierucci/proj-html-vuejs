<template>
    <header class="header">
      <nav class="navbar">
        <!-- Logo -->
        <a href="/" class="navbar-brand">
          <img src="../assets/logo-autocar11.png" alt="Logo" />
        </a>
        
        <!-- Links di navigazione -->
        <ul class="navbar-nav">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About Us</a></li>
          <li><a href="#vehicles">Vehicles</a></li>
          <li><a href="#dealers">Dealers</a></li>
          <li><a href="#packages">Packages</a></li>
          <li><a href="#blog">Blog</a></li>
          <li><a href="#contact">Contact</a></li>
          
        </ul>
        
        <div class="navbar-extra">
          
          <a href="#account" class="navbar-account">
            <img src="../assets/padlock.png" alt="My Account"> My account
          </a>
          <a href="#addcar" class="navbar-account">
            <img src="../assets/add.png" alt="Add Car"> Add Car 
          </a>
          <span class="navbar-phone">(+123) 456 7890</span>
        </div>
      </nav>
    </header>
  </template>
  
  <script>
  
  </script>
  
  <style scoped>
  .header {
    background-color: white;
    color: black;
  }
  
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .navbar-nav {
    list-style: none;
  }
  
  .navbar-nav li {
    display: inline-block;
    margin-right: 20px;
  }
  
  .navbar-nav a {
    color: black;
    text-decoration: none;
    
  }
  
  .navbar-extra {
  }
  </style>
  
