# Connect Google & Firebase Authentication (Step-by-Step)

With Firebase Auth integrated, students can simply click **"Continue with Google"** on your site (whether hosted on Vercel or Cloudflare) to immediately log in. No manual account creation is required!

---

## 3 Quick Steps on Firebase Console:

### Step 1: Open Your Firebase Project
1. Go to **[https://console.firebase.google.com/](https://console.firebase.google.com/)**
2. Click **Create a project** (or select your existing project). Name it anything (e.g. `ai-roadmap`).

### Step 2: Enable Google Authentication
1. In the left sidebar, click **Build** -> **Authentication**.
2. Click **Get Started**.
3. Under the **Sign-in method** tab, click **Google**.
4. Toggle **Enable**.
5. Set your support email (your Gmail) and click **Save**.

### Step 3: Enable Firestore Database (To sync student learning progress)
1. In the left sidebar, click **Build** -> **Firestore Database**.
2. Click **Create database** -> Choose **Start in test mode** -> Click **Next** -> Click **Enable**.

### Step 4: Get Your Web App Config
1. Click the **Settings Gear ⚙️** at top left -> **Project settings**.
2. Scroll down to **Your apps**, click the web icon (`</>`).
3. Give it a nickname and click **Register app**.
4. You will see a `firebaseConfig` snippet like this:
```json
{
  "apiKey": "AIzaSy...",
  "authDomain": "your-project.firebaseapp.com",
  "projectId": "your-project",
  "storageBucket": "your-project.appspot.com",
  "messagingSenderId": "123456789",
  "appId": "1:12345:web:abcdef"
}
```

---

## How to Connect It in Your App:
1. Open your Roadmap website and log in as admin with passcode **`ashu`**.
2. Go to **Admin Panel** (`/#/admin`).
3. Under **Firebase Cloud Sync ☁️**, click **⚙️ Connect Your Free Firebase Database**.
4. Paste the JSON config into the box and click **Connect & Save**.

---

## Add Your Hosted Domain (Vercel / Cloudflare) to Authorized Domains
To allow Google login from your deployed Vercel/Cloudflare URL:
1. In Firebase Console, go to **Authentication** -> **Settings** tab -> **Authorized domains**.
2. Click **Add domain**.
3. Add your Vercel or Cloudflare domain (e.g., `your-app.vercel.app` or `your-app.pages.dev`).
*(Note: `localhost` is already enabled by default!)*
