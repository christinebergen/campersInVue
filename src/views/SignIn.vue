<template>
  <div class="mx-8 my-8">
    <!-- logo -->
    <div class="float-left">
      <div class="pb-6">
        <a href="/"
          ><img
            src="../assets/logo_layered2.png"
            alt="camp logo"
            class="w-12 sm:w-20 rounded-full hover:scale-75 transition-all"
        /></a>
      </div>
    </div>
    <!-- logo -->

    <!-- sign in -->
    <div class="clear-both flex items-center justify-center mx-8">
      <div class="w-full md:w-8/12 bg-[#7993A0] py-12 md:py-16 rounded-xl mt-6">
        <form action="">
          <!-- title -->
          <h1
            class="flex justify-center text-3xl md:text-4xl pb-8 md:pb-10 text-white"
          >
            Welcome Back!
          </h1>

          <!-- email -->
          <div class="flex justify-center pb-4 md:pb-6">
            <input
              class="rounded-md text-lg md:text-xl py-1 md:py-3 w-full mx-20 md:mx-32 pl-8"
              type="email"
              name="email"
              placeholder="Email"
              id="signin-email"
              required
            />
          </div>

          <!-- password -->
          <div class="flex justify-center pb-4 sm:pb-6">
            <input
              class="rounded-md text-lg md:text-xl py-1 md:py-3 w-full mx-20 md:mx-32 pl-8"
              type="password"
              name="password"
              placeholder="Password"
              id="signin-password"
              required
            />
          </div>

          <!-- sign in button -->
          <div class="flex justify-center rounded-md pb-4 md:pb-6">
            <button
              class="bg-[#3E563E] rounded-md text-md md:text-lg py-0 md:py-1 px-8 md:px-20 text-white hover:bg-[#93A889]"
              id="signin"
            >
              Sign In
            </button>
          </div>

          <div class="flex justify-center items-center">
            <button
              type="button"
              id="google-signin"
              class="text-white bg-blue-700 hover:bg-purple-700 focus:ring-4 focus:outline-none focus:ring-[#4285F4]/50 font-medium rounded-lg text-sm px-5 py-2.5 text-center inline-flex items-center dark:focus:ring-[#4285F4]/55 mb-2"
            >
              <svg
                class="w-4 h-4 mr-2 -ml-1"
                aria-hidden="true"
                focusable="false"
                data-prefix="fab"
                data-icon="google"
                role="img"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 488 512"
              >
                <path
                  fill="currentColor"
                  d="M488 261.8C488 403.3 391.1 504 248 504 110.8 504 0 393.2 0 256S110.8 8 248 8c66.8 0 123 24.5 166.3 64.9l-67.5 64.9C258.5 52.6 94.3 116.6 94.3 256c0 86.5 69.1 156.6 153.7 156.6 98.2 0 135-70.4 140.8-106.9H248v-85.3h236.1c2.3 12.7 3.9 24.9 3.9 41.4z"
                ></path>
              </svg>
              Sign in with Google
            </button>
          </div>

          <div class="flex justify-center">
            <button
              class="underline text-sm md:text-md text-white"
              id="open-modal-button"
            >
              Sign up
            </button>
          </div>
        </form>
      </div>

      <!-- sign up modal -->
      <div>
        <div
          id="signup-modal"
          @click="signupModal"
          class="fixed top-32 md:top-60 left-0 right-0 bottom-0 w-48 md:w-80 h-80 md:h-96 mx-auto hidden"
        >
          <div class="bg-[#CED9DF] p-6 rounded-lg">
            <form>
              <h2 class="text-center pb-4 font-bold text-lg">Sign Up</h2>

              <input
                type="email"
                class="w-full border border-gray-400 p-2 mb-4 rounded-lg"
                placeholder="Email"
                id="signup-email"
              />
              <input
                type="password"
                class="w-full border border-gray-400 p-2 mb-4 rounded-lg"
                placeholder="Password"
                id="signup-password"
              />

              <div class="flex justify-center">
                <button
                  class="bg-[#3E563E] text-white py-2 px-4 rounded-xl hover:bg-[#93A889]"
                  id="signup"
                >
                  Sign Up
                </button>
              </div>
            </form>
          </div>
        </div>
        <!-- sign up modal -->
      </div>
    </div>
    <!-- sign in -->
  </div>
</template>

<script setup>
import top from '../components/Top.vue';

// const openModalButton = document.getElementById("open-modal-button");
// const signupModal = document.getElementById("signup-modal");

// openModalButton.addEventListener("click", () => {
//   signupModal.classList.remove("hidden");
// });

// signupModal.addEventListener("click", (event) => {
//   if (event.target === signupModal) {
//     signupModal.classList.add("hidden");
//   }
// });
</script>
<script type="module">
// Import the functions you need from the SDKs you need
import { initializeApp } from 'https://www.gstatic.com/firebasejs/9.17.2/firebase-app.js';
import { getAnalytics } from 'https://www.gstatic.com/firebasejs/9.17.2/firebase-analytics.js';
import {
  getAuth,
  createUserWithEmailAndPassword,
  signInWithEmailAndPassword,
  signOut,
  GoogleAuthProvider,
  signInWithPopup,
  onAuthStateChanged,
  sendEmailVerification,
} from 'https://www.gstatic.com/firebasejs/9.17.2/firebase-auth.js';

// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: 'AIzaSyB2HUFQ8BxbbiqiLQsoxmtZRcUowxHQMP8',
  authDomain: 'happycampers-fe5ba.firebaseapp.com',
  projectId: 'happycampers-fe5ba',
  storageBucket: 'happycampers-fe5ba.appspot.com',
  messagingSenderId: '787972906610',
  appId: '1:787972906610:web:d42a750242852a4589aceb',
  measurementId: 'G-BHXVG7KBWD',
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
//const analytics = getAnalytics(app);
const auth = getAuth();
const provider = new GoogleAuthProvider();

console.log(app);

document.getElementById('signup').addEventListener('click', function () {
  const email = document.getElementById('signup-email').value;
  const password = document.getElementById('signup-password').value;
  //create user with email and password
  createUserWithEmailAndPassword(auth, email, password).then(
    (userCredential) => {
      // Signed in
      //if signed in, redirect to home/index.html
      //window.location.href = "/home/index.html";

      const user = userCredential.user;
      console.log(email, password);
      //if user created successfully, alert user create successfully
      alert('User created successfully');
    }
  );
  // .catch((error) => {
  //   const errorCode = error.code;
  //   const errorMessage = error.message;
  //   console.log(errorCode);
  //   alert(errorMessage);
  //   // ..
  // });
});

const loginEmailPassword = async () => {
  const email = document.getElementById('signin-email').value;
  const password = document.getElementById('signin-password').value;

  try {
    const userCredential = await signInWithEmailAndPassword(
      auth,
      email,
      password
    );
    console.log(userCredential.user);
  } catch {
    console.log(error);
    alert('Invalid email or password');
  }
};
signin.addEventListener('click', loginEmailPassword);

// {
//   const user = userCredential.user;
//   console.log(user);
//   alert("User signed in successfully");
//   // ...
// })
// .catch((error) => {
//   const errorCode = error.code;
//   const errorMessage = error.message;
//   console.log(errorCode);
//   alert(errorMessage);
//   // ..
// });
// });

//sign in with google account
document.getElementById('google-signin').addEventListener('click', function () {
  signInWithPopup(auth, provider).then((result) => {
    // This gives you a Google Access Token. You can use it to access the Google API.
    const credential = GoogleAuthProvider.credentialFromResult(result);
    const token = credential.accessToken;
    // The signed-in user info.
    const user = result.user;
    // IdP data available using getAdditionalUserInfo(result)
    // ...
    //  }).catch((error) => {
    //   // Handle Errors here.
    //   const errorCode = error.code;
    //   const errorMessage = error.message;
    //   // The email of the user's account used.
    //   const email = error.customData.email;
    //   // The AuthCredential type that was used.
    //   const credential = GoogleAuthProvider.credentialFromError(error);
    //   // ...
  });
});

onAuthStateChanged(auth, (user) => {
  if (user !== null) {
    console.log('user logged in: ', user);
    window.location.href = '../home/index.html';
  } else {
    console.log('user logged out');
  }
});

sendEmailVerification(auth.currentUser).then(() => {
  alert('Email verification sent!');
  // Verification email sent!
  // ...
});

// const monitorAuthState = async () =>{
// onAuthStateChanged(auth, (user) => {
//   if (user) {
//     // User is signed in, see docs for a list of available properties
//     // https://firebase.google.com/docs/reference/js/firebase.User

//     console.log(user);
//     window.location.href = "../home/index.html";
//     // ...
//   } else {

//     // User is signed out
//     // ...
//   }
// });
// }
//   monitorAuthState();
</script>
