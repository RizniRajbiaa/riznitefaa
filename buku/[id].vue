<script setup>
import {onMounted} from 'vue';

const supabase = useSupabaseClient()
const route = useRoute ()
const  buku = ref ({})
const getBookById = async () => {
  const {data, error} = await supabase.from('buku').select('*, kategori(*)')
  .eq('id', route.parans.id)
  if(data) buku.value = data [0]

  onMounted(() => {
    getBookById()
  })
}
</script>


