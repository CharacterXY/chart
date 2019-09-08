<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">     
                        <form @submit.prevent="createProduct">
                            <div class="form-group">
                                <label for="name">Name</label>
                                <input v-model="product.name" type="text" id="name" class="form-control">
                            </div>
                            <div class="form-group">
                                <label for="year">Year</label>
                                <input  v-model="product.year" type="number" id="year" class="form-control">
                            </div>
                            <div class="form-group">
                                <label for="price">Price</label>
                                <input v-model="product.price" type="number" id="price" class="form-control">
                            </div>
                                <button class="btn btn-primary">Submit</button>
                        </form> 
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                product: {}
            }
        },
        mounted() {
            console.log('Uspjesno loadano.')
        },
        methods : {
          
          createProduct(){
              let url = 'https://127.0.0.1:8000/products';

              axios.post(url, this.product).then((response) => {
                     window.location.reload();
              });
              console.log(this.product);
          }
        }

    }

</script>
