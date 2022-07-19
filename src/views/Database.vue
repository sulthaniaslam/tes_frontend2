<template>
    <div>
        <Nav></Nav>

        <div class="content">
            <div v-if="modal">
                <Modal 
                    v-on:close-modal="closeModal" 
                    v-bind:tipe="{ tipe }"
                    ></Modal>
            </div>
            <div class="row row-head">
                <div class="col-2">
                    <div class="content-title">Database</div>
                    <br>
                    <small class="content-title-sub">Sync Database</small>
                </div>
                <div class="col-10">
                    <button class="button-back" @click="onBack()">Back</button>
                    <button class="button-save" @click="modalToggle('Save Database', 3)">Save Database</button>
                </div>
            </div>


            <div class="row justify-content-between">
                <div class="col-4">
                    <!-- One of two columns -->
                    <input type="search" name="" id="" style="margin-left: 6.5%; margin-bottom: 3%; background-color: #f6f6f6; border: none;" placeholder="search">
                </div>
                <div class="col-4">
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                    <span style="color: #686868;">
                        <img src="../../src/assets/logo14.png" alt="" style="width: 12px;">
                        <div class="fw-bold d-inline" style="color: #00CC39;"> 95</div> Database Completed
                    </span>
                    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                    <span style="color: #686868;">
                        <img src="../../src/assets/logo15.png" alt="" style="width: 12px;">
                        Add New
                    </span>
                </div>
            </div>


            <div class="row">
                <div class="col-12">
                    <div class="container">
                        <div class="container">
                            <table class="table table-striped text-center">
                                <thead>
                                    <tr>
                                        <th class="text-center">#</th>
                                        <th>ID</th>
                                        <th>Code</th>
                                        <th>Name</th>
                                        <th>Branch</th>
                                        <th>Action</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="text-center">1</td>
                                        <td>100</td>
                                        <td>CJ001</td>
                                        <td>ASD</td>
                                        <td>Jakarta</td>
                                        <td>
                                            <img src="../../src/assets/logo16.png" alt="" style="width: 24px; ">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">2</td>
                                        <td>100</td>
                                        <td>CJ001</td>
                                        <td>ASD</td>
                                        <td>Jakarta</td>
                                        <td>
                                            <img src="../../src/assets/logo16.png" alt="" style="width: 24px; ">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">3</td>
                                        <td>100</td>
                                        <td>CJ001</td>
                                        <td>ASD</td>
                                        <td>Jakarta</td>
                                        <td>
                                            <img src="../../src/assets/logo16.png" alt="" style="width: 24px; ">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">4</td>
                                        <td>100</td>
                                        <td>CJ001</td>
                                        <td>ASD</td>
                                        <td>Jakarta</td>
                                        <td>
                                            <img src="../../src/assets/logo16.png" alt="" style="width: 24px; ">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">5</td>
                                        <td>100</td>
                                        <td>CJ001</td>
                                        <td>ASD</td>
                                        <td>Jakarta</td>
                                        <td>
                                            <img src="../../src/assets/logo16.png" alt="" style="width: 24px; ">
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>

                        <div class="container">
                            <div class="row mt-5">
                                <div class="col-12">

                                    <nav aria-label="...">
                                        <ul class="pagination">
                                            <li class="page-item disabled">
                                                <span class="pagination-link">
                                                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
                                                        <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"/>
                                                    </svg>
                                                </span>
                                            </li>
                                            <li class="page-item"><a class="pagination-link" href="#">1</a></li>
                                            <li class="page-item active" aria-current="page">
                                                <span class="pagination-link">2</span>
                                            </li>
                                            <li class="page-item"><a class="pagination-link" href="#">3</a></li>
                                            <li class="page-item"><a class="pagination-link" href="#">4</a></li>
                                            <li class="page-item"><a class="pagination-link" href="#">5</a></li>
                                            <li class="page-item">
                                                <a class="pagination-link" href="#">
                                                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-right" viewBox="0 0 16 16">
                                                        <path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z"/>
                                                    </svg>
                                                </a>
                                            </li>
                                        </ul>
                                    </nav>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <Footer></Footer>
    </div>
</template>

<script>
import Nav from '../components/Nav.vue'
import Footer from '../components/Footer.vue'
import Modal from '../components/Modal.vue'

export default {
    components: {
        Nav,
        Modal,
        Footer
    },
    data() {
        return {
            modal: false,
            tipe: {
                title : '',
                tipe : 0,
            }
        }
    },
    methods: {
        onBack(){
            this.$router.push({
                path: '/customer'
            })
        },
        modalToggle(title, tipe){
            this.tipe.title = title
            this.tipe.tipe = tipe
            
            this.modal = !this.modal
        },
        closeModal(){
            this.modal = !this.modal
        },
        toDatabase(){
            this.$router.push({
                path: 'database'
            })
        }
    },
}
</script>

<style>
    body{
        background-color: #f2f2f2;
    }

    .content-title{
        position: absolute;
        width: 223px;
        height: 21px;
        left: 25px;
        top: 30px;
        font-family: 'Open Sans';
        font-style: normal;
        font-weight: 700;
        font-size: 16px;
        line-height: 110%;
        letter-spacing: 0.005em;
        color: #FFB800;
    }
    .content-title-sub{
        position: absolute;
        width: 82px;
        height: 17px;
        left: 25px;
        top: 50px;
        font-family: 'Open Sans';
        font-style: normal;
        font-weight: 400;
        font-size: 12px;
        line-height: 140%;
        color: #CCCCCC;;
    }
    .button-back{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 10px 20px;
        gap: 10px;
        position: absolute;
        width: 150px;
        height: 42px;
        right: 200px;
        top: 30px;
        background: #F6F6F6;
        border-radius: 3px;
        border: none;
        text-align: center;
        align-items: center;
        color: #777;
    }
    .button-save{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 10px 20px;
        gap: 10px;
        position: absolute;
        width: 150px;
        height: 42px;
        right: 30px;
        top: 30px;
        background: #FFB800;
        border-radius: 3px;
        border: none;
        text-align: center;
        align-items: center;
        color: white;
    }

    .row-head{
        margin-bottom: 5em;
    }
    /* .row-sub-head{
        margin: 3em;
    } */
</style>
