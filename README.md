# MK-for-YOu
npx create-react-app mk-for-you cd mk-for-you
npm install lucide-react
// File: src/App.js
import React, { useState } from "react";
import { ShoppingBag, Zap, Facebook, Phone } from "lucide-react";

export default function App() {
  const [lang, setLang] = useState("en");

  const text = {
    en: {
      title: "MK for You",
      subtitle: "Clothing & Electrical Accessories",
      shopNow: "Shop Now",
      clothing: "Clothing",
      electronics: "Electronics",
      aboutTitle: "About Us",
      aboutText:
        "MK for You offers a curated selection of clothing and electrical accessories at affordable prices. Our mission is to make your shopping experience simple and reliable.",
      paymentTitle: "Payment & Delivery",
      paymentText:
        "We accept KBZ Pay, Wave Pay, and online payments. Nationwide delivery available.",
      contactTitle: "Contact Us",
      contactText: "Order easily via WhatsApp, Messenger, or Phone.",
      language: "မြန်မာဘာသာသို့ ပြောင်းရန်",
    },
    mm: {
      title: "MK for You",
      subtitle: "အဝတ်အစားနှင့် လျှပ်စစ်ပစ္စည်းများ",
      shopNow: "စျေးဝယ်မည်",
      clothing: "အဝတ်အစားများ",
      electronics: "လျှပ်စစ်ပစ္စည်းများ",
      aboutTitle: "အကြောင်းအရာ",
      aboutText:
        "MK for You သည် စျေးနှုန်းသင့်ပြီး အရည်အသွေးမြင့် အဝတ်အစားများနှင့် လျှပ်စစ်ပစ္စည်းများကို ရှာဖွေနိုင်သော အွန်လိုင်းစတိုးအဖြစ် ဖွဲ့စည်းထားပါသည်။",
      paymentTitle: "ငွေပေးချေမှုနှင့် ပို့ဆောင်မှု",
      paymentText:
        "KBZ Pay၊ Wave Pay နှင့် အွန်လိုင်းငွေပေးချေမှုများကို လက်ခံပါသည်။ နယ်မြေအနှံ့ပို့ဆောင်ပါသည်။",
      contactTitle: "ဆက်သွယ်ရန်",
      contactText:
        "WhatsApp၊ Messenger သို့မဟုတ် ဖုန်းဖြင့် လွယ်ကူစွာ မှာယူနိုင်ပါသည်။",
      language: "Switch to English",
    },
  };

  const t = text[lang];

  return (
    <div className="min-h-screen bg-white text-gray-800">
      {/* Header */}
      <header className="flex justify-between items-center p-5 shadow-md">
        <h1 className="text-2xl font-bold">{t.title}</h1>
        <button
          onClick={() => setLang(lang === "en" ? "mm" : "en")}
          className="text-sm border rounded-full px-3 py-1 hover:bg-gray-100"
        >
          {t.language}
        </button>
      </header>

      {/* Hero Section */}
      <section className="text-center py-16 bg-gray-50">
        <h2 className="text-3xl font-semibold mb-2">{t.subtitle}</h2>
        <button className="mt-4 px-6 py-2 bg-black text-white rounded-full hover:bg-gray-800">
          {t.shopNow}
        </button>
      </section>

      {/* Products Section */}
      <section className="py-12 px-6">
        <h3 className="text-2xl font-semibold mb-6 flex items-center gap-2">
          <ShoppingBag size={24} /> {t.clothing}
        </h3>
        <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
          {[1, 2, 3, 4].map((i) => (
            <div
              key={i}
              className="border rounded-xl p-3 shadow-sm hover:shadow-md transition"
            >
              <div className="bg-gray-200 h-40 rounded-md mb-3"></div>
              <h4 className="font-medium">Product {i}</h4>
              <p className="text-sm text-gray-500">$00.00</p>
            </div>
          ))}
        </div>

        <h3 className="text-2xl font-semibold mt-12 mb-6 flex items-center gap-2">
          <Zap size={24} /> {t.electronics}
        </h3>
        <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
          {[1, 2, 3, 4].map((i) => (
            <div
              key={i}
              className="border rounded-xl p-3 shadow-sm hover:shadow-md transition"
            >
              <div className="bg-gray-200 h-40 rounded-md mb-3"></div>
              <h4 className="font-medium">Item {i}</h4>
              <p className="text-sm text-gray-500">$00.00</p>
            </div>
          ))}
        </div>
      </section>

      {/* About Section */}
      <section className="py-12 px-6 bg-gray-50">
        <h3 className="text-2xl font-semibold mb-4">{t.aboutTitle}</h3>
        <p className="max-w-3xl text-gray-600">{t.aboutText}</p>
      </section>

      {/* Payment Section */}
      <section className="py-12 px-6">
        <h3 className="text-2xl font-semibold mb-4">{t.paymentTitle}</h3>
        <p className="max-w-3xl text-gray-600">{t.paymentText}</p>
      </section>

      {/* Contact Section */}
      <section className="py-12 px-6 bg-gray-50">
        <h3 className="text-2xl font-semibold mb-4">{t.contactTitle}</h3>
        <p className="text-gray-600 mb-6">{t.contactText}</p>
        <div className="flex gap-4">
          <a
            href="https://m.me/"
            target="_blank"
            rel="noopener noreferrer"
            className="flex items-center gap-2 border px-4 py-2 rounded-full hover:bg-gray-100"
          >
            <Facebook size={18} /> Messenger
          </a>
          <a
            href="tel:+959"
            className="flex items-center gap-2 border px-4 py-2 rounded-full hover:bg-gray-100"
          >
            <Phone size={18} /> Call
          </a>
        </div>
      </section>

      {/* Footer */}
      <footer className="text-center py-6 border-t text-sm text-gray-500">
        © {new Date().getFullYear()} MK for You. All rights reserved.
      </footer>
    </div>
  );
}
