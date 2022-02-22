<script>
    import { navigate } from "svelte-routing";
    

    let innerWidth = window.innerWidth;
    let innerHeight = window.innerHeight;

    let userEmail = 'asdf@gmail.com';

    class File {
        constructor(file, image, title, date) {
            this.file = file;
            this.image = image;
            this.title = title;
            this.date = date;
        }
    }

    let fileArray = [0];

    // 배열에 파이어베이스 저장 파일 불러오기
    fileArray[0] = new File('파이어베이스 파일 넣기', `https://media.vlpt.us/images/jacoblee19/post/37558a06-0678-4657-adb2-e1e957e6d8f0/html.webp`, '쇼핑몰 사이트', '1분전')
    fileArray[1] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[2] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[3] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[4] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[5] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[6] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[7] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[8] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[9] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')
    fileArray[10] = new File('아무거나', `https://images.pexels.com/photos/5213347/pexels-photo-5213347.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260`, '아무거니', '1일전')

    function clickFile() {
        alert('파일 불러오기')
    }

     function clickCreateFileButton() {
        // 파일 만들기 버튼 누르면 
        navigate("editor", { replace: true });
    }

    

</script>


<svelte:window bind:innerWidth bind:innerHeight />


<main style="width: {innerWidth}px; height: {innerHeight}px; ">
    <div id="user-section" style="width: {innerWidth}px;">
        <div id="user-email">{userEmail}</div>
    </div>
    <div id="home-section-box" style="width: {innerWidth}px;">
        <div id="home-section" style="height: {innerHeight-50}px">
        
            <div id="page-title">My Workspace</div>
            <button id="create-file-button" on:click={clickCreateFileButton}>
                <div class="page-icon-1">
                </div>
                <div id="button-title">
                    New File
                </div>
                <div class="plus-icon">
                </div>
            </button>
            <div id="file-array" class="grid-container scroll-style" >
                {#each fileArray as file}
                    <div class="grid-item" on:click={clickFile}>
                        <!-- svelte-ignore a11y-missing-attribute -->
                        <img class="image-class" src={file.image}>
                        <div class="flex-row">
                            <div class="page-icon-2">
                            </div>
                            <div class="file-title">
                                {file.title}
                            </div>
                            <div class="file-date">
                                {file.date}
                            </div>
                        </div>
                    </div>
                {/each}
                
            </div>
        </div>
    </div>
    
</main>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;700&display=swap');

    main {
        background-color: #ffffff;
        display: flex;
        justify-content: center;
        flex-direction: column;
        overflow:hidden;
    }

    #user-section {
        height: 50px;
        display: flex;
        justify-content: right;
        flex-direction: row;
    }

    #user-email {
        color: #8E8E8E;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 400;
        font-size: 12px;
        padding-top: 14px;
        margin-right: 30px;
    }

    #home-section {
        width: 920px;
        display: flex;
        justify-content: space-evenly;
        flex-direction: column;
    }

    #home-section-box {
        display: flex;
        justify-content: center;
        flex-direction: row;
    }

    #page-title {
        color: #282828;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 700;
        font-size: 36px;
    }

    #create-file-button {
        width: 180px;
        height: 50px;
        background-color: #18A0FB;
        border: 0;
        border-radius: 8px;
        display: flex;
        justify-content: space-around;
        flex-direction: row;
    }

    #create-file-button:focus {
        border: 0;
    }

    #button-title {
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 700;
        font-size: 18px;
        color: #ffffff;
        margin-top: 5px;
    }

    .page-icon-1 {
        width: 12px;
        height: 16px;
        background-image: url('../icon/pageIcon.png');
        margin-top: 10px;
    }

    .page-icon-2 {
        width: 12px;
        height: 16px;
        background-image: url('../icon/pageIcon2.png');
        margin-top: 18px;
    }

    .plus-icon {
        width: 9px;
        height: 9px;
        background-image: url('../icon/plusIcon.png');
        margin-top: 14px;
    }

    #file-array {
        width: 900px;
        height: 700px;
    }


    .scroll-style {
        overflow: scroll;
        overflow-x: hidden;
    }

    .scroll-style::-webkit-scrollbar {
        width: 4px;
    }

    .scroll-style:hover::-webkit-scrollbar {
        width: 4px;
    }

    .scroll-style::-webkit-scrollbar-track {
        background-color: transparent;
    }

    .scroll-style::-webkit-scrollbar-thumb {
        border-radius: 2px;
        background-color: #C4C4C4;
    }

    .scroll-style::-webkit-scrollbar-button {
        width: 0;
        height: 0;
    }

    .grid-container {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }

    .grid-item {
        width: 180px;
        height: 220px;
        border: 1px solid #E5E5E5;
        margin-bottom: 17px;
        display: flex;
        flex-direction: column;
    }

    .image-class {
        width: 180px;
        height: 170px;
    }

    .flex-row {
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
    }

    .file-title {
        color: #404040;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 400;
        font-size: 14px;
        margin-top: 15px;
    }

    .file-date {
        color: #949494;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 400;
        font-size: 10px;
        margin-top: 18px;
    }

    
</style>