# Pengajian

Flow ini menjelaskan alur pengajuan dan persetujuan gaji oleh staf HRD

## Global Flowchart

```mermaid
flowchart TD
    Start([Mulai])
    --> Input([Input pembuatan payrol])
    --> Generate([Generate payroll oleh aplikasi])
    --> Riview([Review staf HRD])
    --> Updated{Diperlukan update payrol}
        Updated --> |yes|Update([Update payrol yang di buat system])
                --> Updated
        Updated --> |no|Approval([Persetujuan manager HRD])
                --> Payment([Pembayaran oleh finance])
    --> Broadcast([Pengiriman slip gaji karyawan])
    --> End([Selesai])
```

1. Staf HRD melakukan pembuatan payrol bulan berjalan

   a. Upload potongan karyawan

2. Staf HRD akan mereview hasil generate dari payroll dari aplikasi
3. Staf HRD melakukan update apabila di perlukan
4. Staf HRD mengajukan payrol untuk selanjutnya di setujui oleh Manager HRD
5. Manager HRD melakukan review dan persetujuan

## User Journey

### Input pembuatan payrol

```mermaid
journey
    section Input
        Memilih menu Payroll Karyawan : 5 : User
        Tampil list Payroll yang sudah di buat : 4 : Aplikasi
        Menekan tombol Baru : 5 : User
        Tampil form Payroll Karyawan : 4 : Aplikasi
        Memilih bulan payrol : 5 : User
        Memilih file upload potongan : 5 : User
        Simpan form Payroll Karyawan : 5 : User
        Generate payroll di background : 4 : Aplikasi
        Tampil list Payroll : 4 : Aplikasi
```

### Review staf HRD

```mermaid
journey
    section Review
        Memilih menu Payroll Karyawan : 5 : User
        Tampil list Payroll yang sudah di buat : 4 : Aplikasi
        Memilih payroll bulan berjalan dengan status New : 5 : User
        Tampil detail payroll karyawan : 4 : Aplikasi
        Mereview payrol yang sudah di buat : 5 : User
        Melakukan update payroll apabila di perlukan : 5 : User
        Menekan tombol Send : 5 : User
        Tampil list Payroll : 4 : Aplikasi
        Kirim notifikasi ke atasan : 4 : Aplikasi
```

### Persetujuan manager HRD

```mermaid
journey
    section Approval via Email / Notifikasi
        Menerima email pengajuan payroll : 5 : User
        Menekan tombol approve : 5 : User
        Redirect ke halaman detail payroll : 4 : Email Client
        Tampilkan halaman pesetujuan payroll : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

```mermaid
journey
    section Approval via Aplikasi
        Memilih menu Persetujuan Payroll : 5 : User
        Tampil list payroll yang harus di setujui : 4 : Aplikasi
        Menekan tombol lihat : 5 : User
        Tampilkan halaman pesetujuan payroll : 4 : Aplikasi
        Menekan tombol approve / reject : 5 : User
        Redirect ke halaman list approval : 4 : Aplikasi
```

### Pembayaran oleh Finance

```mermaid
journey
    section Pembayaran Gaji
        Memilih menu Payroll Karyawan : 5 : User
        Tampil list Payroll yang sudah di buat : 4 : Aplikasi
        Memilih payroll bulan berjalan dengan status Approved : 5 : User
        Tampil detail payroll karyawan : 4 : Aplikasi
        Mendownload data payrol : 5 : User
        Mengirimkan file excel ke Finance : 5 : User
        Finance melakukan pembayaran : 5 : Finance
        Finance menginformasikan sudah dilakukan pembayaran : 5 : Finance
```

### Pengiriman slip gaji karyawan

```mermaid
journey
    section Pengiriman Slip Gaji
        Staff HRD menerima informasi bahwa gaji telah di bayar : 5 : User
        User memilih menu Payroll Karyawan : 5 : User
        Menampilkan list Payroll yang sudah di buat : 4 : Aplikasi
        Memilih payroll bulan berjalan dengan status Approved : 5 : User
        Tampil detail payroll karyawan : 4 : Aplikasi
        Menekan tombol Kirim Slip Gaji : 5 : User
        Aplikasi secara background melakukan pengiriman Slip Gaji : 5 : Aplikasi
```
