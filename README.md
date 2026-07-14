# UAS Sistem Operasi + Jaringan Komputer - Kelas Sentul

## 1. Arsitektur Sistem Target
* **Alur Deployment:** Developer melakukan `git push` ke GitHub -> GitHub Actions (CI/CD) mendeteksi perubahan -> Melakukan koneksi SSH ke VPS untuk otomatisasi `docker compose pull && docker compose up -d`.
* **Alur Akses User:** User mengakses `uassisop-tia.my.id` -> Cloudflare (SSL/TLS Flexible) -> Nginx Reverse Proxy di VPS -> Docker App Container (Port 80/HTML).

## 2. Runbook (Prosedur Operasional & Emergency)

### Prosedur Restart Aplikasi (Skenario 1 - Container App Down)
Jika aplikasi mati atau container terhenti, jalankan perintah berikut di terminal VPS:
```bash
docker compose restart
