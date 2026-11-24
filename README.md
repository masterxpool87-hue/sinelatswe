# ဆိုင်လက်စွဲ — Offline POS Website

GitHub Pages တွင် တင်ရန် ပြင်ဆင်ထားသော Static Website ဖြစ်သည်။

## ပါဝင်သည့်အရာများ

- `index.html` — Website အပြည့်အစုံ (Responsive layout, animations, Burmese UI)
- `assets/app-logo.jpg` — ဆိုင်လက်စွဲ App Logo
- `assets/store-logo.jpg` — ဗိုလ်တထောင် Online Store Logo

## GitHub Pages တင်နည်း

1. GitHub တွင် Repository အသစ်တစ်ခု ဖန်တီးပါ။ ဥပမာ `sinelatswe-website`။
2. ဤ Folder ထဲရှိ `index.html`, `README.md` နှင့် `assets` Folder ကို Repository ၏ root ထဲသို့ Upload လုပ်ပါ။ `assets` folder အတွင်းရှိ ပုံနှစ်ပုံလည်း ပါရမည်။
3. Repository → **Settings** → **Pages** သို့ သွားပါ။
4. **Build and deployment** တွင် `Deploy from a branch` ကို ရွေးပါ။
5. Branch ကို `main`, Folder ကို `/(root)` ရွေးပြီး **Save** နှိပ်ပါ။
6. GitHub Pages က Website URL ကို ပြသပေးပါလိမ့်မည်။ Publish ပြီးပါက ဖုန်းနှင့် PC နှစ်မျိုးလုံးမှ စမ်းသပ်ပါ။

## Activation Generator — လုံခြုံရေး အလွန်အရေးကြီး

Website ၏ Activation Generator သည် လက်ရှိ `LicenseManager.kt` Logic နှင့် တူညီသော Algorithm ကို အသုံးပြုသည်:

```text
SHA-256(ANDROID_DEVICE_ID + "-" + SECRET_KEY)
first 10 hexadecimal characters, uppercase
formatted as XXXX-XXXX-XX
```

လက်ရှိ Secret Key သည် Website JavaScript ထဲတွင် client-side ထည့်ထားသောကြောင့် GitHub Pages တွင် Publish လုပ်သည်နှင့် မည်သူမဆို Source Code ကြည့်ပြီး ထုတ်ယူနိုင်သည်။ ထို့ကြောင့် ဒီ Generator ကို Public Website ပေါ်တွင် တင်ထားပါက လူတိုင်း Key ထုတ်နိုင်ပြီး၊ အခကြေးငွေပေးပြီးမှ Activate လုပ်စေလိုသည့် License Control အဖြစ် မလုံခြုံပါ။

**လက်တွေ့အသုံးပြုရန် အကြံပြုချက်:** Public website ကို Download / Guide / Contact အတွက်သာ အသုံးပြုပြီး Activation Key Generator ကို private PC ထဲတွင်သာ ထားပါ။ Public online generator လိုအပ်ပါက Secret Key ကို Browser ထဲမထည့်ဘဲ Server-side API (ဥပမာ Cloudflare Worker + server secret) ဖြင့် ထုတ်ပေးရန် လိုအပ်သည်။

## ပြင်ဆင်ထားသော Links

- YouTube: https://www.youtube.com/watch?v=ejK-yS4P9ak
- Official info: https://sites.google.com/view/sinelatswe/home
- App Facebook: https://www.facebook.com/shoplatswe/
- Store Facebook: https://www.facebook.com/bo1000ygn
- MediaFire / Google Drive / Upload-Apk download links: `index.html` ထဲတွင် ထည့်သွင်းထားသည်။

## Local Preview

GitHub Pages HTTPS ပေါ်တွင် Activation Generator အလုပ်လုပ်မည်။ Local `file://` ဖြင့်ဖွင့်ရာတွင် Browser ၏ Web Crypto API ကန့်သတ်ချက်ကြောင့် Generate Key မလုပ်နိုင်ပါက အောက်ပါ command ဖြင့် local server ဖွင့်ကြည့်ပါ:

```bash
python -m http.server 8000
```

ပြီးလျှင် `http://localhost:8000` ကို Browser တွင်ဖွင့်ပါ။
