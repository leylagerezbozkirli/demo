---
name: cmw103-new-session
description: Oturumu kapatma rutini - CLAUDE.md'yi bu oturumda yapılanlarla günceller, gerekirse git init yapar, değişiklikleri anlamlı bir mesajla commit eder ve remote varsa push eder. Kullanıcı /cmw103-new-session dediğinde veya oturumu kaydetmek/kapatmak istediğinde kullan.
---

# cmw103-new-session

Bu adımları **sırayla** uygula. Bir adım başarısız olursa dur, hatayı kullanıcıya aynen göster ve sonraki adıma geçme.

## 1. CLAUDE.md'yi güncelle

- Proje kökündeki `CLAUDE.md` dosyasını oku. Yoksa oluştur.
- Bu oturumda yapılanları konuşma geçmişinden çıkar: değişen/eklenen dosyalar, eklenen özellikler, verilen kararlar, çalıştırma yöntemi, açık kalan işler.
- Dosyada şu bölümler olsun (varsa güncelle, kopyalama yapma):
  - **Proje** - kısa tanım (örn. tek dosyalık statik kişisel tanıtım sayfası: `index.html`).
  - **Çalıştırma** - nasıl açılır/test edilir (örn. `index.html` tarayıcıda açılır; build yok).
  - **Oturum Günlüğü** - en üste bugünün tarihiyle (YYYY-MM-DD) yeni bir başlık ekle ve bu oturumda yapılanları madde madde yaz. Eski kayıtları silme.
  - **Açık İşler** - yarım kalanlar / sonraki adımlar.
- Kısa ve somut yaz; kodda veya git geçmişinde zaten açıkça görünen ayrıntıları tekrar etme.
- Kişisel bilgileri (e-posta vb.) CLAUDE.md'ye yazma.

## 2. Git reposu yoksa oluştur

```bash
git rev-parse --is-inside-work-tree 2>/dev/null || git init
```

Repo zaten varsa hiçbir şey yapma.

## 3. Commit et

```bash
git status --short
git diff --stat
```

- Değişiklik yoksa "commit edilecek değişiklik yok" de ve 4. adıma geç.
- `.env`, anahtar, şifre gibi gizli bilgi içeren dosyaları **ekleme**; görürsen kullanıcıyı uyar.
- Değişiklikleri ekle (`git add -A`) ve diff'e bakarak **anlamlı, Türkçe** bir commit mesajı yaz (repo geçmişindeki stile uy, örn. "Dil seçeneklerine Çince eklendi"). Mesaj neyin neden değiştiğini anlatsın; "güncelleme" gibi genel mesajlar kullanma.
- Hook'ları atlama (`--no-verify` kullanma).

## 4. Remote varsa push et

```bash
git remote
```

- Çıktı boşsa: "Remote yok, push atlandı" de ve bitir.
- Remote varsa **push yap**:
  ```bash
  git push -u origin HEAD
  ```
  (Remote adı `origin` değilse `git remote` çıktısındaki ilk adı kullan.)
- Push reddedilirse (ör. remote önde) **force push yapma**; hatayı kullanıcıya göster ve `git pull --rebase` önermekle yetin.

## Son rapor

Kullanıcıya kısa özet ver: CLAUDE.md'de ne güncellendi, git init yapıldı mı, commit hash'i ve mesajı, push yapıldı mı (hangi remote/branch).
