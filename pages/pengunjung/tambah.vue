<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">ISI DATA PENGUNJUNG</h2>
        <form>
          <div class="mb-3">
            <input type="text" class="from-control from-control-lg rounded-5" placeholder="NAMA..." />
          </div>
          <div class="mb-3">
            <div class="row">
              <div class="col-md-4">
                <select class="from-control from-control from-control-lg from-select rounded-5 mb-2">
                  <option value="">KEANGGOTAAN</option>
                  <option value="Siswa">Siswa</option>
                  <option value="Guru">Guru</option>
                  <option value="Staf">Staf</option>
                  <option value="Umum">Umum</option>
                </select>
              </div>
            </div>
          </div>
          <div class="mb-3">
            <div class="row">
              <div class="col-md-4">
                <select class="from-control from-control-lg from-select rounded-5 mb-2">
                  <option value="">TINGKAT</option>
                  <option value="X">X</option>
                  <option value="XI">XI</option>
                  <option value="XII">XII</option>
                </select>
              </div>
            </div>
          </div>
          <div class="colo-md-4">
            <select class="from-control from-control-lg from-select rounded-5 mb-2">
              <option value="">JURUSAN</option>
              <option value="PPLG">PPLG</option>
              <option value="TKJT">TKJT</option>
              <option value="TSM">TSM</option>
              <option value="DKV">DKV</option>
              <option value="TOI">TOI</option>
            </select>
          </div>
          <div class="colo-md-4">
            <select class="from-control from-control-lg from-select rounded-5 mb-2">
              <option value="">KELAS</option>
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3">3</option>
              <option value="4">4</option>
            </select>
          </div>
          <div class="md-3">
            <select class="from-control from-control-lg from-select rounded-5 mb-2">
              <option value="">KEPERLUAN</option>
              <option value="1">Baca Buku</option>
              <option value="2">Pinjam Buku</option>
              <option value="3">Kembalikan Buku</option>
            </select>
          </div>
          <button type="submit" class="btn btn-dark btn-lg rounded-5">Lanjutkan</button>
        </form>
      </div>
    </div>
  </div>
</template>
