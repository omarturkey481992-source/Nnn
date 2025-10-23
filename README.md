# VulnScanner-MVP

Minimal Vulnerability Scanner (MVP) — FastAPI backend that orchestrates Nmap and OWASP ZAP and produces a JSON report.

## المتطلبات
- Docker & docker-compose
- nmap مثبت داخل الحاوية الآن (لم يعد يحتاج تثبيت محلي على المضيف)
- تأكد من تشغيل Docker Engine وdocker-compose.
- Python 3.10+

## التشغيل (محلي باستخدام Docker Compose)

1. شغّل:
   ```bash
   docker-compose up --build
   ```
2. افتح الواجهة: http://localhost:8000
3. استخدم endpoint لبدء مسح (POST /scan) مع JSON: `{ "target": "https://example.com" }`

## ملاحظات
- OWASP ZAP يعمل كحاوية ويعرض API على المنفذ 8090.
- هذا MVP يوفّر سير عمل أساسي: nmap -> zap spider/scan -> تجميع النتائج -> حفظ JSON report.
- لا تستخدم المسح بدون إذن صريح.
