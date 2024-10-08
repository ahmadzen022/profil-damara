<script setup>
const client = useSupabaseClient()
const products = ref([])

async function getProducts() {
    const { data, error } = await client
        .from('product')
        .select()
    if(data) {
        products.value = data
    }
}

onMounted(() => {
    getProducts()
})
</script>

<template>
    <div id="carousel" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-inner">
            <div class="carousel-item active">
                <img src="~/assets/gambar1.jpg" class="d-block w-100" alt="gambar1">
            </div>
        </div>
    </div>

    <!-- about -->
    <section id="about" class="pt-5">
        <div class="card mb-3 shadow" style="max-width: 100%;">
            <div class="row g-0">
                <div class="col-md-4">
                    <img src="~/assets/about-image.jpeg" class="img-fluid rounded-start p-4 " alt="...">
                </div>
                <div class="col-md-8">
                    <div class="card-body">
                        <h2 class="about card-title text-center">About us</h2>
                        <p class="card-text">Selamat datang di DAMARA WANGI PARFUM, di mana keanggunan dan keharuman bertemu dalam setiap tetes parfum yang kami ciptakan. 
                                            kami bangga menjadi pelopor dalam industri parfum dengan misi untuk menghadirkan pengalaman aroma yang tak terlupakan.
                        </p>
                        <p class="card-text"><small class="text-muted">lebih lanjut</small></p>
                        <!-- contact -->
                        <a href="https://www.instagram.com/damarawangiparfum" target="_blank" class="bg-primary text-light text-center shadow"
                            style="width: 30%;border-radius: 50px; display: block; text-decoration:none">Open</a>
                    </div>
                </div><section id="product">
        <div class="container">
            <div class="row text-center">
                <div class="col pt-5">
                    <h2>Product</h2>
                </div>
            </div>
            <div class="row d-flex justify-content-around pt-5">
                <div v-for="product in products" :key="product.id" class="card mt-5" style="width: 18rem;">
                    <img :src="product.cover" class="card-img-top" :alt="product.nama">
                    <div class="card-body">
                        <h5 class="card-title text-center">{{ product.nama }}</h5>
                        <p class="card-text">{{ product.harga }}</p>
                        <NuxtLink :to="`/${product.id}`" class="btn btn-primary">Open</NuxtLink>
                    </div>
                </div>
                
            </div>
        </div>
    </section>
            </div>
        </div>
    </section>
    <!-- about n  -->

    <!-- product -->
    


    <!-- n -->
    <!-- footer -->
     <Footer />
    <!-- <div class="card mt-5 shadow">
        <div class="card-body">
            <div class="image d-flex justify-content-center">
                <img src="~/assets/logo.png" style="width:150px;" alt="logo">
            </div>
            
            <div class="pt-3 d-flex justify-content-center">
                <p>Jl.ciwasmandi</p>
            </div>
            <div class="d-flex justify-content-center">
                <p> &copy; Rumah Parfum Damara</p>
            </div>
        </div>
    </div> -->
    <!-- contact wa -->
    <NuxtLink to="https://wa.me/6289505898529" class="wa-button fixed-bottom" target="_blank">
            <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" class="wa-icon">
            Hubungi Admin
    </NuxtLink>
    <!-- footer -->
</template>


<style>

.wa-button {
    width: 200px;
    background-color: #25d366;
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 50px;
    font-size: 16px;
    font-weight: bold;
    transition: background-color 0.3s ease;
}

.wa-button:hover {
    background-color: #22b35a;
}

.wa-icon {
    width: 24px;
    height: 24px;
    margin-right: 10px;
}
</style>