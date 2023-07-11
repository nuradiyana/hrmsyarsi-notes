# Lembur Karyawan

Flow ini menjelaskan alur pengajuan dan persetujuan lembur oleh karyawan

## Global Flowchart

```mermaid
flowchart TD
    Start([Mulai])
    --> Input([Input lembur karyawan])
    --> Approval([Persetujuan atasan karyawan])
    --> Riview([Review staf HRD])
    --> ApprovalHRD([Persetujuan manager HRD])
    --> End([Selesai])
```

1. Karyawan melakukan penginputan pada sistem, memasukan informasi waktu lembur
2. Atasan karyawan melakukan approval untuk lembur yang di ajukan
3. (Opsional) Staf HR melakukan review lembur yang sudah di setujui atasan, sistem akan menghitung nominal lembur yang harus di bayarkan
4. (Opsional) Manager HR melakukan approval review yang dilakukan staf HR
5. Semua nonimal rupiah yang harus di bayarkan akan masuk ke dalam proses payroll
6. Nominal pembayaran muncul saat di point 4 atau 2 apabila point 3 dan 4 tidak ada

## User Journey

### Input lebur karyawan

```mermaid
journey
    section Input
        Memilih menu Lembur : 5 : User
        Tampil list lembur : 4 : Aplikasi
        Menekan tombol Tambah : 5 : User
        Tampil form lembur : 4 : Aplikasi
        Mengisi form lembur : 5 : User
        Simpan form user : 5 : User
        Tampil lista lembur : 4 : Aplikasi
        Kirim notifikasi ke atasan : 4 : Aplikasi
```

### Persetujuan atasan karyawan

```mermaid
journey
    section Approval via Email / Notifikasi
        Menerima email pengajuan lembur : 5 : User
        Menekan tombol approve : 5 : User
        Redirect ke halaman detail lembur : 4 : Email Client
        Tampilkan halaman pesetujuan lembur : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

```mermaid
journey
    section Approval via Aplikasi
        Memilih menu Persetujuan Lembur : 5 : User
        Tampil list lembur yang harus di setujui : 4 : Aplikasi
        Menekan tombol lihat : 5 : User
        Tampilkan halaman pesetujuan lembur : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

### Review Staf HRD

```mermaid
journey
    section Review Staf HRD
        Memilih menu Review Lembur : 5 : User
        Tampil list lembur yang harus di review : 4 : Aplikasi
        Menekan tombol review : 5 : User
        Tampilkan halaman review lembur : 4 : Aplikasi
        Tamplikan nilai yang harus di bayarkan : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list review lembur : 4 : Aplikasi
        Kirim notifikasi ke atasan : 4 : Aplikasi
```

### Persetujuan manager HRD

```mermaid
journey
    section Approval via Email / Notifikasi
        Menerima email pengajuan lembur : 5 : User
        Menekan tombol approve : 5 : User
        Redirect ke halaman detail lembur : 4 : Email Client
        Tampilkan halaman pesetujuan lembur : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

```mermaid
journey
    section Approval via Aplikasi
        Memilih menu Persetujuan Lembur : 5 : User
        Tampil list lembur yang harus di setujui : 4 : Aplikasi
        Menekan tombol lihat : 5 : User
        Tampilkan halaman pesetujuan lembur : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi