# 🪙 Saudi Gold Shop Price Evaluator

A lightweight, offline-first mobile web application built for shoppers in Saudi Arabia to instantly calculate global gold benchmarks in Saudi Riyals (SAR), strip out VAT, isolate jewelry manufacturing charges (*المصنعية*), and determine whether a gold shop's quote is fair before buying.

---

## 🌐 Live App Link

👉 **[Open the Saudi Gold Price Evaluator](https://ayhalali.github.io/gold-calculator/)**

---

## ✨ Key Features

* **One-Time Live Spot Price Fetch:** Automatically fetches the current global **24K gold spot price (`XAU/USD` per troy ounce)** upon opening, with an offline fallback and manual refresh trigger (Price is a bit late).
* **Multi-Karat Support:** Instantly converts the global 24K benchmark into **24K, 22K, 21K, and 18K** per-gram prices in **SAR** (using the fixed `3.75 SAR/USD` peg and `31.1035 g/oz` conversion).
* **VAT Extraction & Workmanship Breakdown:** Divides the shop's total receipt price by piece weight, removes **15% VAT** (editable—supports `0%` for 24K investment bullion), and calculates the exact **manufacturing fee in both SAR/gram and percentage (%)**.
* **Automated Purchase Verdict:**
  * 🟢 **Good Price (`< 5%` markup):** Great deal—proceed with confidence.
  * 🟡 **Fair Price (`5% – 10%` markup):** Reasonable retail rate; minor room to negotiate.
  * 🔴 **Overpriced (`> 10%` markup):** High workmanship fee; displays the exact target receipt price to negotiate down to.
  * *(Thresholds are customizable inside the app's settings drawer.)*
* **Live Karat Target Guide:** Displays a real-time reference table showing the maximum receipt price per gram (including VAT) that qualifies as a **Good** or **Fair** deal across all karats.
* **Multi-Shop Quote Comparison:** Save and compare quotes from multiple gold shops side-by-side.
* **100% Offline & Background Persistence:** Built as a zero-dependency single-page web app with local storage persistence—your numbers and saved shop quotes remain intact even without cell reception inside a gold souq or after force-closing the app.

---

## 📱 How to Add to Your iPhone Home Screen

Adding the web app to your iPhone Home Screen lets you launch it full-screen like a native app and use it completely offline:

1. Open **Safari** on your iPhone and navigate to your live app link (`https://ayhalali.github.io/gold-calculator/`).
2. Tap the **Share** button at the bottom of the screen (the square icon with an upward arrow).
3. Scroll down the share menu and tap **Add to Home Screen**.
4. Ensure **Open as Web App** is toggled **On** (if shown), customize the icon name if desired, and tap **Add** in the top-right corner.
5. Tap the new **Gold Evaluator** icon on your iPhone Home Screen anytime to launch it.

---

## 🧮 How the Calculation Works

1. **Global Karat Base Price (SAR/g):**
   $$\text{Base Price per Gram} = \left(\frac{\text{24K Spot USD/oz}}{31.1035}\right) \times 3.75 \times \left(\frac{\text{Karat}}{24}\right)$$
2. **Shop Net Price Excluding VAT (SAR/g):**
   $$\text{Net Price per Gram} = \frac{\text{Total Shop Price} \div \text{Weight (g)}}{1 + \text{VAT Rate}}$$
3. **Manufacturing Markup Rate (%):**
   $$\text{Manufacturing Rate (\%)} = \frac{\text{Net Price per Gram} - \text{Base Price per Gram}}{\text{Base Price per Gram}} \times 100$$

---

## 📂 Repository Structure

```text
├── index.html      # Self-contained offline-ready web application
└── README.md       # Project documentation and setup guide
