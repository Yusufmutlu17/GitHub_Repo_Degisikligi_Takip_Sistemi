# 📌 GitHub Repository Tracker

## 📖 Giriş

GitHub Repository Tracker, belirlenen GitHub repolarını belirli zaman aralıklarında otomatik olarak izleyen bir Python uygulamasıdır. Program, GitHub REST API üzerinden repository bilgilerini alarak **yıldız (⭐) sayısı** ve **son güncellenme (push) tarihi** gibi bilgileri takip eder.

Takip edilen repolarda herhangi bir değişiklik tespit edildiğinde kullanıcıya **Windows masaüstü bildirimi** gönderilir. Böylece GitHub hesabını sürekli kontrol etmeye gerek kalmadan önemli değişikliklerden anında haberdar olunabilir.

Programın arka planda kolayca çalıştırılabilmesi amacıyla Python dosyası **PyInstaller** kullanılarak `.exe` formatına dönüştürülmüştür. İsteğe bağlı olarak bu uygulama Windows başlangıcına eklenerek bilgisayar açıldığında otomatik olarak çalıştırılabilir.

---

# 🛠 Kullanılan Teknolojiler

* **Python** – Projenin geliştirilmesinde kullanılan programlama dili.
* **GitHub REST API** – Repository bilgilerini almak için kullanılmıştır.
* **Requests** – GitHub API'ye HTTP istekleri göndermek amacıyla kullanılmıştır.
* **Plyer** – Windows masaüstü bildirimleri oluşturmak için kullanılmıştır.
* **PyInstaller** – Python uygulamasını bağımsız çalıştırılabilir (.exe) dosyasına dönüştürmek için kullanılmıştır.

---

# ⚙ Çalışma Mantığı

Program aşağıdaki adımları izleyerek çalışmaktadır:

1. Kullanıcı, takip etmek istediği GitHub repolarını `favorite_repos` listesine ekler.
2. Program, GitHub REST API üzerinden her repository'nin güncel bilgilerini alır.
3. İlk çalıştırmada elde edilen bilgiler belleğe kaydedilir.
4. Program arka planda sürekli çalışarak her **60 saniyede bir** repository bilgilerini yeniden kontrol eder.
5. Eğer;

   * Repository'nin yıldız sayısı değişmişse,
   * veya son güncellenme (push) tarihi değişmişse,

   kullanıcıya masaüstü bildirimi gönderilir.
6. Güncel bilgiler belleğe kaydedilir ve izleme işlemi aynı şekilde devam eder.

---

# ✨ Özellikler

* GitHub repositorylerini otomatik olarak takip eder.
* Repository yıldız sayısındaki değişiklikleri algılar.
* Son güncellenme tarihindeki değişiklikleri kontrol eder.
* Windows masaüstü bildirimi gönderir.
* Arka planda kesintisiz çalışabilir.
* `.exe` olarak kullanılabilir.
* Windows başlangıcında otomatik çalışacak şekilde yapılandırılabilir.

---


Gerekli Python kütüphanelerini yükleyin:

```bash
pip install requests plyer
```

Ardından `favorite_repos` listesine takip etmek istediğiniz GitHub repolarını ekleyin.

Örnek:

```python
favorite_repos = {
    "OpenAI": "https://github.com/openai/openai-python",
    "Python": "https://github.com/python/cpython"
}
```

Programı çalıştırmak için:

```bash
python takip.py
```

veya oluşturduğunuz `takip.exe` dosyasını çalıştırabilirsiniz.

---

# 📌 Kullanım Senaryosu

Program çalıştırıldıktan sonra arka planda belirlenen GitHub repolarını düzenli olarak kontrol eder. Takip edilen repository üzerinde yeni bir güncelleme yapılması veya yıldız sayısında değişiklik meydana gelmesi durumunda kullanıcıya Windows bildirim sistemi üzerinden anlık bildirim gönderilir.

---

# ⚠ Not

* Program GitHub REST API kullanmaktadır.
* Kontrol aralığı varsayılan olarak **60 saniye** olarak ayarlanmıştır.
* Çok sayıda repository'nin kısa aralıklarla sorgulanması GitHub API'nin istek sınırlarına (Rate Limit) ulaşılmasına neden olabilir.
* Programın bilgisayar açıldığında otomatik başlaması için oluşturulan `.exe` dosyası Windows Başlangıç klasörüne eklenebilir.

---


