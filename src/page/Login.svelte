<script>
    import { navigate } from "svelte-routing";
    

    let innerWidth = window.innerWidth;
    let innerHeight = window.innerHeight;

    function clickLoginButton() {
        // 로그인 버튼누르면 로그인페이지 연결
        navigate("home", { replace: true });
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