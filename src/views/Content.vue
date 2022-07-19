<template>
    <div>
        <div class="content">
            <div v-if="modal">
                <Modal 
                    v-on:close-modal="closeModal" 
                    v-bind:tipe="{ tipe }"
                    ></Modal>
            </div>
            <div class="row">
                <div class="col-2">
                    <!-- <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16">
                        <path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"/>
                    </svg> -->
                    <input type="text" name="" id="" class="input-search" placeholder="search">
                </div>
                <div class="col-2">
                    <select name="" id="" class="input-combobox">
                        <option value="">Select</option>
                        <option value="">Branch</option>
                        <option value="">Users</option>
                        <option value="">Customer</option>
                    </select>
                </div>
                <div class="col-8">
                    <div class="d-flex flex-row-reverse">
                        <div class="p-4">
                            <button class="success" @click="modalToggle('Sync Customer', 1)">Sync</button>
                        </div>
                    </div>
                </div>
            </div>

            <!--  -->

            <div class="row">
                <div class="col-12">
                    <div class="container">
                        <div class="container">
                            <table class="table table-striped">
                                <thead>
                                    <tr>
                                        <th class="text-center">#</th>
                                        <th>Code</th>
                                        <th>Date</th>
                                        <th>Database From</th>
                                        <th>Database To</th>
                                        <th>Status</th>
                                        <th>Action</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="text-center">1</td>
                                        <td>TX001</td>
                                        <td>12/09/2022</td>
                                        <td>ASD</td>
                                        <td>AGZ</td>
                                        <td>
                                            <button class="warning">Sync</button>
                                        </td>
                                        <td>
                                            <img src="../../src/assets/logo12.png" @click="modalToggle('Sync', 2)" alt="" style="width: 44.78px; margin-right: 5px; ">
                                            <img src="../../src/assets/logo13.png" alt="" @click="toDatabase()" style="width: 44.78px; ">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">2</td>
                                        <td>TX002</td>
                                        <td>12/09/2022</td>
                                        <td>DGA</td>
                                        <td>ASE</td>
                                        <td>
                                            <button class="warning">Sync</button>
                                        </td>
                                        <td>
                                            <img src="../../src/assets/logo12.png" alt="" style="width: 44.78px; margin-right: 5px; ">
                                            <img src="../../src/assets/logo13.png" alt="" style="width: 44.78px; ">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">3</td>
                                        <td>TX003</td>
                                        <td>12/09/2022</td>
                                        <td>ASQ</td>
                                        <td>HGD</td>
                                        <td>
                                            <button class="info">In Progress</button>
                                        </td>
                                        <td>
                                            <!-- <img src="../../src/assets/logo12.png" alt="" style="width: 44.78px; margin-right: 5px; "> -->
                                            <img src="../../src/assets/logo13.png" alt="" style="width: 44.78px; position: static; margin-left: 50px;">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">4</td>
                                        <td>TX004</td>
                                        <td>12/09/2022</td>
                                        <td>HGI</td>
                                        <td>HWA</td>
                                        <td>
                                            <button class="success">Done</button>
                                        </td>
                                        <td>
                                            <img src="../../src/assets/logo12.png" alt="" style="width: 44.78px; margin-right: 5px; ">
                                            <img src="../../src/assets/logo13.png" alt="" style="width: 44.78px; ">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="text-center">5</td>
                                        <td>TX005</td>
                                        <td>12/09/2022</td>
                                        <td>HJO</td>
                                        <td>TYU</td>
                                        <td>
                                            <button class="danger">Failed</button>
                                        </td>
                                        <td>
                                            <img src="../../src/assets/logo12.png" alt="" style="width: 44.78px; margin-right: 5px; ">
                                            <img src="../../src/assets/logo13.png" alt="" style="width: 44.78px; ">
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
                                            <li>
                                                <div class="page-count">
                                                    <select name="" id="">
                                                        <option value="">10</option>
                                                    </select>
                                                    <!-- 10
                                                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-down" viewBox="0 0 16 16">
                                                        <path fill-rule="evenodd" d="M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z"/>
                                                    </svg> -->
                                                </div>
                                            </li>
                                            <li>
                                                <span class="desc">Showing 1-10 of 200</span>
                                            </li>
                                        </ul>
                                    </nav>

                                    <!-- <a href="#">
                                        <div class="previous">
                                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-left" viewBox="0 0 16 16">
                                                            <path fill-rule="evenodd" d="M11.354 1.646a.5.5 0 0 1 0 .708L5.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"/>
                                                        </svg>
                                        </div>
                                    </a>

                                    <a href="#">
                                        <div class="page">1</div>
                                    </a>
                                    <a href="#">
                                        <div class="page active">2</div>
                                    </a>
                                    <a href="#">
                                        <div class="page">3</div>
                                    </a>
                                    <a href="#">
                                        <div class="page">4</div>
                                    </a>
                                    <a href="#">
                                        <div class="page">5</div>
                                    </a>

                                    <a href="#">
                                        <div class="next">
                                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-right" viewBox="0 0 16 16">
                                                        <path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z"/>
                                                    </svg>
                                        </div>
                                    </a> -->
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Modal from '../components/Modal.vue'

export default {
    components: {
        Modal
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
    .content{
        position: absolute;
        left: 20%;
        right: 1.84%;
        top: 3.85%;
        bottom: 8.3%;

        background: #FFFFFF;
    }
    /*  */
    .input-search{
        box-sizing: border-box;
        position: absolute;
        height: 40px;
        left: 2%;
        right: 0%;
        top: 3%;
        bottom: 0%;
        background: #F6F6F6;
        border: 1px solid #F2F2F2;
    }

    .input-combobox{
        position: absolute;
        width: 200px;
        height: 40px;
        font-size: 14px;
        font-family: 'Open Sans';
        color: #999;
        background-color: white;
        top: 3%;
        padding: 8px 16px;
        border: 1px solid ;
        border-radius: 3px;
        /* border-color: transparent transparent rgba(0, 0, 0, 0.1) transparent; */
        cursor: pointer;
        user-select: none;
    }

    /*  */
    /*  */

    thead{
        background-color:#E6A500;
        color: white;
        font-family: 'Open Sans';
        font-size: 12px;
        font-weight: 400;
    }
    tbody{
        color: #686868;
        font-family: 'Open Sans';
        font-size: 12px;
        font-weight: 400;
    }

    /*  */
    /*  */

    .page-item{
        /* border: 1px solid black; */
        padding-left: 6px;
        padding-right: 6px;
        padding-top: 6px;
        padding-bottom: 6px;
        font-size: 14px;
        /* background: #F2F2F2; */
        background: #F2F2F2;
        border-radius: 3px;
        width: 30px;
        height: 30px;
    }
    .pagination .active{
        background-color: #FFE299;
    }
    .pagination-link{
        color: #686868;
        text-decoration: none;
    }

    .page-count{
        position: absolute;
        left: 25%;
        right: 0%;
        top: 71.5%;
        bottom: 0%;
        width: 60px;
        height: 30px;
        background: #F2F2F2;
        border-radius: 3px;
        text-align: center;
        color: #7E7D7D;
    }
    .page-count select{
        border: none;
        color: #7E7D7D;
    }
    .desc{
        position: absolute;
        left: 31%;
        right: 0%;
        top: 72.5%;
        bottom: 20%;

        font-family: 'Poppins';
        font-style: normal;
        font-weight: 400;
        font-size: 12px;
        line-height: 18px;
        color: #7E7D7D;
    }
    /* .previous{
        width: 30px;
        height: 30px;
        position: absolute;
        left: 2%;
        right: 86.9%;
        top: 70%;
        bottom: 0%;
        background: #F2F2F2;
        border-radius: 3px;
        color: #686868;
    }
    .next{
        width: 30px;
        height: 30px;
        position: absolute;
        left: 15%;
        right: 86.9%;
        top: 70%;
        bottom: 0%;
        background: #F2F2F2;
        border-radius: 3px;
        color: #686868;
    }
    .page{
        width: 30px;
        height: 30px;
        position: absolute;
        left: 10%;
        right: 86.9%;
        top: 70%;
        bottom: 0%;
        background: #F2F2F2;
        border-radius: 3px;
        color: #686868;
    } */

    /*  */
    /*  */

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