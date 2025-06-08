# Mlbb-Top-Up.-mn
Mlbb/diamond.mn
import React, { useState } from "react";

export default function MobileLegendsTopUp() { const [selectedPackage, setSelectedPackage] = useState(null); const [formData, setFormData] = useState({ userId: "", zoneId: "", email: "", phone: "", });

const packages = [ { id: 1, diamonds: 86, price: 3000 }, { id: 2, diamonds: 172, price: 6000 }, { id: 3, diamonds: 257, price: 9000 }, ];

const handleChange = (e) => { setFormData({ ...formData, [e.target.name]: e.target.value }); };

const handleSubmit = (e) => { e.preventDefault(); console.log("Захиалга:", { ...formData, selectedPackage, }); alert("Захиалга илгээгдлээ! Console-г шалгана уу."); };

return ( <div className="max-w-xl mx-auto p-4"> <h1 className="text-2xl font-bold mb-4">Mobile Legends Diamond Top-Up</h1>

<div className="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">
    {packages.map((pkg) => (
      <div
        key={pkg.id}
        className={`p-4 rounded-xl border cursor-pointer transition hover:shadow ${
          selectedPackage?.id === pkg.id
            ? "border-blue-500 bg-blue-50"
            : "border-gray-200"
        }`}
        onClick={() => setSelectedPackage(pkg)}
      >
        <p className="text-lg font-semibold">{pkg.diamonds} 💎</p>
        <p className="text-sm text-gray-500">{pkg.price.toLocaleString()}₮</p>
      </div>
    ))}
  </div>

  <form onSubmit={handleSubmit} className="space-y-4">
    <input
      name="userId"
      type="text"
      placeholder="User ID"
      value={formData.userId}
      onChange={handleChange}
      className="w-full p-2 border rounded-xl"
      required
    />
    <input
      name="zoneId"
      type="text"
      placeholder="Zone ID"
      value={formData.zoneId}

