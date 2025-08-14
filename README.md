import React, { useState } from "react";

export default function MadeByMeOnboarding() {
  const [step, setStep] = useState(1);
  const [formData, setFormData] = useState({
    email: "",
    password: "",
    plan: "",
    role: "",
    designerInfo: {
      productTypes: "",
      experience: "",
      tools: "",
    },
    marketerInfo: {
      channels: "",
      targetAudience: "",
      experience: "",
    },
    storeName: "",
    storeDescription: "",
    products: [],
  });

  const handleChange = (e) => {
    const { name, value } = e.target;

    // تحديث بيانات المصمم
    if (formData.role === "designer" && name in formData.designerInfo) {
      setFormData((prev) => ({
        ...prev,
        designerInfo: { ...prev.designerInfo, [name]: value },
      }));
    }
    // تحديث بيانات المسوق
    else if (formData.role === "marketer" && name in formData.marketerInfo) {
      setFormData((prev) => ({
        ...prev,
        marketerInfo: { ...prev.marketerInfo, [name]: value },
      }));
    }
    // تحديث باقي الحقول
    else {
      setFormData((prev) => ({ ...prev, [name]: value }));
    }
  };

  const nextStep = () => setStep((s) => Math.min(s + 1, 7));
  const prevStep = () => setStep((s) => Math.max(s - 1, 1));

  return (
    <div className="min-h-screen bg-gradient-to-tr from-indigo-400 via-purple-500 to-pink-500 flex items-center justify-center p-6">
      <div className="bg-white rounded-xl shadow-lg w-full max-w-2xl p-8">

        {/* الخطوة 1 */}
        {step === 1 && (
          <>
            <h2 className="text-3xl font-bold mb-6 text-purple-700">
              التسجيل في منصة MADE BY ME
            </h2>
            <input
              type="email"
              name="email"
              placeholder="البريد الإلكتروني"
              value={formData.email}
              onChange={handleChange}
              className="border rounded p-3 mb-4 w-full"
            />
            <input
              type="password"
              name="password"
              placeholder="كلمة المرور"
              value={formData.password}
              onChange={handleChange}
              className="border rounded p-3 mb-4 w-full"
            />
            <button
              disabled={!formData.email || !formData.password}
              onClick={nextStep}
              className="bg-purple-600 text-white py-3 px-6 rounded w-full disabled:opacity-50"
            >
              التالي
            </button>
          </>
        )}

        {/* الخطوة 2 */}
        {step === 2 && (
          <>
            <h2 className="text-3xl font-bold mb-6 text-purple-700">اختر خطتك</h2>
            <div className="space-y-4 text-lg">
              {[
                { value: "free", label: "التجربة المجانية - 15 يوم" },
                { value: "monthly", label: "الاشتراك الشهري - 9.99 دولار" },
                { value: "yearly", label: "الاشتراك السنوي - 29.99 دولار" },
              ].map((plan) => (
                <label
                  key={plan.value}
                  className={`block p-4 border rounded cursor-pointer ${
                    formData.plan === plan.value
                      ? "bg-purple-100 border-purple-500"
                      : ""
                  }`}
                >
                  <input
                    type="radio"
                    name="plan"
                    value={plan.value}
                    checked={formData.plan === plan.value}
                    onChange={handleChange}
                    className="mr-3"
                  />
                  {plan.label}
                </label>
              ))}
            </div>
            <div className="flex justify-between mt-8">
              <button onClick={prevStep} className="py-3 px-6 border rounded hover:bg-gray-100">
                عودة
              </button>
              <button
                disabled={!formData.plan}
                onClick={nextStep}
                className="bg-purple-600 text-white py-3 px-6 rounded disabled:opacity-50"
              >
                التالي
              </button>
            </div>
          </>
        )}

        {/* الخطوة 3 */}
        {step === 3 && (
          <>
            <h2 className="text-3xl font-bold mb-6 text-purple-700">هل أنت مصمم أم مسوّق؟</h2>
            <select
              name="role"
              value={formData.role}
              onChange={handleChange}
              className="border rounded p-3 w-full mb-6"
            >
              <option value="">اختر دورك</option>
              <option value="designer">مصمم</option>
              <option value="marketer">مسوّق</option>
            </select>

            {formData.role === "designer" &&
              Object.keys(formData.designerInfo).map((field) => (
                <input
                  key={field}
                  type="text"
                  name={field}
                  placeholder={
                    field === "productTypes"
                      ? "أنواع المنتجات التي تصممها"
                      : field === "experience"
                      ? "خبرتك في التصميم"
                      : "أدوات التصميم المفضلة (مثلاً Canva, Figma)"
                  }
                  value={formData.designerInfo[field]}
                  onChange={handleChange}
                  className="border rounded p-3 w-full mb-4"
                />
              ))}

            {formData.role === "marketer" &&
              Object.keys(formData.marketerInfo).map((field) => (
                <input
                  key={field}
                  type="text"
                  name={field}
                  placeholder={
                    field === "channels"
                      ? "قنوات التسويق (مثلاً Instagram, TikTok)"
                      : field === "targetAudience"
                      ? "الجمهور المستهدف"
                      : "خبرتك في التسويق"
                  }
                  value={formData.marketerInfo[field]}
                  onChange={handleChange}
                  className="border rounded p-3 w-full mb-4"
                />
              ))}

            <div className="flex justify-between mt-8">
              <button onClick={prevStep} className="py-3 px-6 border rounded hover:bg-gray-100">
                عودة
              </button>
              <button
                disabled={!formData.role}
                onClick={nextStep}
                className="bg-purple-600 text-white py-3 px-6 rounded disabled:opacity-50"
              >
                التالي
              </button>
            </div>
          </>
        )}

        {/* باقي الخطوات كما هي... */}
      </div>
    </div>
  );
}
