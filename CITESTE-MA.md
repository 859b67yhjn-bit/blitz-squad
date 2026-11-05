# Blitz Squad pe iPhone, fără Xcode

Proiectul ăsta face din joc o aplicație iOS adevărată (Capacitor). Compilarea o face GitHub pe un Mac din cloud, gratuit. Tu primești un fișier `.ipa` și îl pui pe telefon cu Sideloadly și Apple ID-ul tău.

## 1. Pune proiectul pe GitHub (o singură dată)

1. Fă-ți cont gratuit pe https://github.com/signup.
2. Apasă **New repository**, nume `blitz-squad`, alege **Private**, apoi **Create repository**.
3. Pe pagina repo-ului apasă **uploading an existing file** și trage **tot conținutul** folderului `blitz-ios`, inclusiv folderul `.github`.
   - Folderul `.github` e ascuns de sistem. Pe Windows: Explorer, **View**, bifează **Hidden items**. Pe Mac: în Finder apasă `Cmd + Shift + .`
   - Dacă browserul nu ia folderul `.github`, folosește aplicația gratuită **GitHub Desktop**.
4. Apasă **Commit changes**.

## 2. Construiește aplicația

1. Intră în tab-ul **Actions** al repo-ului. Dacă GitHub întreabă, apasă butonul verde care activează workflow-urile.
2. Workflow-ul **Construieste aplicatia iOS** pornește singur după fiecare încărcare. Îl poți porni și manual cu **Run workflow**.
3. Durează cam 10–15 minute. Când apare bifa verde, intră pe rulare și descarcă **BlitzSquad-ipa** de jos, din secțiunea **Artifacts**.
4. Dezarhivează și ai `BlitzSquad.ipa`.

## 3. Instalează pe iPhone cu Sideloadly

1. Descarcă Sideloadly de pe https://sideloadly.io (Windows sau Mac).
   - Pe Windows instalează și **iTunes** și **iCloud** de pe site-ul Apple, nu din Microsoft Store.
2. Conectează iPhone-ul prin cablu și apasă **Ai încredere** pe telefon.
3. În Sideloadly trage `BlitzSquad.ipa`, scrie Apple ID-ul tău și apasă **Start**. Introdu parola și codul de verificare dacă le cere.
4. Pe iPhone: **Setări → General → VPN și gestionare dispozitiv**, alege Apple ID-ul tău și apasă **Ai încredere**.
5. Pe iOS 16 sau mai nou: **Setări → Confidențialitate și securitate → Mod dezvoltator → Pornit**, apoi repornește telefonul.

## Bine de știut

- Cu un Apple ID gratuit, aplicația merge **7 zile**. După aceea o reinstalezi la fel cu Sideloadly. Progresul (monede, campioni, trofee) rămâne cât timp nu ștergi aplicația.
- Contul gratuit permite maxim 3 aplicații instalate așa.
- Cu un cont Apple Developer plătit (99 $ pe an) aplicația ține un an și poți folosi TestFlight pentru prieteni.
- **Versiuni noi:** înlocuiești folderul `www` din repo cu cel nou și GitHub construiește singur un `.ipa` nou.
- Multiplayer-ul cu prietenii merge momentan doar în versiunea din linkul Claude. În aplicația nativă va avea nevoie de un server propriu.

## Ce e în folder

- `www/` – jocul complet (cod, modele 3D, imagini, fonturi), merge și fără internet.
- `resources/` – iconița și ecranul de pornire.
- `capacitor.config.json`, `package.json` – setările aplicației (`ro.blitzsquad.joc`).
- `.github/workflows/ios.yml` – rețeta după care GitHub compilează aplicația.
