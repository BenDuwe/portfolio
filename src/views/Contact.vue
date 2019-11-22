<template>
  <div class="contact anchor">
    <a name="contact"></a>
    <h2>Contact</h2>
    <p>Have a question?</p>
    <p>Or perhaps want to hire me?</p>
    <button @click="toggleState = !toggleState">
      <a title="Get in touch!">Get in touch!</a>
    </button>
    <div class="pop-up" :class="{ hide: toggleState }" @click.self="closePopup" @close="closePopup">
      <div class="pop-up__content">
        <div class="pop-up__content__close" @click="closePopup">X</div>
        <h3>Personal contact details:</h3>
        <ul>
          <li>
            <a href="mailto:benduwee@gmail.com">
              <svg
                width="30"
                height="24"
                xmlns="http://www.w3.org/2000/svg"
                fill-rule="evenodd"
                clip-rule="evenodd"
              >
                <path
                  d="M24 21h-24v-18h24v18zm-23-16.477v15.477h22v-15.477l-10.999 10-11.001-10zm21.089-.523h-20.176l10.088 9.171 10.088-9.171z"
                  fill="#2c383b"
                />
              </svg> benduwee@gmail.com
            </a>
          </li>
          <li>
            <a href="tel:+32473496230">
              <svg
                width="30"
                height="24"
                xmlns="http://www.w3.org/2000/svg"
                fill-rule="evenodd"
                clip-rule="evenodd"
              >
                <path
                  d="M18 24h-12c-1.104 0-2-.896-2-2v-20c0-1.104.896-2 2-2h12c1.104 0 2 .896 2 2v20c0 1.104-.896 2-2 2zm1-5.083h-14v3.083c0 .552.449 1 1 1h12c.552 0 1-.448 1-1v-3.083zm-7 3c-.553 0-1-.448-1-1s.447-1 1-1c.552 0 .999.448.999 1s-.447 1-.999 1zm7-17h-14v13h14v-13zm-1-3.917h-12c-.551 0-1 .449-1 1v1.917h14v-1.917c0-.551-.448-1-1-1zm-4.5 1.917h-3c-.276 0-.5-.224-.5-.5s.224-.5.5-.5h3c.276 0 .5.224.5.5s-.224.5-.5.5z"
                  fill="#2c383b"
                />
              </svg> 0473/496230
            </a>
          </li>
        </ul>
      </div>
    </div>
    <p>You can also find me on:</p>
    <ul class="social">
      <li>
        <a href="https://www.linkedin.com/in/benduwé">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              d="M0 0v24h24v-24h-24zm8 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.397-2.586 7-2.777 7 2.476v6.759z"
              fill="#2c383b"
            />
          </svg>
        </a>
      </li>
      <li>
        <a href="https://github.com/BenDuwe">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              d="M0 0v24h24v-24h-24zm14.534 19.59c-.406.078-.534-.171-.534-.384v-2.195c0-.747-.262-1.233-.55-1.481 1.782-.198 3.654-.875 3.654-3.947 0-.874-.311-1.588-.824-2.147.083-.202.357-1.016-.079-2.117 0 0-.671-.215-2.198.82-.639-.18-1.323-.267-2.003-.271-.68.003-1.364.091-2.003.269-1.528-1.035-2.2-.82-2.2-.82-.434 1.102-.16 1.915-.077 2.118-.512.56-.824 1.273-.824 2.147 0 3.064 1.867 3.751 3.645 3.954-.229.2-.436.552-.508 1.07-.457.204-1.614.557-2.328-.666 0 0-.423-.768-1.227-.825 0 0-.78-.01-.055.487 0 0 .525.246.889 1.17 0 0 .463 1.428 2.688.944v1.489c0 .211-.129.459-.528.385-3.18-1.057-5.472-4.056-5.472-7.59 0-4.419 3.582-8 8-8s8 3.581 8 8c0 3.533-2.289 6.531-5.466 7.59z"
              fill="#2c383b"
            />
          </svg>
        </a>
      </li>
      <li>
        <a href="https://www.facebook.com/benduwee">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              d="M0 0v24h24v-24h-24zm16 7h-1.923c-.616 0-1.077.252-1.077.889v1.111h3l-.239 3h-2.761v8h-3v-8h-2v-3h2v-1.923c0-2.022 1.064-3.077 3.461-3.077h2.539v3z"
              fill="#2c383b"
            />
          </svg>
        </a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Contact",
  data() {
    return {
      toggleState: true
    };
  },
  methods: {
    closePopup: function() {
      this.toggleState = !this.toggleState;
    }
  }
};
</script>
<style scoped>
.contact {
  /* position: relative; */
  padding: 1rem;
}
ul {
  list-style: none;
}
.social {
  display: flex;
  justify-content: center;
}
.social li {
  margin: 0.5rem;
}
button {
  width: 8rem;
  margin: 1rem 0;
}
button a {
  font-size: 1.1rem;
}

/* button {
    padding: 5px 0;
    width: 6rem;
    border: 2px inset #8b2635;
  }
  button:hover {
    border: 2px outset #8b2635;
  } */
.pop-up {
  position: fixed;
  background-color: #44444467;
  top: 3.9rem;
  left: 0;
  width: 100vw;
  height: calc(100vh - 3.9375rem);
  z-index: 10;

  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 0;
  transition: margin-top 0.2s ease-in;
}
.hide {
  margin-top: -100vh;
}

.pop-up__content {
  background-color: #fcfcfc;
  padding: 3rem;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.pop-up__content h3 {
  margin-bottom: 2rem;
  position: relative;
}
.pop-up__content h3::after {
  position: absolute;
  bottom: -6px;
  right: 0;
  content: "";
  width: 100%;
  height: 3px;
  background-color: #4bc0b0;
}

.pop-up__content ul {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.pop-up__content li {
  margin-bottom: 0.5rem;
}
.pop-up__content ul a {
  /* text-transform: uppercase; */
  font-weight: 800;
  text-decoration: none;
  color: inherit;
  display: flex;
  align-items: center;
}

.pop-up__content__close {
  cursor: pointer;
  color: #2c383b;
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
  font-weight: 900;
  transition: color 0.1s ease-in-out;
}
.pop-up__content__close:hover {
  color: #ff312e;
}
</style>
