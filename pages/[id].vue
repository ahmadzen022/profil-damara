    <template>
    <div class="content">
        <div class="container">
            <h2 class="text-center my-4 ">DETAIL PRODUK</h2>
            <div class="row d-flex justify-content-center flex-md-wrap" style="padding-top: 50px;">
                <div class="col-3 ">
                    <img :src="detail?.cover"  class="cover row img-fluid" alt="cover"   style="width: 250px; padding-top: 100px;">
                    <div class="row">
                    </div>
                </div>
                <div class="col-4">
                    <div class="row">
                        <!-- <h1 class="text start text-center my-4">DETAIL PRODUK</h1> -->
                    </div>
                    <div class="row">
                    <div class="badge bg-secondary class p-2">{{ detail?.nama }}</div>
                        <ul class="list-group list-group-flush">
                            <li class="list-group-item">Stok : {{ detail?.stok }}</li>
                            <li class="list-group-item">Size : {{ detail?.size }}</li>
                            <li class="fs-5 list-group-item text-success ">Harga : {{ detail?.harga }}</li>
                            <li class="list-group-item ">Deskripsi : {{ detail?.deskripsi }}</li>
                        </ul>                       
                    </div>
                    <nuxt-link href="https://wa.me/6283814789833" class="btn btn-outline-success btn-lg mt-4  d-flex justify-content-around">Order WhatsApp</nuxt-link>
                    <nuxt-link to="/" class="btn btn-outline-secondary btn-lg mt-4  d-flex justify-content-around">Kembali</nuxt-link>
                </div>
            </div>
        </div>
        <Footer />
        </div>
    </template>
    <script setup>


    const supabase = useSupabaseClient()
    const route = useRoute()
    const detail = ref()

    const ambildata = async () => {
    const { data, error } = await supabase
    .from('product')
    .select()
    .eq('id', route.params.id)
    .maybeSingle()
    if(data) detail.value = data

    }

    onMounted(() => {
    ambildata()
    })

    </script>
    <style scoped>
    .content {
    background-image:linear-gradient(#ffffff,#ffffff);
    background-size: cover;
    width: 100%;
    height: 100vh;
    font-family: '';
    color: rgb(135, 135, 135);
    margin-top:25vh ;
    }
    .container{
        margin-top: 10vh;
    }
    </style> 