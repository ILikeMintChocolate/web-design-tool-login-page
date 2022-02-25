



<script>
    import { navigate } from "svelte-routing";
    
    // 파이어베이스
    import { initializeApp } from "firebase/app";
    import { getAnalytics } from "firebase/analytics";
    import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth";

    const firebaseConfig = {
        apiKey: "AIzaSyCAPjucpY0gKqRbPZpJW4rugAfvhadrBCg",
        authDomain: "webdesigntool-6c99e.firebaseapp.com",
        projectId: "webdesigntool-6c99e",
        storageBucket: "webdesigntool-6c99e.appspot.com",
        messagingSenderId: "548202789405",
        appId: "1:548202789405:web:c416d76ff145ac0f25e4f4",
        measurementId: "G-DJFTVDBQT8"
    };

    
    const app = initializeApp(firebaseConfig);
    const analytics = getAnalytics(app);

    const provider = new GoogleAuthProvider();
    const auth = getAuth();
    // 파이어베이스

    
    

    let innerWidth = window.innerWidth;
    let innerHeight = window.innerHeight;

    function clickLoginButton() {
        signInWithPopup(auth, provider).then((result) => {
            const credential = GoogleAuthProvider.credentialFromResult(result);
            const token = credential.accessToken;
            const user = result.user;
            navigate("home", { replace: true });
        }).catch((error) => {
            const errorCode = error.code;
            const errorMessage = error.message;
            const email = error.email;
            const credential = GoogleAuthProvider.credentialFromError(error);
        });
    }

</script>


<svelte:window bind:innerWidth bind:innerHeight />


<main style="width: {innerWidth}px; height: {innerHeight}px">
    <div id="login-section" style="margin-top: {(innerHeight - 600)/2 - 20}px;">
        <div style="margin-left: 70px;">
            <h1>
                Welcome !
            </h1>
            <h3>
                Please Sign in to continue
            </h3>
        
        </div>
        <div class="center">
            <button on:click={clickLoginButton}>
                <div id="github-icon"></div>
                <div>Sign in With GitHub</div>
            </button>
        </div>
        
        <div></div>
    </div>

</main>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;700&display=swap');

    main {
        background-color: #383838;
        display: flex;
        justify-content: center;
    }

    #login-section {
        width: 340px;
        height: 600px;
        background-color: #ffffff;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
    }

    h1 {
        color: #282828;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 700;
        font-size: 30px;
    }

    h3 {
        color: #8E8E8E;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 400;
        font-size: 16px;
        margin-top: -10px;
    }

    button {
        width: 200px;
        height: 40px;
        border: 2px solid #C4C4C4;
        border-radius: 10px;
        background-color: #ffffff;
        cursor: pointer;
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
    }

    button div {
        color: #404040;
        font-size: 14px;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 400;
    }

    button #github-icon {
        width: 16px;
        height: 16px;
        margin-top: 3px;
        background-image: url("../icon/githubIcon.png");
    }


    .center {
        display: flex;
        justify-content: center;
        flex-direction: row;
    }
</style>