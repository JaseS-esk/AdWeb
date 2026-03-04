# 🛡️ AD Yönetim — Active Directory Management Suite

> modern web arayüzü ile AD yönetimini kolaylaştıran, tek exe paketi ile kurulumu son derece basit bir yönetim çözümü.

---

## 📸 Özellikler

| Modül | Açıklama |
|-------|----------|
| 🔐 **Kullanıcı Yönetimi** | AD kullanıcılarını listeleme, arama, kilit açma, durum değiştirme |
| 🔑 **Şifre Sıfırlama** | Tek veya toplu kullanıcı şifre sıfırlama |
| 👥 **Grup Yönetimi** | Grup üyelerini görüntüleme, ekleme ve çıkarma |
| 💻 **Bilgisayar Yönetimi** | AD bilgisayarlarını yönetme ve durum takibi |
| 🔒 **BitLocker** | Recovery key sorgulama ve görüntüleme |
| 📊 **Denetim Kayıtları** | SUCCESS/FAILURE/WARNING filtrelemeli audit log sistemi |
| ⚡ **Toplu İşlem** | Çoklu kullanıcı üzerinde aynı anda işlem yapma |
| 📈 **Dashboard** | Gerçek zamanlı AD istatistikleri ve aktivite akışı |
| 🔐 **HWID Lisanslama** | Donanım bazlı lisans sistemi ile yetkisiz kullanım önleme |

---

## 🏗️ Teknik Altyapı

```
┌─────────────────────────────────────────────────┐
│                  ADYonetim.exe                  │
│  ┌──────────────────┬──────────────────────┐   │
│  │   Tkinter GUI    │   Kurulum Sihirbazı  │   │
│  │   (Setup Wiz.)   │   + Log Monitoru     │   │
│  └──────────┬───────┴──────────────────────┘   │
│             │ embed                             │
│  ┌──────────▼───────────────────────────────┐  │
│  │          FastAPI + Uvicorn               │  │
│  │   REST API  ·  JWT Auth  ·  CORS         │  │
│  └──────────────────┬───────────────────────┘  │
│                     │ PowerShell (hidden)       │
│  ┌──────────────────▼───────────────────────┐  │
│  │         Active Directory (LDAP)          │  │
│  └──────────────────────────────────────────┘  │
└─────────────────────────────────────────────────┘
        ▲
        │ HTTP (localhost)
┌───────┴──────────────────┐
│   React 18 + Vite SPA    │
│   Tailwind CSS · Recharts │
└──────────────────────────┘
```

### Backend
- **Python 3.12** + **FastAPI** — Asenkron REST API
- **Uvicorn** — ASGI web sunucusu
- **PowerShell** — Active Directory komutları (gizli, terminalsiz)
- **JWT** — Stateless kimlik doğrulama
- **PyInstaller** — Tek exe paketi (`--onefile --noconsole`)

### Frontend
- **React 18** + **Vite** — Modern SPA framework
- **Tailwind CSS** — Utility-first stil sistemi
- **React Router v6** — Client-side routing
- **Recharts** — İnteraktif grafikler
- **Lucide React** — İkon seti

### Güvenlik
- **HWID Tabanlı Lisans** — Her makineye özgü donanım kimliği
- **JWT Session Yönetimi** — Token bazlı oturum
- **PowerShell Execution Policy Bypass** — Güvenli PS çalışma ortamı
- **Audit Logging** — Tüm işlemler `[SUCCESS]`/`[FAILURE]`/`[WARNING]` etiketiyle kayıt altına alınır
- **Role-Based Access Control** — Admin / Viewer yetki seviyeleri

---

## 🚀 Dağıtım Mimarisi

```
ad-yonetim-exe/
├── ADYonetim.exe      ← Tek dosya, kurulum gerektirmez
└── (Otomatik oluşturulanlar)
    ├── .license       ← HWID lisans dosyası
    ├── .env           ← Sunucu ayarları (port, secret)
    ├── data/
    │   └── admins.json   ← Yönetici kullanıcılar
    └── logs/
        └── audit.log     ← Denetim kayıtları
```

---

## ✨ Öne Çıkan Teknik Kararlar

### 🎁 Single Executable Deployment
PyInstaller `--onefile` ile tüm Python bağımlılıkları, React build dosyaları ve PowerShell scriptleri tek bir `.exe` içinde paketlendi.

### 🖥️ Terminalsiz GUI
`--noconsole` + Tkinter tabanlı kurulum sihirbazı. Sunucu başladıktan sonra stdout/stderr GUI içindeki log monitörüne yönlendiriliyor.

### 🔇 Silent PowerShell
Tüm `subprocess.run()` çağrıları `CREATE_NO_WINDOW` flag'i ile çalışıyor — kullanıcı arayüzünde hiçbir terminal penceresi görünmüyor.

---

## 📋 Sistem Gereksinimleri

| Bileşen | Gereksinim |
|---------|-----------|
| İşletim Sistemi | Windows 10/11 (64-bit) |
| Active Directory | Windows Server 2012+ |
| Çalışma Modu | Domain Controller erişimi olan sunucu/istemci |
| RAM | Min. 2 GB |
| Disk | Min. 500 MB |

---

## 🔗 İletişim

> Bu proje, kurumsal Active Directory yönetimini modern web teknolojileriyle birleştiren, güvenli ve kullanımı kolay bir çözüm sunmak amacıyla geliştirilmiştir.

---