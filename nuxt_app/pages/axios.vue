<template>
  <section class="container">
  <h1>{{title}}</h1>
  <p>{{message}}</p>
  </section>
</template>

<script>
import firebase from "firebase";

export default {
  data: function() {
    return {
      title:'Auth',
      message: 'this is message.',
    };
  },
  created: function() {
    var config = { // ●各自の設定を記述
      apiKey: "XXX",
      authDomain: "XXX.firebaseapp.com",
      databaseURL: "https://XXX.firebaseio.com",
      projectId: "XXX",
      storageBucket: "XXX.appspot.com",
      messagingSenderId: "XXX"
    };
    firebase.initializeApp(config);

    var provider = new firebase.auth.GoogleAuthProvider();
    var self = this;
    firebase.auth().signInWithPopup(provider)
      .then(function(result) {
      self.message = result.user.displayName + ', ' 
        + result.user.email;
      });
  },
};
</script>