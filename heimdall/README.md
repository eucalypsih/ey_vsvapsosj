# ey_vsvapsosj

q:
apakah bisa flash VBmeta dan Custom Recovery di Heimdall

<br>

a-ai:
**Ya, Anda bisa melakukan flash VBMeta dan Custom Recovery menggunakan Heimdall.** Heimdall adalah alat sumber terbuka alternatif Odin yang dirancang khusus untuk mem-flash perangkat Samsung melalui mode unduh (_Download Mode_).

Anda dapat melakukan proses ini secara bersamaan atau terpisah melalui baris perintah (_Command Line / CLI_).

### Cara Flash via Baris Perintah (CLI)
Pastikan file kustom recovery (seperti TWRP atau OrangeFox) dan file `vbmeta` Anda sudah berformat `.img` (bukan `.tar` atau `.md5`). Matikan ponsel dan masuk ke **Download Mode**, lalu hubungkan ke PC.

Gunakan perintah di bawah ini sesuai kebutuhan Anda:
-   Flash VBMeta dan Recovery Sekaligus (Direkomendasikan)
    ```bash
    heimdall flash --VBMETA vbmeta.img --RECOVERY recovery.img
     ```
-   Flash Tanpa Otomatis Reboot
Jika Anda ingin mencegah perangkat langsung menyala ke sistem agar kustom recovery tidak tertimpa recovery bawaan, tambahkan perintah `--no-reboot`:
    ```bash
    heimdall flash --VBMETA vbmeta.img --RECOVERY recovery.img --no-reboot
    ```
-   Hanya Flash VBMeta
    ```bash
    heimdall flash --VBMETA vbmeta.img
     ```
-   Hanya Flash Recovery
    ```bash
    heimdall flash --RECOVERY recovery.img
    ```

### Aturan Penting Nama Partisi
Heimdall bersifat sensitif terhadap huruf besar dan kecil (_case-sensitive_). Nama argumen partisi harus ditulis dengan huruf kapital penuh (`--VBMETA` dan `--RECOVERY`) agar sistem mengenali partisi perangkat Samsung Anda dengan tepat.

Jika Anda ingin memastikan nama partisi pada ponsel Anda, Anda bisa mengunduh berkas tabel partisi terlebih dahulu dengan mengetik perintah `heimdall download-pit --output file.pit`.


<br>

