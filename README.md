# مهارة فنّ الترجمة العربية
### (Arabic Translation Skill — Tarjama + فصحى)

**Arabic translation skill for AI agents** — translates English↔Arabic the way Enani taught: meaning before words, transformation before literalism, living Arabic usage before the dictionary. It diagnoses word, structure, idiom and style problems (`تم التوقيع من قبل` ← `وقّع`, `قام بزيارة` ← `زار`, `The agreement was signed by` ← `وقّع الوزيران`), and filters the result through the anti-العَرَنْجِيَّة rules of `arabic-writing-skill`. Works with Claude Code, Codex, Antigravity and VS Code agent harnesses.

🔗 **الموقع المرجعي (الدليل والألفاظ والتركيب والاصطلاح والشعر والنماذج): [specailm5.github.io/arabic-tarjama-skill](https://specailm5.github.io/arabic-tarjama-skill/)**

> مهارة برمجية ولغوية لوكلاء الذكاء الاصطناعي لترجمة النصوص بين العربية والإنجليزية على أصولها الفنية: الألفاظ والمجرّدات والمجسّدات والمختصرات، والتركيب والحال والتفضيل والأفعال مع الأدوات، وبناء الجملة والمبني للمجهول والتحميل، والصفات والإضافة، والتراكيب الاصطلاحية والصياغة، وترجمة الشعر والأمانة — مستندةً إلى كتاب **«فن الترجمة»** للدكتور **محمد عناني**، ومسنودة بأصول **مهارة الكتابة العربية الفصيحة ونبذ العَرَنْجِيَّة** (`arabic-writing-skill`) وتجربة **مهارة القصة** (`arabic-story-skill`) في الحوار ومستويات اللغة.

---

## 📖 ما هي المهارة؟

مهارة تُعلِّم الوكيل الذكي **صنعة الترجمة** (كيف تُنقل) و**لسانها** (كيف تُصاغ عربيةً فصيحة)، فتجمع بين ثلاثة أمور لا تتفرّق:

1. **التشخيص البنيوي**: أين تقع المشكلة؟ في الكلمة (مجرّدة/مجسّدة/مختصر) أم في العلاقة النحوية (حال/تفضيل/فعل + أداة) أم في الجملة (مجهول/تحميل/ترتيب) أم في العرف (مصطلح/تعبير/رطانة) أم في النص (شعر/أدب/صحافة)؟
2. **التحويل العربي**: إعادة بناء الجملة بحسب مقتضيات العربية — الفعل أولاً، والخبر قريباً، والمجهول المعلوم الفاعل إلى معلوم، والصفات المكدّسة موزّعة، والإضافة المثقلة مفكوكة.
3. **فلتر اللسان**: تمرير النص على قواعد `arabic-writing-skill` لنبذ التراكيب الإفرنجية المنقولة، فتستقيم الجملة عربيةً في بنائها وروحها لا في إعرابها وحده.

**القواعد الثلاث الحاكمة:**
> **المعنى قبل اللفظ، والتحويل قبل الحرفية، والعرف العربي المعاصر قبل القاموس.**

**والقاعدة الرابعة:**
> **«ليس على الترجمة سيد»** — لا مترجم ينجو من مشكلة، والحصيف من يسأل ويراجع.

---

## 📂 بنية المهارة ومكوناتها

```
arabic-tarjama-skill/
│
├── skills/arabic-tarjama-skill/          # المهارة (تركيب Agent Skills القياسي)
│   ├── SKILL.md                          # الدليل الأساسي (المنهج الكامل + قائمة التدقيق)
│   ├── references/                       # الملاحق المرجعية التفصيلية
│   │   ├── words_and_terms.md            # الألفاظ: المجرّدات والمجسّدات والمختصرات
│   │   ├── syntax_and_sentence.md        # التركيب: الحال والتفضيل والمجهول والصفات
│   │   ├── idioms_and_style.md           # المصطلح والتعبير والصياغة والرطانة
│   │   └── poetry_and_fidelity.md        # الشعر والإيقاع والصورة والأمانة
│   └── examples/
│       └── before_after_translations.md  # دراسات حالة كاملة قبل وبعد
│
├── docs/                                 # الموقع المرجعي الإلكتروني (GitHub Pages)
│
├── .agents/skills/arabic-tarjama-skill/  # مسار الاكتشاف التلقائي لبيئات Codex و Antigravity
│
└── .claude/skills/arabic-tarjama-skill/  # مسار الاكتشاف التلقائي لبيئة Claude Code
```

---

## 🚀 طرق التثبيت والاستخدام (Installation Guide)

### أولاً: التثبيت بأمر واحد عبر `npx` (الطريقة الأسرع — موصى به)

```bash
npx skills add specailm5/arabic-tarjama-skill -g -y
```

ولاختيار بيئات بعينها أو التثبيت داخل مشروع محدد:

```bash
npx skills add specailm5/arabic-tarjama-skill -a claude-code -a codex
npx skills add specailm5/arabic-tarjama-skill --skill arabic-tarjama-skill -g -y
```

### ثانياً: التثبيت العام (يدوياً)

#### لنظام Windows (PowerShell):
```powershell
$src = "skills\arabic-tarjama-skill"

# 1. Claude Code
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\arabic-tarjama-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.claude\skills\arabic-tarjama-skill\"

# 2. Codex / Agent Skills العامة
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills\arabic-tarjama-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.agents\skills\arabic-tarjama-skill\"

# 3. Google Antigravity / Gemini
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.gemini\config\skills\arabic-tarjama-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.gemini\config\skills\arabic-tarjama-skill\"
```

#### لنظام macOS / Linux (Bash):
```bash
src=skills/arabic-tarjama-skill
mkdir -p ~/.claude/skills/arabic-tarjama-skill && cp -r "$src/." ~/.claude/skills/arabic-tarjama-skill/
mkdir -p ~/.agents/skills/arabic-tarjama-skill && cp -r "$src/." ~/.agents/skills/arabic-tarjama-skill/
mkdir -p ~/.gemini/config/skills/arabic-tarjama-skill && cp -r "$src/." ~/.gemini/config/skills/arabic-tarjama-skill/
```

### ثالثاً: التثبيت المحلي داخل مشروع محدد (VS Code Workspace Harness)

انسخ مجلد `skills/arabic-tarjama-skill` داخل مجلد `.agents/skills/` أو `.claude/skills/` في جذر مشروعك، فيكتشف الوكيلُ المهارةَ عند الترجمة أو المراجعة.

---

## ⚡ كيف تعمل المهارة؟ (أوامر سريعة)

**خريطة التشخيص — أين المشكلة؟**

<table dir="rtl">
<thead>
<tr>
<th align="right">المستوى</th>
<th align="right">السؤال</th>
<th align="right">العلاج</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>الكلمة</strong></td>
<td>مجرّدة أم مجسّدة أم مختصر؟</td>
<td>السياق · التعريب · التوليد · الشرح</td>
</tr>
<tr>
<td><strong>العلاقة</strong></td>
<td>حال أم تفضيل أم فعل + أداة؟</td>
<td>المفعول المطلق · أفعل التفضيل · المعنى الوظيفي</td>
</tr>
<tr>
<td><strong>الجملة</strong></td>
<td>مجهولة أم محمّلة أم مؤخَّرة الخبر؟</td>
<td>معلوم · تفكيك · تقديم الخبر</td>
</tr>
<tr>
<td><strong>الوصف</strong></td>
<td>صفات مكدّسة أم إضافة مثقلة؟</td>
<td>«يراد فعل» · توزيع · جملة صلة</td>
</tr>
<tr>
<td><strong>العرف</strong></td>
<td>مصطلح بحت أم استعاري أم تلازم؟</td>
<td>معنى عام · مثيل/بديل · مقابل عرفي</td>
</tr>
</tbody>
</table>

**فلتر اللسان — تعريب النص:**

<table dir="rtl">
<thead>
<tr>
<th align="right">الترجمة العرنجية ❌</th>
<th align="right">الصواب العربي ✅</th>
<th align="right">العلة</th>
</tr>
</thead>
<tbody>
<tr>
<td>تم توقيع الاتفاقية من قِبل الوزيرين</td>
<td>وقّع الوزيران الاتفاقية</td>
<td>المجهول مع فاعل معلوم</td>
</tr>
<tr>
<td>قام بزيارة عمه</td>
<td>زار عمه</td>
<td>الاشتقاق المباشر</td>
</tr>
<tr>
<td>أعطى وعداً بالمساعدة</td>
<td>وعد بالمساعدة</td>
<td>نبذ الفعل المساعد</td>
</tr>
<tr>
<td>تم ذلك من خلال المفاوضات</td>
<td>تم ذلك بالمفاوضات</td>
<td><code>من خلال</code> للفُرجة الحقيقية</td>
</tr>
<tr>
<td>على صعيد الاقتصاد</td>
<td>في شأن الاقتصاد</td>
<td>الصعيد وجه الأرض</td>
</tr>
<tr>
<td>الموقف الأكثر صعوبة</td>
<td>أصعب المواقف</td>
<td>أفعل التفضيل المباشر</td>
</tr>
<tr>
<td>أريد هذا فقط</td>
<td>ما أريد إلا هذا</td>
<td>أسلوب الحصر والقصر</td>
</tr>
<tr>
<td>لعب دوراً محورياً</td>
<td>كان قطب الرحى</td>
<td>استعارة مسطّحة مستوردة</td>
</tr>
</tbody>
</table>

---

## 🧭 مكان المهارة في منظومة المهارات العربية

هذه المهارة هي **الحلقة الثالثة** في منظومة متكاملة:

| المهارة | مهمّتها | علاقتها بالترجمة |
| :--- | :--- | :--- |
| **`arabic-writing-skill`** | تحرير النص العربي من العَرَنْجِيَّة | فلتر اللسان بعد الترجمة |
| **`arabic-story-skill`** | صنعة القصة والحوار والشخصية | الحوار ومستويات اللغة ووجهة النظر |
| **`arabic-tarjama-skill`** | نقل المعنى بين اللغتين | الحلقة الجامعة: تشخيص ← تحويل ← صياغة ← تحرير |

**الترابط العملي:**
- الترجمة تبدأ من **المعنى**، والكتابة تُحكم **الصياغة**، والقصة تُضبط **النغمة والحوار**.
- المترجم يستدعي `arabic-writing-skill` في كل نصّ، ويستدعي `arabic-story-skill` إذا كان النص سردياً أو حوارياً أو شعرياً.
- لا تُستبدل مهارة بأخرى: الترجمة بلا فلتر تخرج عرنجية، والفلتر بلا ترجمة يحرّر نصاً لم يُنقل أصلاً.

### خريطة المراحل القادمة

- **المرحلة ٢ — سدّ الثغرات:** تحديد المهارات الناقصة في المنظومة (منها: التحرير والنقد الأدبي، الترجمة القانونية والعلمية المتخصصة، الترجمة الشفوية، تحقيق النصوص، الكتابة الأكاديمية، المحتوى الرقمي) واستخراج كل مهارة من كتابها المرجعي.
- **المرحلة ٣ — الربط والتكامل:** بناء «وكلاء مسار» (workflows) تستدعي المهارات الثلاث معاً، مثل: `فكرة → قصة → ترجمة → تحرير`، و`نص أجنبي → ترجمة → مراجعة لغوية → تقييم نقدي`، مع قوائم تدقيق مشتركة ومصطلحات موحّدة.

---

## 📚 المراجع والاعتماد

* كتاب **«فن الترجمة»**، للدكتور **محمد عناني** — سلسلة «أدبيات» بإشراف د. محمود علي مكي — الشركة المصرية العالمية للنشر/لونجمان — الطبعة الخامسة ٢٠٠٠ — ISBN 977-16-0476-7. والنسخة المتاحة على **أرشيف الإنترنت (Internet Archive)**: <https://archive.org/details/fann_al-tarjama>.
* **مهارة الكتابة العربية الفصيحة ونبذ العَرَنْجِيَّة** (`arabic-writing-skill`)، مستخلصة من كتاب «العَرَنْجِيَّة: بلغات أعجمية وألسن عربية» لأحمد الغامدي.
* **مهارة كتابة القصة العربية** (`arabic-story-skill`)، مستخلصة من كتاب «فن كتابة القصة» لحسين القباني.

> **إقرار بالفضل:** هذه المهارة صياغةٌ تعليميةٌ مستقلّةٌ لمبادئ كتاب «فن الترجمة» وأمثلته، مع نقل اقتباساتٍ وأمثلةٍ بإسنادها إلى مؤلفها. ولا يتضمّن المستودع نسخةً كاملةً من الكتاب (PDF أو نصّاً مفرَّغاً)، ولا يُغني عن الرجوع إلى الأصل.

---

## 📜 الترخيص (License)

هذه المهارة مفتوحة المصدر ومتاحة للاستخدام الشخصي والتجاري والبحثي لدعم الترجمة إلى العربية الفصيحة.
