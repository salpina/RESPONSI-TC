# RESPONSI-TC
- kerjakan dari website-profil terlebih Dahulu
## Buat dua direktori: website-utama dan website-profil. 
```
mkdir website-profil
mkdir website-utama
```
## Masuk kedalam masing" direktori
```
cd website-profil
cd website-utama
```
## Buat file index.html (sesuai deskripsi halaman utama).
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Halaman Utama</title>
</head>
<body>
    <h1>Data Diri</h1>
    <p>Nama Lengkap: Salvina Salsabilla</p>
    <p>NIM: 215610081</p>
    <p>Program Studi: Sistem Informasi</p>
    <p>Hobi: Membaca, Menulis, dan Bersepeda</p>
    <a href="https://4f0aa670-e00e-4e00-999b-50f18a93408c-10-244-8-107-8081.papa.r.killercoda.com/">Profil</a>
</body>
</html>
```
## Buat file index.html (sesuai dekripsi halaman profil).
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil</title>
</head>
<body>
    <h1>Profil</h1>
    <img src="foto.jpg" alt="Foto Profil" style="width:200px;">
</body>
</html>
```
## Membuat Dockerfile di website-profil dan website-utama
```
FROM nginx:latest
COPY . /usr/share/nginx/html
EXPOSE 80
```
## Di dalam website-profil, letakkan file gambar profil Anda (foto.jpg).
```
wget -O ~/website-profil/foto.jpg
```
## Membuat network my-namamahasiswa-network
```
docker network create my-salvina-network
```
## Build Image website-profil dan website-utama
```
docker build -t website-profil .
docker build -t website-utama .
```
## Jalankan Container Website-profil
```
docker run -d --name website-profil --network my-salvina-network -p 8081:80 website-profil
```
## Jalankan Container Website-utama
```
docker run -d --name cont_utama --network my-salvina-network -p 8080:80 website-utama
```
# Hasil Saat Dijalankan
- Website-Utama
  ![image](https://github.com/salpina/RESPONSI-TC/assets/168054744/343b13e2-20fc-4603-908e-4586da0d9dd3)
- Website-Profil
  ![image](https://github.com/salpina/RESPONSI-TC/assets/168054744/2ce61f16-1312-4fac-aeef-480a272595e7)
