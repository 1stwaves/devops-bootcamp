# Project Rules

Aturan berikut wajib dipatuhi untuk setiap perubahan kode dan konfigurasi di dalam project ini:

## 1. Shell Script (`.sh`)
- Setiap file `.sh` **wajib** diawali dengan shebang:
  ```bash
  #!/usr/bin/env bash
  set -euo pipefail
  ```

## 2. Terraform (`.tf`)
- Gunakan sintaks Terraform terbaru.
- Setiap blok `variable` **wajib** menyertakan `type` (tipe data) dan `description` (deskripsi).
- **Dilarang** melakukan hardcode credential, secret, token, atau password di dalam file `.tf` (gunakan variable, secret manager, atau environment variable).

## 3. YAML (`.yaml`)
- Gunakan indentasi **2 spasi** secara konsisten (hindari tab).

## 4. JSON (`.json`)
- Pastikan setiap file `.json` berformat valid tanpa *trailing comma* atau komentar.

## 5. Validasi Sebelum Commit
- Sebelum menjalankan `git commit`, **selalu** jalankan validasi sintaks lokal terlebih dahulu terhadap file yang diubah atau ditambahkan (misalnya `bash -n` / `shellcheck` untuk `.sh`, `terraform fmt -check` / `terraform validate` untuk `.tf`, validasi YAML, dan validasi JSON).
