<div dir="rtl">

<p align="center">
  <img src="reverse-skill.png" alt="reverse-skill" width="120" />
</p>
<h1 align="center">reverse-skill — حزمة مهارات الأمن السيبراني والهندسة العكسية للوكلاء الأذكياء</h1>

<p align="center">
  🌍 <a href="README.md">English</a> · <a href="README_zh.md">中文</a> · <strong>العربية</strong>
</p>

> **هذه نسخة مضمَّنة داخل مستودع [rea](../../)** — المصدر الأصلي: [zhaoxuya520/reverse-skill](https://github.com/zhaoxuya520/reverse-skill) · الترخيص: [MIT](LICENSE)

---

## 💡 الفكرة باختصار

في الماضي كان إتقان الهندسة العكسية يستغرق **سنوات** من الخبرة العملية. أما اليوم، فيمكن لوكيل الذكاء الاصطناعي أن يتعلم **سير عمل الخبراء** من خلال حزمة مهارات واحدة منظمة.

زوِّد الوكيل بأي هدف — ملف **APK**، أو ملف **ثنائي (Binary)**، أو **برنامج ثابت (Firmware)**، أو كود **JavaScript مشوش** — وسيقوم تلقائيًا بتحديد:

- ← **الأداة** الصحيحة التي يجب استخدامها (jadx؟ IDA؟ Frida؟ radare2؟ BurpSuite؟)
- ← **المكان** الذي يجب التحقيق فيه أولًا
- ← **الخطوة التالية** التي يجب اتخاذها
- ← **كيفية توثيق** النتائج والأدلة بشكل احترافي

بدلًا من أن يخمّن الوكيل الأوامر، توجهه هذه الحزمة إلى **منهجية قابلة للتكرار** نفسها التي يتبعها المحترفون.

## 📊 الأرقام الحالية

| قواعد التوجيه | حالات الاختبار المرجعي | وحدات المهارات الأساسية | منصات CI | نموذج العميل |
|---:|---:|---:|---|---|
| 44 قاعدة (R0–R45) | 175 حالة | 45 وحدة | Windows + Ubuntu | محايد تجاه العميل |

أكثر من **43,000 نجمة** على GitHub — حزمة مجرَّبة من مجتمع الأمن السيبراني.

## 🗺️ كيف يعمل التوجيه؟

```
مهمة المستخدم
  → RULES.md (القواعد العامة + بوابة النطاق قبل أي إجراء)
  → MASTER-ROUTING (سلّم التوجيه الرئيسي السريع)
  → case-init / scope.md (تهيئة القضية: الصلاحيات + ملف الشبكة)
  → مهارة السيناريو المناسبة → الأدوات / خوادم MCP / السكربتات
  → الخط الزمني + سلسلة (الدليل ← النتيجة ← المسار) → التقرير + سجل الميدان
```

> 🤖 **إذا كنت وكيل ذكاء اصطناعي:** انتقل إلى [README_AI.md](README_AI.md) واتبع التعليمات بدقة.

## 🎯 السيناريوهات المدعومة

| السيناريو | نقطة الدخول |
|---|---|
| تحليل APK / أندرويد | `skills/apk-reverse/` |
| iOS / تطبيقات الجوال | `skills/mobile-reverse/` |
| الهندسة العكسية للملفات الثنائية (exe/dll/so/elf) | `skills/ida-reverse/` · `skills/radare2/` |
| Binary Ninja / HLIL / MLIL / MCP | `skills/binary-ninja-reverse/` |
| .NET / C# | `skills/dotnet-reverse/` |
| JavaScript الأمامية / المعاملات المشفرة | `skills/js-reverse/` |
| أجهزة DSL الافتراضية / تعليمات JS المخصصة | `skills/reverse-engineering/dsl-vm-reverse/` |
| التقاط HTTP / إعادة تشغيل الطلبات | anything-analyzer · Reqable MCP + `js-reverse/` |
| تحليل البرمجيات الخبيثة / YARA | `skills/malware-analysis/` |
| اختبار الاختراق / الفحص | `skills/pentest-tools/` |
| سلاسل الهجوم / التنسيق لفريق الأحمر | `skills/attack-chain/` |
| مراجعة أدلة القضية / تسليم التقارير | `skills/case-review/` |
| مسابقات CTF | `CTF-Sandbox-Orchestrator/` (42 مهارة فرعية) |
| الفيرموير / إنترنت الأشياء | `skills/firmware-pentest/` |
| مقارنة الرقع / ثغرات N-day | `skills/patch-diff-exploit/` |
| تطوير الاستغلال (Pwn) | `skills/pwn-chain/` |
| تجاوز EDR | `skills/edr-bypass-re/` |
| أمان API / GraphQL | `skills/api-security/` |
| أمان سلسلة التوريد / SBOM | `skills/supply-chain-security/` |
| أمان نماذج اللغة الكبيرة | `skills/llm-security/` |
| فك التشويش من OLLVM | `skills/reverse-engineering/references/ollvm-deobfuscation.md` |
| المخططات / التقارير | `skills/diagram-generator/` · `skills/docs-generator/` |

## 🚀 كيف تبدأ

### المتطلبات الأساسية

- **Java / JDK** — لأدوات jadx و apktool
- **Node.js 22.12+** — لسلسلة أدوات JS وخوادم MCP
- **Python 3.x** — لـ Frida والسكربتات المساعدة
- **عميل ذكاء اصطناعي برمجي** — Claude Code أو Codex أو Cursor أو OpenCode أو أي عميل متوافق

### التثبيت

انسخ هذا المجلد (`reverse-skill/`) إلى بيئة عملك، أو استنسخ المستودع الأصلي مباشرة:

```bash
git clone https://github.com/zhaoxuya520/reverse-skill.git
```

ثم حدِّث فهرس الأدوات حسب نظامك:

| النظام | الأمر |
|---|---|
| Windows | `powershell -File skills/scripts/refresh-tool-index.ps1` |
| Linux / macOS | `bash skills/scripts/refresh-tool-index.sh` |
| Kali Linux | `bash kali/scripts/refresh-tool-index.sh` |

تحقَّق من الأدوات المكتشَفة في [skills/tool-index.md](skills/tool-index.md).

### أدلة المنصات

- **Kali Linux** → [kali/README-kali.md](kali/README-kali.md)
- **Ubuntu/Debian** → [docs/platforms/linux.md](docs/platforms/linux.md)
- **macOS** → [docs/platforms/macos.md](docs/platforms/macos.md)

## 📂 الملفات الأساسية

| الملف | الوظيفة |
|---|---|
| [README_AI.md](README_AI.md) | تهيئة وكيل الذكاء الاصطناعي وإعداداته |
| [RULES.md](RULES.md) | قواعد التوجيه العامة (بوابة النطاق قبل التنفيذ) |
| [skills/MASTER-ROUTING.md](skills/MASTER-ROUTING.md) | سلّم التوجيه السريع الأساسي |
| [skills/routing.md](skills/routing.md) | مصفوفة توجيه (المهمة ← المهارة) |
| [skills/SKILL.md](skills/SKILL.md) | نقطة الدخول الرئيسية |
| [skills/INDEX.md](skills/INDEX.md) | فهرس تنقّل المهارات (مولَّد تلقائيًا) |
| [skills/config/routing.json](skills/config/routing.json) | المصدر الوحيد للحقيقة في التوجيه (43 قاعدة) |
| [skills/tool-index.md](skills/tool-index.md) | حالة الأدوات المحلية (مولَّد تلقائيًا) |
| [skills/scripts/master-route.ps1](skills/scripts/master-route.ps1) | الفرز الأولي الشامل (يقرأ routing.json) |
| [skills/scripts/case-init.ps1](skills/scripts/case-init.ps1) | مجلد القضية: النطاق / الخط الزمني / عناصر العمل |
| [skills/ops/](skills/ops/) | النطاق وسلسلة الأدلة والأدوار والخط الزمني |

## ⚖️ استخدام مسؤول

هذه الحزمة مخصصة **للأمن السيبراني المشروع والبحث المصرَّح به فقط**: اختبار الاختراق بموجب تفويض، تحليل البرمجيات الخبيثة الدفاعي، مسابقات CTF، وأبحاث الأمان. استخدمها فقط على الأنظمة التي تملك إذنًا صريحًا وخطيًا باختبارها. راجع [DISCLAIMER.md](DISCLAIMER.md) و[SECURITY.md](SECURITY.md) للتفاصيل.

## 📄 الترخيص

مشروع reverse-skill الأصلي منشور تحت ترخيص [MIT](LICENSE). هذه النسخة مضمَّنة مع الحفاظ على **كامل سجل الالتزامات (commits) الأصلي** احترامًا لمؤلفي المشروع.

- المصدر: <https://github.com/zhaoxuya520/reverse-skill>
- الموقع الرسمي: <https://reverse.apivix.com/>
- الدرس التعليمي: <https://reverse.apivix.com/docs/>

</div>
