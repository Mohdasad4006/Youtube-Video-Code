# index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Mobile navbar | upCoding</title>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/css/all.min.css"
    />
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <nav class="navbar">
      <ul class="navbar-icons">
        <li class="navbar-icon active">
          <i class="fa-solid fa-house-user"></i>
          <span>Home</span>
        </li>

        <li class="navbar-icon">
          <i class="fa-solid fa-magnifying-glass"></i>
          <span>Search</span>
        </li>
        <li class="navbar-icon">
          <i class="fa-regular fa-message"></i>
          <span>Message</span>
        </li>
        <li class="navbar-icon">
          <button onclick="changeAppearance()" class="appearence-btn"><i class="fa-solid fa-moon"></i></button>
          <span>Mode</span>
        </li>

        <li class="navbar-icon">
          <i class="fa-regular fa-circle-user"></i>
          <span>Profile</span>
        </li>
      </ul>
    </nav>
    <script src="script.js"></script>
  </body>
</html>

```
# Style.css

```css 
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@100;200;300;400;500;600;700&display=swap");

       :root {

        --white: #ffffff;
        --black: #000000;

        --green: #247881;
        --green-dark: #2c3639;
        --green-light: #8ec3b0;
        --green-light-opacity: rgba(36, 120, 129, 0.2);

        
        --shadow-green: 0px 0px 8px var(--green);
        --shadow-black: 0px 0px 5px var(--black);
      } 

      * {
        margin: 0;
        padding: 0;
        outline: none;
        list-style-type: none;
        box-sizing: border-box;
        font-family: "Montserrat", sans-serif;
      }

      html,
      body {
        font-size: 62.5%; /*font-size = 10px*/;
      }

      body {
        display: flex;
        position: relative;
        height: 100vh;
        width: 100%;
        background-color: var(--green-light);
        /* background-color: bisque; */
      }

      .navbar {
        display: flex;
        align-items: center;
        height: 6rem;
        padding: 1rem;
        width: 350px;
        margin: auto;
        background-color: var(--white);
        border: 1px solid var(--white);
        border-radius: 50px;
        box-shadow: var(--shadow-green);
      }

      .navbar-icons {
        flex: 1;
        display: flex;
        align-items: center;
        justify-content: space-around;
      }

      .appearence-btn {
  height: 2.5rem;
  width: 2.5rem;
  right: 4rem;
  font-size: 1.5rem;
  top: 4rem;
  cursor: pointer;
  background-color: transparent;
  border-radius: 35px;
  border: none;
}
      .navbar-icon {
        flex: 20%;
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        text-decoration: none;
        cursor: pointer;
        border-radius: 35px;
        padding: 1.1rem 2rem 1.1rem 1.3rem;
      }

      .navbar-icon i {
        font-size: 2rem;
        color: var(--green-dark);
      }

      .navbar-icon span {
        opacity: 0;
        font-size: 1.2rem;
        font-weight: 600;
        color: var(--green);
        margin-left: -4rem;
        transition: opacity 0.1s ease, margin-left 0.4s ease;
      }

      .active.navbar-icon {
        display: flex;
        align-items: center;
        border-radius: 35px;
        width: 100%;
        background-color: var(--green-light-opacity);
        padding: 1.1rem 2rem 1.1rem 1.3rem;
      }

      .active.navbar-icon i {
        color: var(--green);
      }

      .active.navbar-icon span {
        opacity: 1;
        margin-left: 0.8rem;
      }

      .dark.navbar {
        background-color: var(--black);
        border: var(--black);
        box-shadow: var(--shadow-black);
        transition: 0.3s ease-in-out;
      }

      .dark .navbar-icon {
        background-color: var(--black);
        transition: 0.3s ease-in-out;
      }

      .dark .active.navbar-icon {
        background-color: var(--green);
        transition: 0.3s ease-in-out;
      }

      .dark .navbar-icon i,
      .dark .navbar-icon span {
        color: var(--white);
        transition: 0.3s ease-in-out;
      }

      .dark.appearence-btn {
        background-color: var(--black);
        color: var(--white);
        transition: 0.3s ease-in-out;
      }

      .navbar-icon.dark {
        background-color: var(--black);
        transition: 0.3s ease-in-out;
      }

      .dark .navbar-icon i,
      .dark .navbar-icon span {
        color: var(--white);
        transition: 0.3s ease-in-out;
      }
```

# script.js

``` javascript
let links = document.querySelectorAll(".navbar-icon");
      const navbar = document.querySelector(".navbar");
      let isDark = false;
      const clearActive = () => {
        for (link of links) link.classList.remove("active");
      };

      for (link of links) {
        link.onmouseover = function () {
          clearActive();
          this.classList.add("active");
        };
      }

      const changeAppearance = () => {
        if (!isDark) {
          navbar.classList.add("dark");
          isDark = !isDark;
        } else {
          navbar.classList.remove("dark");
          isDark = !isDark;
        }
      };

```