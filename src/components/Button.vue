<template>
    <div>
        <div v-if="(tipe.class == 'success')">
            <button class="success">
                {{tipe.text}}
            </button>
        </div>
        <div v-else-if="(tipe.class == 'warning')">
            <button class="warning">
                {{tipe.text}}
            </button>
        </div>
        <div v-else-if="(tipe.class == 'info')">
            <button class="info">
                {{tipe.text}}
            </button>
        </div>
        <div v-else-if="(tipe.class == 'danger')">
            <button class="danger">
                {{tipe.text}}
            </button>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        'tipe'
    ],
    created() {
        // console.log(this.tipe);
    },
}
</script>

<style>
    .success{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 8px;
        gap: 10px;
        /* position: absolute; */
        width: 110px;
        height: 40px;
        left: 1193px;
        top: 48px;
        background: #00CC39;
        border-radius: 3px;
        border: none;
        color: white;    
    }
    .warning{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 8px;
        gap: 10px;
        /* position: absolute; */
        width: 110px;
        height: 40px;
        left: 1193px;
        top: 48px;
        background: #FFCD4C;
        border-radius: 3px;
        border: none;
        color: white;    
    }
    .info{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 8px;
        gap: 10px;
        /* position: absolute; */
        width: 110px;
        height: 40px;
        left: 1193px;
        top: 48px;
        background: #4AB8F6;
        border-radius: 3px;
        border: none;
        color: white;    
    }
    .danger{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 8px;
        gap: 10px;
        /* position: absolute; */
        width: 110px;
        height: 40px;
        left: 1193px;
        top: 48px;
        background: #FE2700;
        border-radius: 3px;
        border: none;
        color: white;
    }

</style>