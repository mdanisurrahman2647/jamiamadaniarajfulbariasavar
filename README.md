import { useState } from "react";

export default function Home() {
  const [name, setName] = useState("");
  const [message, setMessage] = useState("");

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    alert(`ধন্যবাদ, ${name}! আপনার মেসেজ পাঠানো হয়েছে।`);
    setName("");
    setMessage("");
  };

  return (
    <div className="min-h-screen bg-white text-gray-800 p-6">
      <header className="text-center mb-10">
        <h1 className="text-4xl font-bold">আল জামিয়াতুল মাদানিয়া</h1>
        <p className="text-lg">রাজ ফুলবাড়িয়া, সাভার, ঢাকা</p>
        <p className="text-sm mt-2 text-green-700">অনলাইনে আমাদের উপস্থিতিতে আপনাকে স্বাগতম!</p>
      </header>

      <section className="grid grid-cols-1 md:grid-cols-2 gap-6 mb-10">
        <div className="p-6 border rounded shadow">
          <h2 className="text-2xl font-semibold mb-2">আমাদের সম্পর্কে</h2>
          <p>
            আল জামিয়াতুল মাদানিয়া একটি স্বনামধন্য কওমি মাদ্রাসা, যা দীর্ঘদিন ধরে
            ইলমে নববী প্রচারে অগ্রণী ভূমিকা পালন করছে। এখানে হিফজ, কিতাব বিভাগ ও
            দাওরায়ে হাদীস পর্যন্ত দ্বীনি শিক্ষা প্রদান করা হয়।
          </p>
        </div>

        <div className="p-6 border rounded shadow">
          <h2 className="text-2xl font-semibold mb-2">শিক্ষা কার্যক্রম</h2>
          <ul className="list-disc list-inside">
            <li>হিফজুল কুরআন</li>
            <li>নূরানী ও নাজেরা বিভাগ</li>
            <li>ফযিলত ও দাওরায়ে হাদীস</li>
            <li>নিয়মিত তালীম ও তাকরার</li>
          </ul>
        </div>

        <div className="p-6 border rounded shadow">
          <h2 className="text-2xl font-semibold mb-2">ভর্তি তথ্য</h2>
          <p>
            প্রতিবছর শাওয়াল মাসে নতুন ছাত্র ভর্তি করা হয়। আগ্রহী অভিভাবক ও ছাত্রদের
            মাদ্রাসায় যোগাযোগ করতে অনুরোধ জানানো যাচ্ছে।
          </p>
        </div>

        <div className="p-6 border rounded shadow">
          <h2 className="text-2xl font-semibold mb-2">যোগাযোগ</h2>
          <p>ঠিকানা: রাজ ফুলবাড়িয়া, সাভার, ঢাকা</p>
          <p>মোবাইল: 01XXXXXXXXX</p>
          <p>ই-মেইল: madania@example.com</p>

          <form onSubmit={handleSubmit} className="mt-4 flex flex-col gap-3">
            <input
              type="text"
              placeholder="আপনার নাম"
              className="border px-3 py-2 rounded"
              value={name}
              onChange={(e) => setName(e.target.value)}
              required
            />
            <textarea
              placeholder="মেসেজ"
              className="border px-3 py-2 rounded"
              value={message}
              onChange={(e) => setMessage(e.target.value)}
              required
              rows={4}
            />
            <button
              type="submit"
              className="bg-green-700 text-white py-2 rounded hover:bg-green-800 transition"
            >
              পাঠান
            </button>
          </form>
        </div>
      </section>

      <footer className="text-center text-sm text-gray-500 mt-10">
        &copy; {new Date().getFullYear()} আল জামিয়াতুল মাদানিয়া. সর্বস্বত্ব সংরক্ষিত।
      </footer>
    </div>
  );
}