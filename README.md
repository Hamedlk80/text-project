# 🩺 Medical Chatbot NLP Pipeline

پروژه‌ای برای ساخت یک چت‌بات پردازش زبان طبیعی در حوزه پزشکی که وظیفه‌ی دریافت متن تبدیل‌شده از صوت پزشکان، استخراج اطلاعات مهم، خلاصه‌سازی و تبدیل خروجی به صوت را دارد.

---

## 📌 ویژگی‌ها

- دریافت متن پزشکی از مکالمات دکتر (خروجی Speech-to-Text)
- ترجمه اصطلاحات انگلیسی پزشکی به فارسی (در صورت وجود)
- خلاصه‌سازی خودکار جملات طولانی
- استخراج اطلاعات ساختاریافته از متن:
  - نام بیمار
  - سن (در صورت وجود)
  - تشخیص بیماری
  - لیست داروها با جزئیات (دوز، مدت مصرف، توضیحات)
- خروجی JSON با فرمت استاندارد
- تبدیل خروجی به صوت (TTS فارسی)
- قابل اجرا روی سیستم‌های معمولی (low-resource friendly)
- طراحی ماژولار با قابلیت توسعه آسان

---

## 📂 ساختار پروژه

<thead>
    <tr>
      <th>مسیر</th>
      <th>توضیحات</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>data/</code></td>
      <td>داده‌های ورودی و خروجی تست</td>
    </tr>
    <tr>
      <td><code>src/</code></td>
      <td>کدهای اصلی پروژه</td>
    </tr>
    <tr>
      <td><code>src/preprocessing/</code></td>
      <td>نرمال‌سازی و ترجمه اصطلاحات</td>
    </tr>
    <tr>
      <td><code>src/summarization/</code></td>
      <td>ماژول خلاصه‌سازی</td>
    </tr>
    <tr>
      <td><code>src/extraction/</code></td>
      <td>ماژول استخراج اطلاعات (NER/rule-based)</td>
    </tr>
    <tr>
      <td><code>src/tts/</code></td>
      <td>تبدیل متن به صوت</td>
    </tr>
    <tr>
      <td><code>src/main.py</code></td>
      <td>اجرای اصلی پروژه</td>
    </tr>
    <tr>
      <td><code>requirements.txt</code></td>
      <td>لیست کتابخانه‌ها</td>
    </tr>
    <tr>
      <td><code>.gitignore</code></td>
      <td>تنظیمات نادیده گرفتن فایل‌ها برای Git</td>
    </tr>
    <tr>
      <td><code>README.md</code></td>
      <td>فایل معرفی پروژه</td>
    </tr>
    <tr>
      <td><code>LICENS</code></td>
      <td>مجوز استفاده</td>
    </tr>
  </tbody>
</table>




⚙️ نصب و راه‌اندازی

# ایجاد محیط مجازی
python -m venv venv
source venv/bin/activate  # برای ویندوز: venv\Scripts\activate

# نصب وابستگی‌ها
pip install -r requirements.txt

🚀 اجرای پروژه

python src/main.py

🧪 تست

# بعد از اجرای main.py، می‌توانید یک فایل متنی پزشکی را تست کنید.
# مثال:
python src/main.py --input data/sample_note.txt

📤 فرمت خروجی

{
  "نام بیمار": "علی احمدی",
  "سن": "۴۵",
  "تشخیص": "فشار خون بالا",
  "داروها": [
    {
      "نام دارو": "لوزارتان",
      "دوز": "۵۰ میلی‌گرم",
      "تعداد دفعات": "روزی یک عدد",
      "مدت مصرف": "۳۰ روز"
    }
  ]
}

📚 وابستگی‌ها

    Python 3.8+

    Transformers

    spaCy / Hazm

    gTTS / Coqui TTS (برای خروجی صوت)

    Flask یا FastAPI (در صورت نیاز به API)

🛠 TODO

طراحی رابط کاربری

فاین‌تیون مدل‌های خلاصه‌سازی یا استخراج

استفاده از پایگاه داده برای ذخیره اطلاعات بیماران

پشتیبانی از چند کاربر همزمان (در نسخه API)
