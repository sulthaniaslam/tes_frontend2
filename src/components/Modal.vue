<template>
    <div class="modal-test">
        <div v-if="(tipe.tipe.tipe == 1)">
            <div class="content-modal1">
                <div class="modal-title">{{ this.tipe.tipe.title }}</div>
                <div class="modal-content">
                    <div class="row">
                        <div class="col-6">
                            <select name="" id="" class="form-select">
                                <option value="">Database</option>
                                <option value=""></option>
                            </select>
                        </div>
                        <div class="col-6">
                            <select name="" id="" class="form-select">
                                <option value="">User</option>
                                <option value=""></option>
                            </select>
                        </div>
                    </div>
                    <div class="row mt-3">
                        <div class="col-6">
                            <select name="" id="" class="form-select">
                                <option value="">Branch</option>
                                <option value=""></option>
                            </select>
                        </div>
                    </div>

                </div>
                <div class="modal-footer">
                    <button class="close" @click="$emit('close-modal')">Cancel</button>
                    <button class="save">Save</button>
                </div>
            </div>
        </div>
        <div v-else-if="(tipe.tipe.tipe == 2)">
            <div class="content-modal2">
                <div class="modal-title">{{this.tipe.tipe.title}}</div>
                <div class="modal-content">
                    <div class="row">
                        <div class="col-6">
                            <div class="form-check">
                                <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1">
                                <label class="form-check-label text-radio" for="flexRadioDefault1">
                                    Update Data
                                </label>
                                <br>
                                <span class="text-radio-small">Existing data will be updated</span>
                            </div>
                        </div>
                        <div class="col-6">
                            <div class="form-check">
                                <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1">
                                <label class="form-check-label text-radio" for="flexRadioDefault1">
                                    Skip Data
                                </label>
                                <br>
                                <span class="text-radio-small">Will add new data</span>
                            </div>
                        </div>
                    </div>
                </div>
                <button class="close" @click="$emit('close-modal')">Close</button>
                <button class="save">Save</button>
            </div>
        </div>
        <div v-else-if="(tipe.tipe.tipe == 3)">
            <div class="content-modal3">
                <div class="modal-content text-center">
                    <div class="row">
                        <div class="col-12">
                            <p style="color : #7E7D7D;">Are you sure to save ?</p>
                        </div>
                    </div>
                </div>
                <button class="close" @click="$emit('close-modal')">Close</button>
                <button class="save" @click="onSave()">Save</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        'tipe'
    ],
    created() {
        // console.log(this.tipe.tipe.title);
    },
    methods: {
        onSave(){
            this.$router.push({
                path: '/customer'
            })
        }
    },
}
</script>

<style>
    .modal-test{
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.3);
        z-index: 2;
    }
    .content-modal1{
        position: absolute;
        max-width: 90%;
        /* justify-content: center;
        align-items: center; */
        width: 755px;
        height: 286px;
        left: 380px;
        top: 33px;
        background: #fff;
        display: flex;
        
    }
    .content-modal2{
        position: absolute;
        max-width: 90%;
        /* justify-content: center;
        align-items: center; */
        width: 438px;
        height: 233px;
        left: 530px;
        top: 33px;
        background: #fff;
        display: flex;
        
    }
    .content-modal3{
        position: absolute;
        max-width: 90%;
        /* justify-content: center;
        align-items: center; */
        width: 438px;
        height: 233px;
        left: 530px;
        top: 33px;
        background: #fff;
        display: flex;
        
    }
    .close{
        position: absolute;
        left: 30px;
        top: 75%;
        border: none;
        background-color: #F2F2F2;
        width: 150px;
        height: 42px;
        color: #777;
    }
    .save{
        display: flex;
        flex-direction: column;
        padding: 10px 20px;
        gap: 10px;
        position: absolute;
        width: 150px;
        height: 42px;
        right: 35px;
        top: 75%;
        background: #FFB800;
        border-radius: 3px;
        border: none;
        color: white;
    }
    .modal-title{
        position: absolute;
        width: 104px;
        height: 21px;
        left: 30px;
        top: 20px;
        font-family: 'Open Sans';
        font-style: normal;
        font-weight: 700;
        font-size: 14px;
        line-height: 150%;
        color: #686868;
    }
    .modal-content{
        position: absolute;
        width: 92%;
        height: 90px;
        left: 30px;
        top: 60px;
    }
    .text-radio{
        font-family: 'Open Sans';
        font-style: normal;
        font-weight: 700;
        font-size: 12px;
        line-height: 140%;

        /* identical to box height, or 17px */

        /* Color pallate/Neutral/90 */
        color: #686868;
    }
    .text-radio-small{
        font-family: 'Open Sans';
        font-style: italic;
        font-weight: 400;
        font-size: 12px;
        line-height: 140%;

        /* identical to box height, or 17px */

        /* Color pallate/Neutral/30 */
        color: #CCCCCC;
    }
</style>

