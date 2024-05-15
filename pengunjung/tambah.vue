<script setup>
const supabase = useSupabaseClient()

const members= ref([])
const objectives = ref([])
</script>

<script setup>
const form = ref({

const kirimData = async () => {
    const {error} = await supabase.from('pengunjung').insert([form.value])
    if(!error) navigateTo('/pengunjung')
})
const getKeanggotaan = async () => {
  const {data, error} = await supabase.from('keanggotaan').select('*')
  if(data) objectives.value = data
}
constgetKeperluan = async () => {
  const{data, error} = await supabase.from('keperluan').select('*')
  if(data) objectives.value = data
}
</script>

onMounted(() => {
  getKeanggotaan()
  getKeperluan()
})
<form @submit.prevent="kirimData">
  </form>
  <input v-model="form.nama" type="text" placeholder="NAMA...">
  <select v-model="form.tingkat">
  </select>

  <select v-model="form.keanggotaan">
    <option value="">KEANGGOTAAN</option>
    <option v-for="(member,i) in members" :key="i" :value="member.id">{{member.nama}}</option>
    </select>
    
<select v-model="form.keperluan">
  <option value="">KEPERLUAN</option>
  <option v-for="(item,i) in objectives" :key="i" :value="item.id">{{item.nama}}</option>
  </select>







<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">ISI DATA PENGUNJUNG</h2>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg rounded-5" placeholder="NAMA..">
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KELAS</option>
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3">3</option>
            </select>
            </div>
            <div class="col-md-4">
              <select class="form-control form-control-lg form-select rounded-5 mb-2">
                <option value="">jurusan</option>
                <option value="PPLG">PPLG</option>
                <option value="TJKT">TJKT</option>
                <option value="TSM">TSM</option>
                <option value="TOI">TOI</option>
                <option value="DKV">DKV</option>
              </select>
            </div>
          </div>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KEPERLUAN</option>
              <option value="baca">baca buku</option>
              <option value="pinjam">pinjam buku</option>
              <option value="kembalikan">kembalikan buku</option>
            </select>
          </div>
          <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">kirim</button>
        </div>
    </template>
