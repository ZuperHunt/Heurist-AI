Penulis: [Luthfi0x](https://twitter.com/luthfi0x)

# Pengenalan
Bab ini berisi pengenalan mengenai Heurist AI

## Heurist AI
![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/23fd09da-b1bd-424f-94d9-d48ebff52c4f)

> [!NOTE]
> Heurist AI adalah sebuah project L2 yang berfokus pada bisnis hostring dan inference AI model menggunakan zkStacks.

# Tutorial AI Mining
Bab ini berisi tutorial cara mining Waifu dan Llama points

## Requirement
Syarat menjadi miner
- Spek Komputer
  
| Name | Minimum | Recommended | 
| ------------- | ------------- | ------------- |
| Operating System  | Windows, Ubuntu | Windows, Ubuntu  |
| CPU  | 4 Cores  | 8 Cores | 
| RAM  | 32 GB  | 64 GB | 
| SSD  | 80 GB  | 120** GB | 
| SSD  | NVIDIA GPU dengan VRAM 12 GB  | NVIDIA GPU dengan VRAM 24 GB++** | 

> [!TIP]
> Kami menggunakan [Vast.ai](https://cloud.vast.ai/?ref_id=124940) dengan speksifikasi `NVIDIA RTX 4090/ 24 Cores/ 32 GB RAM/ 120 GB SSD`. Jika kamu membutuhkan provider GPU, kami sangat merekomendasikan [Vast.ai](https://cloud.vast.ai/?ref_id=124940) karena harganya yang affordable. [Daftar](https://cloud.vast.ai/?ref_id=124940) sekarang sebelum GPUnya habis (FCFS).

> [!IMPORTANT]
> ** Kebutuhan VRAM tergantung model AI yang akan kamu mining. Silahkan lihat [dokumentasinya](https://docs.heurist.ai/guides/miner-guide) untuk informasi yang lebih lengkap. Jika kamu mau menjalankan 2 model sekaligus maka gunakan speksifikasi yang kita rekomendasikan.

## Persiapan VPS

### Persiapan Templates
1. Buka menu `Templates` > Pilih `Pytorch 2.2.0 Cuda12.1 Devel` dan Klik `Edit`![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/a41526df-98ae-4afd-9b6d-b3978fb5bf50)
2. Pada tab `Version Tag`, Pilih `2.1.2-cuda.12.1-cudnn8-devel`. ![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/5e9d5266-e2a8-4c05-bd68-b7f618d68acc)
3. Klik `Select and Save`

### Membeli VPS
1. Buka menu `Search`
2. Geser slider `Disk Space to Allocate` dan Centang `Unverified Machines`
3. Pilih GPU yang ingin dibeli lalu klik `Rent`. Di sini saya menggunakan RTX 4090. ![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/ca856455-301e-463d-ae4a-a3e86339010d)

### Connect VPS
1. Buka menu `Instances`
2. Klik `Open` ![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/2cdfeb64-1dbd-461b-b121-93ad8e4169f0)
3. Klik `File` > `New` > `Terminal` ![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/315f2de8-dfcb-4dfc-b494-b54d640360e4)
4. Lanjut ke tutorial selanjutnya.

## Dependencies

### Updates All Packages
```
sudo apt update && sudo apt upgrade
```

### Install nano
```
sudo apt install nano 
```

### Install jq
```
sudo apt update && sudo apt install jq
```

### Install bc
```
sudo apt update && sudo apt install bc
```

### Download Repo Heurist
```
git clone https://github.com/heurist-network/miner-release
```

### Install Python Mining Environment
```
conda create --name gpu-3-11 python=3.11
```
```
conda init
```
Close terminal saat ini di halaman utama `Jupyter` > `Running` > Klik `Shut Down All`![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/6df9365f-c0e4-42bd-be0f-3f8cd2bf945c)
Buat terminal baru. 

> [!IMPORTANT]
> **Jika kamu mau menjalankan 2 model, maka buat 2 terminal baru.**

## Mining Stable Diffusion
Buka terminal pertama dan jalankan perintah2 di bawah ini

### Aktifkan Conda
```
conda activate gpu-3-11
```

### Buka Repo Heurist
```
cd miner-release
```

### Membuat .env
```
touch .env
```
```
nano .env
```
```
MINER_ID_O=ALAMAT_EVM_KAMU
```
Save file tersebut `Control + X`

### Install SD Mining Script
```
pip install -r requirements.txt
```

### Start Mining
```
python3 sd-miner-v1.1.0.py
```
- Ikuti langkah2 yang diberikan. 
- Setelahnya VPS kamu akan mendownload file. 
- Tunggu selama 24 jam. 
- Jika sukses tampilannya seperti: ![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/172f08fa-65f6-45e6-a077-c7b6507cad70)

> [!WARNING]
> Jika kamu menggunakan VGA dengan VRAM 24 GB sama seperti saya (RTX 4090) dan ingin menjalankan 2 model sekaligus. Maka jalankan command `python3 sd-miner-v1.1.0.py  --exclude-sdxl`

## Mining Large Language Model (LLM)
> [!CAUTION]
> Jalankan perintah2 di bawah ini di terminal kedua

### Install LLM Python Environemnt
```
sudo apt update && sudo apt upgrade && sudo apt install software-properties-common && sudo add-apt-repository ppa:deadsnakes/ppa && sudo apt install python3-venv
```
- Ikuti langkah2 yang diberikan. 
- Setelahnya VPS kamu akan mendownload file. 
- Tunggu beberapa saat.

### Buka Repo Heurist
```
cd miner-release
```

### Membuat .env (opsional jika kamu sudah mengikuti tutorial mining Stable Diffusion)
```
touch .env
```
```
nano .env
```
```
MINER_ID_O=ALAMAT_EVM_KAMU
```
Save file tersebut `Control + X`

### Start Mining
```
./llm-miner-starter.sh openhermes-2.5-mistral-7b-gptq
```
Jika sukses tampilannya seperti: ![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/578ec529-50d8-4116-a0fa-bd7a5d8e17a6)

## Cek Waifu and Llama Points
- Pastikan kamu sudah mining selama 1 jam
- Buka [Portal Heurist](https://www.heurist.ai/portal)
- `Connect Wallet` Mining Kamu
- Buka menu `Mining`. ![image](https://github.com/ZuperHunt/Heurist-AI/assets/33769324/2c1cc8a2-2d30-4e77-b2e7-fdd5855ec731)

## Help

Join komunitas [Discord ZuperHunt](https://t.co/n7TeWVlA48) jika kamu ada pertanyaan.

## Change Logs

* 0.0.1
    * Initial Release

## Acknowledgments

Referensi
* [Psyxology_](https://twitter.com/Psyxology_/status/1775286543868952744)
