# Study Deck – Capacitor Android Project

Personalized quiz cards for any subject or exam.

---

## Easiest way: Build APK online with GitHub (can be done from phone)

This method uses **GitHub Actions** (free). You only need a free GitHub account and a phone browser.

### Step-by-step (phone-friendly)

1. **Create a free GitHub account** (if you don’t have one)  
   → https://github.com/signup

2. **Create a new repository**
   - Tap the **+** → **New repository**
   - Name it: `studydeck` (or any name)
   - Keep it **Public**
   - Do **not** add README, .gitignore, or license
   - Tap **Create repository**

3. **Upload the project files**
   - On the new empty repo page, tap **uploading an existing file**
   - Upload **all** the files and folders from this project:
     - `www/` folder (with `index.html` inside)
     - `.github/` folder (with the workflow inside)
     - `package.json`
     - `capacitor.config.json`
     - `README.md`
     - `.gitignore`
   - Scroll down → write any commit message → tap **Commit changes**

4. **Start the build**
   - Go to the **Actions** tab of your repository
   - Tap the workflow named **“Build Android APK”**
   - Tap **Run workflow** → **Run workflow** (green button)
   - Wait 4–8 minutes for the build to finish (you will see a green checkmark)

5. **Download the APK**
   - Open the completed workflow run
   - Scroll down to **Artifacts**
   - Tap **studydeck-debug-apk** to download the zip
   - Unzip it → you get `app-debug.apk`
   - Transfer the APK to your phone and install it  
     (you may need to allow “Install from unknown sources” in Android settings)

---

## Important note about quiz generation

The app tries to call the Anthropic API to generate questions.  
**A real API key must never be put inside the APK.**  

Until you add a backend proxy, the “Generate quiz” button will show an error.  
The rest of the app (UI, history, results) works fine.

---

## Project structure

```
studydeck-app/
├── www/
│   └── index.html
├── .github/
│   └── workflows/
│       └── build-android.yml   ← this builds the APK for you
├── capacitor.config.json
├── package.json
├── .gitignore
└── README.md
```

---

## Alternative: Build on a computer (if you get access later)

```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

Then use Android Studio → Run or Generate Signed APK.
