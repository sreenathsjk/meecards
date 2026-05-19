# TapID — Smart Digital Identity Cards
### India's Smartest Digital Identity Platform

> *"Tap. Connect. Own your identity."*  
> Built for professionals, students, and entrepreneurs — starting from Anantapur, Andhra Pradesh.

---

## 📁 Project File

| File | Description |
|------|-------------|
| `tapid-website.html` | Complete single-file website — open in any browser |

---

## 🌐 What This Website Does

TapID is a full marketing + product website for a Smart Digital Identity Card startup targeting India's Tier 2 & 3 markets. The site includes:

- **Homepage Hero** — Brand intro, tagline, stats, and CTAs
- **Marquee Strip** — Scrolling feature highlights
- **Card Types Section** — 6 plan tiers with pricing
- **Card Builder** — Form where users enter their details
- **240-Card Gallery** — Live card preview gallery with user data applied
- **Features Section** — Product benefits and stats
- **Reviews Section** — 6 testimonials from real user personas
- **FAQ Section** — 8 accordion questions
- **Footer** — Links, socials, legal

---

## 🚀 How to Run

No installation. No server. No dependencies.

```bash
# Option 1 — just open it
double-click tapid-website.html

# Option 2 — serve locally (optional)
npx serve .
# then open http://localhost:3000
```

Works in Chrome, Firefox, Safari, Edge — any modern browser.

---

## 🃏 Card Builder Flow

1. User uploads a photo (optional)
2. Fills in: Name, Designation, Company, Phone, Email, Website, WhatsApp
3. Clicks **"See My Cards — Browse 240 Unique Designs"**
4. Full-screen gallery opens with **240 unique cards** — every one is different
5. Each card shows the user's actual details, live
6. User clicks a card to select it
7. Clicks **"Download This Card"**
8. Payment modal opens → Razorpay checkout

---

## 🎨 Card Design System

The 240 cards are generated from a combination matrix:

| Dimension | Count | Examples |
|-----------|-------|---------|
| **Color Palettes** | 24 | Dark Elite, Saffron, Teal, Gold, Midnight, Rose, Royal Blue, Forest, Crimson, Violet… |
| **Layout Styles** | 10 | Standard, Compact, Wide Avatar, Minimal, Bold Name, Centered, Split, Pill Contacts, Icon Row, Sidebar |
| **Background Patterns** | 10 | Circles, Diagonal Lines, Triangle, Wave, Dots, Hexagon, Arc, Cross-hatch… |

**Total: 24 × 10 = 240 unique cards**

Every card includes:
- User's name, designation, company
- Phone, email, website
- WhatsApp connect button (if provided)
- QR code graphic
- NFC chip visual
- SVG background pattern

---

## 💳 Pricing Plans (Payment Modal)

| Plan | Price | What You Get |
|------|-------|-------------|
| Digital Card — Free | ₹0 | Download card as PNG/PDF |
| Pro Digital Card | ₹99/month | Live profile link + lead capture + analytics |
| NFC Elite Card + Pro | ₹398/month | Physical NFC card delivered + all Pro features |

---

## 💻 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML5, CSS3, JavaScript (ES6+) |
| Fonts | Google Fonts — Syne, Instrument Sans |
| Payments | Razorpay (integration point marked in code) |
| Hosting | Any static host — Vercel, Netlify, Firebase Hosting |
| No dependencies | Zero npm packages, zero frameworks |

---

## 🔌 Razorpay Integration

The payment button currently shows an `alert()` as a placeholder.  
To go live, replace the `handlePayment()` function in the `<script>` block:

```javascript
function handlePayment() {
  closePaymentModal();

  // Replace this block with real Razorpay SDK call:
  const options = {
    key: "YOUR_RAZORPAY_KEY_ID",
    amount: selPlan === 'pro' ? 9900 : 39800, // paise
    currency: "INR",
    name: "TapID",
    description: selPlan === 'pro' ? "Pro Digital Card" : "NFC Elite Card + Pro",
    image: "https://tapid.in/logo.png",
    handler: function(response) {
      alert("Payment successful! ID: " + response.razorpay_payment_id);
      // trigger download or redirect to dashboard
    },
    prefill: {
      name: document.getElementById('f_name').value,
      email: document.getElementById('f_email').value,
      contact: document.getElementById('f_phone').value,
    },
    theme: { color: "#FF6B00" }
  };

  const rzp = new Razorpay(options);
  rzp.open();
}
```

Also add the Razorpay SDK script before `</body>`:

```html
<script src="https://checkout.razorpay.com/v1/checkout.js"></script>
```

---

## 📂 Recommended Folder Structure (when scaling)

```
tapid/
├── index.html              ← This file (rename tapid-website.html)
├── assets/
│   ├── logo.png
│   ├── og-image.png        ← For WhatsApp/social sharing preview
│   └── favicon.ico
├── README.md               ← This file
└── .env                    ← Razorpay keys (never commit this)
```

---

## 🌍 Deployment (One-Click Options)

### Vercel
```bash
npm i -g vercel
vercel deploy
```

### Netlify
Drag and drop the `tapid-website.html` file at [app.netlify.com/drop](https://app.netlify.com/drop)

### Firebase Hosting
```bash
npm i -g firebase-tools
firebase init hosting
firebase deploy
```

---

## 📱 Responsive Breakpoints

| Breakpoint | Layout Changes |
|-----------|---------------|
| `> 900px` | Full desktop layout, 3-column card types grid, side-by-side builder |
| `≤ 900px` | Mobile layout, single column, nav links hidden, stacked sections |

---

## 🗺️ Roadmap (Phase 2 & 3 Features to Build)

- [ ] Backend API (Node.js + Supabase) for saving profiles
- [ ] User authentication (phone OTP via Supabase Auth)
- [ ] Dynamic profile URLs (`tapid.in/yourname`)
- [ ] Real QR code generation (linking to live profile)
- [ ] NFC card order management system
- [ ] Document vault (Aadhar, PAN, Resume upload)
- [ ] Lead capture CRM dashboard
- [ ] WhatsApp Business API integration
- [ ] Analytics dashboard (profile views, taps, leads)
- [ ] Mobile app (React Native)
- [ ] Telugu + Hindi language toggle
- [ ] DigiLocker / Aadhar API integration
- [ ] AI resume builder from profile data

---

## 👤 Target Users

| Persona | Use Case |
|---------|---------|
| Insurance Agent | Tap card → lead form → WhatsApp follow-up |
| Final Year Student | QR on printed resume → live portfolio |
| Real Estate Team | Team dashboard → central lead CRM |
| Freelance Designer | Portfolio + pricing + testimonials in one link |
| Small Business Owner | WhatsApp ordering link + product categories |

---

## 🏙️ Go-To-Market — Anantapur First

- Launch in 5 colleges in Anantapur district (JNTUA, SKU, etc.)
- Partner with LIC/HDFC agent associations for bulk signup
- Local WhatsApp group broadcasts
- Student ambassador program (₹500 per 10 referrals)
- Offline NFC demo at local trade exhibitions

---

## 📄 License

Private — Proprietary. All rights reserved.  
© 2025 TapID · tapid.in · Made in India 🇮🇳

---

## 📞 Contact

| Channel | Details |
|---------|---------|
| WhatsApp | +91 98765 43210 |
| Email | hello@tapid.in |
| Website | tapid.in |
| Location | Anantapur, Andhra Pradesh, India |

