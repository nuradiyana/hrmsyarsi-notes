# Presensi

Presensi secara umum terdiri dari

1. Management shifting karyawan
2. Management ijin karyawan, cuti maupun ijin lainnya

## Pembuatan Shifting

Catatan :

1. Head / manager karyawan membuat jadwal shif secara berkala
2. Apakah di perlukan approval atasan ?

## Tukar Shifting

### Global Flowchart

```mermaid
flowchart TD
    Start([Mulai])
    --> Input([Input tukar shifting karyawan])
    --> Approval([Persetujuan atasan karyawan])
    --> End([Selesai])
```

1. Karyawan melakukan penginputan pada sistem, memasukan informasi pertukaran shifting
2. Atasan karyawan melakukan approval untuk pertukaran shifting yang diajukan
3. Sistem akan mengirimkan informasi pertukaran kepada user yang mengajukan dan user yang jadwalnya di tukar

### User Journey

#### Pengajuan tukar shifting

```mermaid
journey
    section Input
        Memilih menu Jadwal Shift : 5 : User
        Tampil list jadwal shift yang sudah di buat : 4 : Aplikasi
        Memilih jadwal shift yang akan di tukar : 5 : User
        Tampil form pertukaran jadwal shift : 4 : Aplikasi
        Mengisi form pertukaran jadwal shift : 5 : User
        Simpan form pertukaran jadwal shift : 5 : User
        Tampil list jadwal shift : 4 : Aplikasi
        Kirim notifikasi ke atasan : 4 : Aplikasi
```

#### Persetujuan tukar shifting

```mermaid
journey
    section Approval via Email / Notifikasi
        Menerima email pengajuan pertukaran shift : 5 : User
        Menekan tombol approve : 5 : User
        Redirect ke halaman detail pertukaran shift : 4 : Email Client
        Tampilkan halaman pesetujuan pertukaran shift : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

```mermaid
journey
    section Approval via Aplikasi
        Memilih menu Tukar Shift : 5 : User
        Tampil list pengajuan pertukaran shift yang harus di setujui : 4 : Aplikasi
        Menekan tombol lihat : 5 : User
        Tampilkan halaman pesetujuan pertukaran shift : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

## Ijin karyawan

### Global Flowchart

```mermaid
flowchart TD
    Start([Mulai])
    --> Input([Input ijin karyawan])
    --> Approval([Persetujuan atasan karyawan])
    --> Riview([Review staf HRD])
    --> End([Selesai])
```

1. Karyawan melakukan penginputan pada sistem, memasukan informasi waktu ijin
2. Atasan karyawan melakukan approval untuk ijin yang diajukan
3. Staf HR melakukan review ijin yang sudah di setujui atasan
4. Apabila ijin adalah cuti maka akan mengurangi hak cuti karyawan

### User Journey

#### Pengajuan ijin karyawan

```mermaid
journey
    section Input
        Memilih menu Ketidakhadiran : 5 : User
        Tampil list ketidakhadiran : 4 : Aplikasi
        Menekan tombol Tambah : 5 : User
        Tampil form pengajuan ketidakhadiran : 4 : Aplikasi
        Mengisi form ketidakhadiran : 5 : User
        Simpan form ketidakhadiran : 5 : User
        Tampil list ketidakhadiran : 4 : Aplikasi
        Kirim notifikasi ke atasan : 4 : Aplikasi
```

#### Persetujuan ijin karyawan

```mermaid
journey
    section Approval via Email / Notifikasi
        Menerima email pengajuan ketidakhadiran : 5 : User
        Menekan tombol approve : 5 : User
        Redirect ke halaman detail ketidakhadiran : 4 : Email Client
        Tampilkan halaman pesetujuan ketidakhadiran : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

```mermaid
journey
    section Approval via Aplikasi
        Memilih menu Persetujuan Ketidakhadiran : 5 : User
        Tampil list ketidakhadiran yang harus di setujui : 4 : Aplikasi
        Menekan tombol lihat : 5 : User
        Tampilkan halaman pesetujuan ketidakhadiran : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```
