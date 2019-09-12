<script>

import {Line} from 'vue-chartjs'; // wrapper za chart.js

 export default {
    extends: Line,
    data(){
        return {
            url: 'http://chart.local/products',
            years: [],
            labels: [],
            name: [],
            prices: [],
            data: ''
        }
    },
    methods: {
        
        getProducts(){
            axios.get(this.url).then((response) => {
                console.log(response.data);
            });
        }
    },

    mounted(){
        this.getProducts();
    }
}

</script>