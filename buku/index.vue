<script setup>
const supabase = useSupabaseClient()
const books = ref([])

const getBooks = async () =>{
  const {data, error} = await supabase.from('buku').select('*, kategori(*)')
  if(data) books.value = data
}

onMounted(()) => {
  getBooks()
}
</script>

<div v-for="(book,i) in books" :key="i" class="col-lg-2">
  <div class="card-mb-3">
  <div class="card-body">
  <img :src="book.cover" class="cover" alt="cover">
  </div>
</div>
</div>

<form @submit.prevent="getBooks">
  <input v-model="keyword" type="search">
</form>

<script setup>
const keyword = ref('')
const getBooks = async () => {
const { data, error} = await supabase.from('buku').select('*, kategori(*)')
.ilike('judul', '%${keyword.value}%')
if(data) books.value = data
}
</script>

<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">BUKU</h2>
        <div class="my-3">
          <input type="search" class="form-control- rounded-5" placeholder="mau baca apa hari ini?">
        </div>
        <div class="my-3 text-muted">menampilkan 3 dari 3</div>
        <div class="row">
          <div class="col-lg-2">
            <div class="col-lg-3">
              <div class="card-body">
                <img src="~/assets/img/cover1.jpeg" class="cover" alt="cover1">
              </div>
            </div>          
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img src="~/assets/img/cover2.jpeg" class="cover" alt="cover2">
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img src="~/assets/img/cover3.png" class="cover" alt="cover3">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.card-body {
  width: 100%;
  height: 20em;
  padding: 0;
}
.cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 0 30;
}
</style>