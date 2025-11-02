# Project Responsive Web Design using Bootstrap
## Date:02.11.2025

## AIM:
To create a simplified clone of Dribbble (https://dribbble.com/) landing page.


## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Insert the necessary CSS and JavaScript files as external in order to use Bootstrap.

### Step 5:
Create a HTML file and include the needed Bootstrap components.

### Step 6:
Publish the website in the LocalHost.

## PROGRAM :

```
login form

<!DOCTYPE html>
<html>
  <head>
    <title>Login Form</title>
    <style>
      body {
        font-family: "Poppins", Arial, sans-serif;
        margin: 0;
        background: linear-gradient(to right,white, gray);
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
      }

      .login-box {
        background: white;
        padding: 40px 35px;
        border-radius: 16px;
        width: 90%;
        max-width: 350px;
        text-align: center;
        box-shadow: 0 8px 25px rgba(0, 0, 0, 0.25);
        animation: fadeIn 0.7s ease-in-out;
      }

      h2 {
        margin-bottom: 20px;
        color: #333;
      }

      hr {
        border: none;
        height: 2px;
        background: linear-gradient(to right, white,gray);
        margin: 15px;
      }

      .input-box {
        margin-bottom: 20px;
        text-align: left;
      }

      .input-box label {
        font-size: 14px;
        color: #555;
        display: block;
        margin-bottom: 6px;
      }

      .input-box input {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 8px;
        outline: none;
        transition: 0.3s;
        box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
      }

      .input-box input:focus {
        border-color:gray;
        box-shadow: 0 0 8px rgba(0,225,0,0);
      }

      .submit-btn {
        background: linear-gradient(to right, #007bff, #0056b3);
        color: white;
        border: none;
        padding: 12px 20px;
        border-radius: 8px;
        width: 100%;
        cursor: pointer;
        font-weight: bold;
        transition: 0.3s;
      }

      .submit-btn:hover {
        background: linear-gradient(to right, #0056b3, #003f7f);
        transform: scale(1.03);
      }

      .register {
        margin-top: 15px;
        color: #555;
        font-size: 14px;
      }

      .register a {
        color: #007bff;
        text-decoration: none;
        font-weight: 600;
      }

      .register a:hover {
        text-decoration: underline;
      }

      @keyframes fadeIn {
        from {
          opacity: 0;
          transform: translateY(20px);
        }
        to {
          opacity: 1;
          transform: translateY(0);
        }
      }
    </style>

    <script>
      function validation() {
        const username = document.getElementById("t1").value.trim();
        const pwd = document.getElementById("t2").value.trim();

        if (username === "" || pwd === "") {
          alert("Please fill in all fields.");
          return;
        }

        if (username === "24009351" && pwd === "1004") {
          alert("✅ Login successful!");
          window.location.href = "mainmenu.html";
        } else {
          alert("❌ Incorrect username or password.");
        }
      }
    </script>
  </head>

  <body>
    <div class="login-box">
      <h2>Login</h2>
      <hr />

      <div class="input-box">
        <label for="t1">Username</label>
        <input type="text" id="t1" placeholder="Enter your username" />
      </div>

      <div class="input-box">
        <label for="t2">Password</label>
        <input type="password" id="t2" placeholder="Enter your password" />
      </div>

      <input
        type="button"
        value="Login"
        class="submit-btn"
        onclick="validation()"
      >

      <hr />

      <div class="register">
        New to DRIBBLE? <a href="register.html">Create an account</a>
      </div>
    </div>
  </body>
</html>
```
```
mainmenu.html

<!DOCTYPE html>
<html>
<head>
    <title>Dribbble Shots Gallery</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
  background-color: #f8f8f8;
}

.gallery-card {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 16px rgba(0,0,0,0.07);
  transition: box-shadow 0.2s;
  overflow: hidden;
  margin-bottom: 24px;
}

.gallery-card:hover {
  box-shadow: 0 6px 24px rgba(0,0,0,0.13);
} 

.gallery-card img {
  width: 100%;
  object-fit: cover;
  border-radius: 12px 12px 0 0;
  min-height: 180px;
  max-height: 210px;
}

.p-3 {
  padding: 1.1rem !important;
}

.shot-title {
  color: #333;
  font-weight: 600;
  font-size: 1rem;
  margin-bottom: 0;
}

.shot-meta {
  font-size: 0.97rem;
  color: #8e8e8e;
  margin-top: 4px;
}

.avatar {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  object-fit: cover;
  background: #ededed;
  border: 2px solid #fff;
  margin-right: 10px;
}
@media (max-width: 767px) {
  .gallery-card img {
    min-height: 130px;
    max-height: 160px;
  }
  .avatar {
    width: 30px;
    height: 30px;
  }
}
.footer-copyright {
  background: #232323;
  color: #fff;
  font-size: 1rem;
  letter-spacing: 0.3px;
  display: block;
  border-radius: 0;
  text-align: center;
  width: 100%;
  position: fixed;
  bottom: 0;
  left: 50%;
  right: 50%;
  transform: translateX(-50%);
}
    </style>
</head>
<body>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container-fluid">
            <a class="navbar-brand" href="mainmenu.html">Dribbble</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item"><a class="nav-link" href="designers.html">Designers</a></li>
                <li class="nav-item"><a class="nav-link" href="#">Teams</a></li>
                <li class="nav-item"><a class="nav-link" href="#">Community</a></li>
                <li class="nav-item"><a class="nav-link" href="#">Jobs</a></li>
            </ul>
            <form class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-light" type="submit">Search</button>
            </form>
            <button class="btn btn-pink ms-3">Sign Up</button>
        </div>
    </nav>

    <div class="container">
  <div class="row">
    <!-- Card 1 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45505835/file/b4af2085bba57d833422888c43749438.png?format=webp&resize=1200x900&vertical=center" alt="Famous">
            <span class="shot-title">Famous</span>
          </div>
          <div class="shot-meta">
            <span>4,044 views · 290 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 2 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45508234/file/500ec010d52cbc24c2169dcee2152607.png?format=webp&resize=1200x900&vertical=center" alt="Balkan Brothers">
            <span class="shot-title">Balkan Brothers</span>
          </div>
          <div class="shot-meta">
            <span>2,404 views · 236 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 3 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45507683/file/408f4f5515dea5b9edd3a8135634050c.webp?format=webp&resize=400x300&vertical=center" alt="Jan Losert">
            <span class="shot-title">Jan Losert</span>
          </div>
          <div class="shot-meta">
            <span>3,985 views · 264 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 4 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45507344/file/a6f93eada6d9e9cee1648d92e012ee1a.png?format=webp&resize=400x300&vertical=center" alt="Mattias Johansson">
            <span class="shot-title">Mattias Johansson</span>
          </div>
          <div class="shot-meta">
            <span>2,602 views · 186 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 5 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45513444/file/57149f0834f37f14d64899987a9120a6.jpg?format=webp&resize=400x300&vertical=center" alt="Ruslan Siiz">
            <span class="shot-title">Ruslan Siiz</span>
          </div>
          <div class="shot-meta">
            <span>2,369 views · 178 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 6 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45508179/file/f14d7f1c7f5d4194570c9dc475fb6aeb.png?format=webp&resize=400x300&vertical=center" alt="Paperpillar">
            <span class="shot-title">Paperpillar</span>
          </div>
          <div class="shot-meta">
            <span>2,025 views · 160 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 7 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45505820/file/d10204052e1c54f9bf3aa12883f5bcac.png?format=webp&resize=400x300&vertical=center " alt="Alfrey Davilla">
            <span class="shot-title">Alfrey Davilla | vaneltia</span>
          </div>
          <div class="shot-meta">
            <span>1,841 views · 158 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 8 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45507183/file/still-6d6869267b4c687ae2612e518a74de0f.png?format=webp&resize=400x300&vertical=center" alt="Studio-JQ Δ">
            <span class="shot-title">A Studio-JQ Δ</span>
          </div>
          <div class="shot-meta">
            <span>2,179 views · 158 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 9 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45511486/file/be650639fe6bb586d5a5293031b5220f.jpg?crop=209x401-1803x1597&format=webp&resize=400x300&vertical=center" alt="RomainTrystram">
            <span class="shot-title">RomainTrystram</span>
          </div>
          <div class="shot-meta">
            <span>1,872 views · 148 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 10 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45512380/file/336db146149f03e454d744e1070f5aef.jpg?format=webp&resize=400x300&vertical=center" alt="inFullMobile">
            <span class="shot-title">inFullMobile</span>
          </div>
          <div class="shot-meta">
            <span>2,167 views · 134 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 11 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45508524/file/4bfc9f8cdff664e22e886cbd4bfd40c1.png?format=webp&resize=400x300&vertical=center" alt="FourPlus Studio">
            <span class="shot-title">FourPlus Studio</span>
          </div>
          <div class="shot-meta">
            <span>1,371 views · 127 likes</span>
          </div>
        </div>
      </div>
    </div>
    <!-- Card 12 -->
    <div class="col-md-4 col-sm-6 mb-4">
      <div class="gallery-card">
        <div class="p-3">
          <div class="d-flex align-items-center mb-2">
            <img class="avatar mr-2" src="https://cdn.dribbble.com/userupload/45509440/file/5be1367870dedc22851a7ac120d8c5bc.jpg?format=webp&resize=400x300&vertical=center" alt="MUTI">
            <span class="shot-title">MUTI</span>
          </div>
          <div class="shot-meta">
            <span>728 views · 118 likes</span>
          </div>
        </div>
      </div>
    </div>

      <br>
<footer class="footer-copyright mt-5">
  <div class="container-fluid text-center py-3">
    <span>&copy; 2025 All rights reserved. Designed by BTU.</span>
  </div>
</footer>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>

```

## OUTPUT:

![alt text](<Screenshot 2025-11-02 200357.png>)
![alt text](<Screenshot 2025-11-02 200420.png>)

## RESULT:
The Project for responsive web design using Bootstrap is completed successfully.
