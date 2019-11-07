<template>
  <div id="nav">
    <router-link to="/">
      <svg
        width="30"
        height="45"
        viewBox="0 0 105 180"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M5.904 116L27.648 13.184H51.984C64.368 13.184 74.064 16.544 81.072 23.264C88.08 29.984 91.584 40.304 91.584 54.224C91.584 66.128 89.232 76.736 84.528 86.048C79.92 95.36 73.104 102.704 64.08 108.08C55.152 113.36 44.208 116 31.248 116H5.904ZM21.024 104.912H31.968C41.952 104.912 50.352 102.656 57.168 98.144C63.984 93.632 69.168 87.536 72.72 79.856C76.272 72.176 78.048 63.584 78.048 54.08C78.048 43.52 75.504 35.936 70.416 31.328C65.424 26.624 58.752 24.272 50.4 24.272H38.16L21.024 104.912Z"
          fill="#7E7B7B"
        />
        <path
          d="M20.904 165L42.648 62.184H69.288C78.792 62.184 86.232 64.056 91.608 67.8C97.08 71.544 99.816 77.544 99.816 85.8C99.816 92.808 97.704 98.52 93.48 102.936C89.256 107.256 83.64 110.088 76.632 111.432V112.152C81.336 113.4 85.272 115.752 88.44 119.208C91.608 122.664 93.192 127.272 93.192 133.032C93.192 140.04 91.464 145.944 88.008 150.744C84.648 155.448 79.992 159 74.04 161.4C68.184 163.8 61.416 165 53.736 165H20.904ZM46.248 105.96H63.096C67.416 105.96 71.304 105.288 74.76 103.944C78.312 102.6 81.144 100.584 83.256 97.896C85.368 95.112 86.424 91.608 86.424 87.384C86.424 82.872 84.984 79.416 82.104 77.016C79.224 74.52 74.424 73.272 67.704 73.272H53.16L46.248 105.96ZM36.024 154.056H54.168C62.328 154.056 68.616 152.232 73.032 148.584C77.448 144.936 79.656 139.752 79.656 133.032C79.656 128.424 78.168 124.536 75.192 121.368C72.216 118.2 67.176 116.616 60.072 116.616H43.944L36.024 154.056Z"
          fill="white"
        />
      </svg>
    </router-link>
    <ul>
      <li>
        <router-link to="/about">About Me</router-link>
      </li>
      <li>
        <p>|</p>
      </li>
      <li>
        <router-link to="/portfolio">Projects</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style scoped>
#nav {
  position: -webkit-sticky;
  position: sticky;
  top: 0px;
  background: #555;
  padding: 5px 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

ul {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  list-style: none;
  /* font-family: "Raleway", Arial, sans-serif; */
  text-decoration: none;

  text-align: center;
  text-transform: uppercase;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 1px;
}

ul * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-transition: all 0.35s ease;
  transition: all 0.35s ease;
}
ul li {
  display: inline-block;
  list-style: outside none none;
  margin: 0.5em 0.3em;
  padding: 0;
}
ul a {
  padding: 0.3em 0;
  color: rgba(255, 255, 255, 0.5);
  position: relative;
  text-decoration: none;
  display: inline-block;
}
ul a:before,
ul a:after {
  height: 3px;
  position: absolute;
  content: "";
  -webkit-transition: all 0.35s ease;
  transition: all 0.35s ease;
  background-color: #42b983;
  width: 0;
}
ul a:before {
  top: 0;
  left: 0;
}
ul a:after {
  bottom: 0;
  right: 0;
}
ul a:hover,
ul a.router-link-exact-active {
  color: #ffffff;
}
ul a:hover:before,
ul a.router-link-exact-active:before,
ul a:hover:after,
ul a.router-link-exact-active:after {
  width: 100%;
}

@media only screen and (min-width: 768px) {
  ul {
    font-size: 1rem;
  }
}
</style>