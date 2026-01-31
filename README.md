# 🌟 Kids Quiz Game – Layan Amashhadani

A fun quiz for kids (ages 6–10) with Countries, History, Animals, Science, Sports, timer, two-player mode, and Arabic/English.

**Live:** [Play the quiz](https://drmahmoodhachim-gif.github.io/kids-quiz_lAYAN/)

---

## 🌐 See scores from ALL users (different devices & locations)

By default, **top scorers** and **who tried the quiz** are stored only in the **browser** (this device). To see scores from **everyone** – any device, any location – you need to connect the quiz to **Firebase**.

### Quick steps

1. **Create a Firebase project**  
   Go to [console.firebase.google.com](https://console.firebase.google.com) → Create project.

2. **Create a Realtime Database**  
   In the project: **Build** → **Realtime Database** → Create Database (e.g. test mode).

3. **Get your config**  
   **Project settings** (gear) → **Your apps** → Add web app if needed → Copy the `firebaseConfig` object.

4. **Add config to the quiz**  
   Open **index.html** in an editor. Find:
   ```javascript
   const FIREBASE_CONFIG = {
     apiKey: "AIzaSyDummyReplaceWithYourOwnFromFirebaseConsole",
     ...
   };
   ```
   Replace the **whole** `FIREBASE_CONFIG` object with your copied config (with your real `databaseURL`, etc.).

5. **Set database rules**  
   In Firebase: **Realtime Database** → **Rules**. Use:
   ```json
   {
     "rules": {
       "quiz": {
         ".read": true,
         ".write": true
       }
     }
   }
   ```
   Click **Publish**.

6. **Upload the updated quiz**  
   Save **index.html** and push to GitHub (or re-upload).  
   After that, everyone who opens the quiz will see the **same** top scorers and “who tried the quiz” list, from any device or location.

---

For more detail, see **FIREBASE-SETUP.md** in the project (if you have it locally).
