# Onboarding Karyawan

Flow ini menjelaskan flow karyawan baru saat bergabung dengan RS Yarsi,
Ada dua flow yaitu self service artinya user / karyawan mengisi data secara
mandiri atau di inputkan oleh staf HRD.

## Global Flowchart

```mermaid
flowchart TD
    Start([Mulai])
    -->InputHRD{Input HRD}
    InputHRD
        -->|yes|Onboarding1[1.0 - Calon karyawan menginput sendiri]
        -->Onboarding3[1.1 - Staf HRD melakukan input gaji dan divisi]
        -->End([Selesai])
    InputHRD
        -->|no|Onboarding2[2.0 - Calon karyawan mengisi form]
        -->Onboarding4[2.1 - Staf HRD input data ke system]
        -->End([Selesai])
```
<p align = "center">Flowchart global onboarding karyawan</p><br />

## Karyawan input sendiri

```mermaid
flowchart LR
    subgraph one [1.0]
    direction TB
        StartOne[Mulai]
            -->Personal[1.0.1 - Input data personal]
            -->Address[1.0.2 - Input data alamat]
            -->Family[1.0.3 - Input data keluarga]
            -->Education[1.0.4 - Input data pendidikan]
            -->Experience[1.0.5 - Input data pengalaman]
            -->Permission[1.0.6 - Input ijin yang dimiliki]
            -->Certificate[1.0.7 - Input sertifikasi yang dimiliki]
            -->Organization[1.0.8 - Input data organisasi]
            -->Skill[1.0.9 - Input data keahlian]
            -->Attachment[1.0.10 - Upload berkas]
    end

    subgraph two [1.1]
    direction TB
        Division[1.1.1 - Input data jabatan dan divisi]
            -->Salary[1.1.2 - Input data gaji / benefit]
            -->Contract[1.1.3 - Input masa kontrak]
            -->EndTwo[Selesai]
    end

    one-->two
```
<p align = "center">Flowchart karyawan input data sendiri</p><br />


## Diinput oleh staf

```mermaid
flowchart LR
    subgraph one [2.0]
    direction TB
        StartOne[Mulai]
            -->form[2.0.1 - Mengisi form karyawan baru]
    end

    subgraph two [2.1]
    direction TB
        Personal[2.1.1 - Input data personal]
            -->Address[2.1.2 - Input data alamat]
            -->Family[2.1.3 - Input data keluarga]
            -->Education[2.1.4 - Input data pendidikan]
            -->Experience[2.1.5 - Input data pengalaman]
            -->Permission[2.1.6 - Input ijin yang dimiliki]
            -->Certificate[2.1.7 - Input sertifikasi yang dimiliki]
            -->Organization[2.1.8 - Input data organisasi]
            -->Skill[2.1.9 - Input data keahlian]
            -->Attachment[2.1.10 - Upload berkas]
            -->Division[2.1.1 - Input data jabatan dan divisi]
            -->Salary[2.1.2 - Input data gaji / benefit]
            -->Contract[2.1.3 - Input masa kontrak]
        -->EndTwo[Selesai]
    end

    one-->two
```
<p align = "center">Flowchart staff HRD input data karyawan</p><br />
