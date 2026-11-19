# CLAUDE.md

## Proje

CMW103 dersi demosu: tek dosyalık statik kişisel tanıtım sayfası (`index.html`) — matematik öğretmeni portfolyosu. Yazı makinesi efekti, karanlık mod ve TR/EN/中文 dil seçimi var. Harici build/bağımlılık yok.

## Çalıştırma

- `index.html` dosyasını tarayıcıda aç; build veya sunucu gerekmez.
- Görsel kontrol için headless Edge ile ekran görüntüsü:
  `msedge --headless=new --window-size=1280,1600 --virtual-time-budget=6000 --screenshot=shot.png file:///.../index.html`

## Skill'ler

- `/cmw103-new-session` (`.claude/skills/cmw103-new-session/SKILL.md`): CLAUDE.md'yi günceller, gerekirse `git init`, commit ve remote varsa push.

## Oturum Günlüğü

### 2026-11-19
- Sayfa tarayıcıda açıldı ve headless Edge ekran görüntüsüyle doğrulandı; hero bölümü, menü, dil ve karanlık mod düğmeleri doğru görünüyor (etkileşimler test edilmedi).
- `cmw103-new-session` skill'i oluşturuldu (istekteki yol `cmw104` yazıyordu; ad ile tutarlı olsun diye `cmw103` seçildi).
- CLAUDE.md ilk kez oluşturuldu.

## Açık İşler

- Dil (TR/EN/中文), karanlık mod ve e-posta düğmeleri tarayıcıda tıklanarak test edilmedi.
