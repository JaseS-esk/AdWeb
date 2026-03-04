# AD Yönetim — Kurulum ve Çalıştırma Kılavuzu

## Gereksinimler

- Windows 10/11 (64-bit)
- Active Directory Domain ortamı
- Geçerli lisans anahtarı

---

## Kurulum (İlk Çalıştırma)

### 1. Dosyayı Çalıştır

`ADYonetim.exe` dosyasına çift tıklayın. Kurulum sihirbazı otomatik açılır.

### 2. Lisans Aktivasyonu

| Alan | Açıklama |
|------|----------|
| **HWID** | Sisteme özgü donanım kimliği — otomatik gösterilir |
| **Lisans Anahtarı** | Alınan anahtar — 5 deneme hakkı |

> 📋 **HWID Kopyala** butonu ile HWID'i panoya alabilirsiniz.

### 3. Sunucu Ayarları

| Alan | Varsayılan | Açıklama |
|------|-----------|----------|
| **Port** | `8000` | Sunucunun dinleyeceği port (1024–65535) |
| **AD Kullanıcı Adı** | — | `DOMAIN\kullanıcıadi` veya `kullanıcıadi` |

### 4. Domain Keşfi

Ağdaki Active Directory domainleri otomatik taranır.  
Bulunamazsa uygulamadan manuel olarak eklenebilir.

### 5. Tamamlama

**"Sunucuyu Başlat"** butonuna basın → uygulama log monitörüne geçer ve tarayıcı otomatik açılır.

---

## Sonraki Çalıştırmalar

`ADYonetim.exe`'ye çift tıklayın. Sihirbaz atlanır, sunucu doğrudan başlar.

---

## Lisans Üretimi (Keygen)

```
python keygen_gui.py
```

| Özellik | Açıklama |
|---------|----------|
| **Tek HWID** | HWID gir → Anahtar üret → Kopyala |
| **Yerel HWID** | "Yerel HWID'i Al" ile otomatik doldur |
| **Toplu Üretim** | Her satıra bir HWID → Tümünü üret |

---

## Kurulumu Sıfırlama

Sihirbazı tekrar açmak için şu dosyaları silin:

```
ADYonetim.exe'nin yanındaki:
  ├── .license   ← sil
  └── .env       ← sil
```

---

## Teknik Bilgi

| Öğe | Değer |
|-----|-------|
| Sunucu | FastAPI + Uvicorn |
| Varsayılan URL | `http://localhost:8000` |
| Veri dizini | `exe_klasörü/data/` |
| Yönetici tanımı | `data/admins.json` |
| Log dizini | `exe_klasörü/logs/` |
