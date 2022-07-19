<template>
    <div>
        <div class="nav-left">
            <div class="box-nav">
                <div class="menu-top">
                    <a href="#">
                        <img src="../../src/assets/logo1.png" alt="" class="menu-icon">
                    </a>
                    <a href="#">
                        <img src="../../src/assets/logo2.png" alt="" class="menu-icon">
                    </a>
                    <a href="#">
                        <img src="../../src/assets/logo3.png" alt="" class="menu-icon">
                    </a>
                </div>
                <div class="menu-bottom">
                    <a href="#">
                        <img src="../../src/assets/logo4.png" alt="" class="menu-icon">
                    </a>
                    <a href="#">
                        <img src="../../src/assets/logo5.png" alt="" class="menu-icon">
                    </a>
                    <a href="#">
                        <img src="../../src/assets/logo6.png" alt="" class="menu-icon">
                    </a>
                    <a href="#">
                        <img src="../../src/assets/logo7.png" alt="" class="menu-icon">
                    </a>
                    <a href="#">
                        <img src="../../src/assets/logo8.png" alt="" class="menu-icon">
                    </a>
                </div>
            </div>

            <button class="button-show" @click="hideToggle()" v-if="!hide">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-right" viewBox="0 0 16 16">
                    <path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z"/>
                </svg>
            </button>
        </div>
        <div class="nav-right" v-if="hide">
            <span class="nav-brand">Master</span>
            <div class="menu">
                <ul>
                    <li class="nav-link"><img src="../../src/assets/logo9.png" alt="" class="menu-icon"> Branch</li>
                    <li class="nav-link"><img src="../../src/assets/logo10.png" alt="" class="menu-icon"> Users</li>
                    <li class="nav-link text-warning"><img src="../../src/assets/logo11.png" alt="" class="menu-icon"> Customer</li>
                </ul>
            </div>
            <button class="button" @click="hideToggle()">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
                    <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"/>
                </svg>
            </button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            hide: true,
        }
    },
    methods: {
        hideToggle(){
            this.hide = !this.hide
        },
    },
}
</script>

<style>
    .box-nav{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 0px;
        gap: 156px;
        width: 45px;
        height: 615px;
        flex: none;
        order: 0;
        align-self: stretch;
        flex-grow: 1;
    }
    .nav-left{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px 13px 40px;
        gap: 30px;
        position: absolute;
        width: 71px;
        height: 725px;
        left: 0px;
        top: 0px;

        background: linear-gradient(0deg, #FFE299 -2.27%, #FFFDF9 39.19%);
    }
    .menu-icon{
        width: 40px;
        height: 40px;
        flex: none;
        order: 0;
        flex-grow: 0;
        border-radius: 5px;
    }
    .nav-left .menu-top{
        /* background-color: crimson; */
        width: 45px;
        height: 164px;
        flex: none;
        order: 0;
        flex-grow: 0;
    }
    .nav-left .menu-top img{
        margin-bottom: 1em;
    }
    .nav-left .menu-bottom{
        /* background-color: red; */
        margin-top: 3.5em;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 0px;
        gap: 16px;
        width: 30px;
        height: 260px;
        flex: none;
        order: 0;
        flex-grow: 0;
    }


    /*  */
    /*  */
    
    .nav-right{
        width: 200px;
        height: 725px;
        margin-left: 4.5em;
        background: #FFFFFF;
        flex: none;
        order: 0;
        flex-grow: 0;
    }
    .nav-right .nav-brand{
        position: absolute;
        padding-top: 1em;
        padding-left: 1.5em;
        font-family: 'Open Sans';
        font-style: normal;
        font-weight: 600;
        line-height: 150%;
        color: #686868;
    }
    .nav-right .menu{
        position: absolute;
        padding-top: 3em;
        font-family: 'Open Sans';
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 150%;
        color: #686868;
    }
    .nav-right .menu .nav-link{
        margin-bottom: 1.5em;
        margin-left: 1em;
    }
    .nav-right .menu .nav-link img{
        width: 15px;
        height: 15px;
        left: 1em;
        top: 1em;
        filter: drop-shadow(0px 2px 4px rgba(120, 120, 120, 0.15));
    }
    .nav-right .menu ul li .menu-icon{
        width: 20px;
        height: 20px;
    }

    .button{        
        position: absolute;
        width: 35px;
        height: 35px;
        left: 255px;
        top: 570px;
        background: #FFB800;
        box-shadow: 1px 2px 8px rgba(250, 177, 9, 0.25);
        border-radius: 3px;
        color: white;
    }
    .button-show{        
        position: absolute;
        width: 35px;
        height: 35px;
        left: 50px;
        top: 625px;
        background: #FFB800;
        box-shadow: 1px 2px 8px rgba(250, 177, 9, 0.25);
        border-radius: 3px;
        color: white;
    }
    /*  */
    /*  */
    
</style>