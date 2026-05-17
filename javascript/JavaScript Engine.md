# 🔥 أول حاجة: إيه هو JavaScript Engine؟

**يوناس قال:**
> محرك JavaScript = برنامج يشغّل كود JavaScript

### أمثلة على Engines:

| المتصفح   | المحرك              |
|-----------|---------------------|
| Chrome    | **V8**              |
| Firefox   | **SpiderMonkey**    |
| Safari    | **JavaScriptCore**  |

---

### 🧠 أهم جزئين في الـ Engine

**1. Call Stack**  
المكان اللي **الكود بيتنفذ فيه** خطوة بخطوة.

**2. Heap**  
مخزن الذاكرة اللي بيحفظ فيه **الكائنات (Objects)** والمتغيرات.

---

### 🎯 مثال

```js
const user = {
  name: 'Moaaz'
};

الـ object بيتخزن في Heap
تنفيذ السطر بيحصل في Call Stack


🔥 Compilation vs Interpretation
1. Compilation
البرنامج كله يتحول لـ Machine Code مرة واحدة قبل التشغيل.
(مثل: C++ و Java)
2. Interpretation
الكود يتقرأ سطر سطر ويتنفذ مباشرة.
💥 قديمًا JavaScript كانت Interpreted فقط، وده كان بيخليها بطيئة.

🔥 JavaScript الحديثة: JIT Compilation
JIT = Just In Time Compilation
يعني الكود:

يتحلل
يتحول لـ Machine Code
يتنفذ فورًا

الخطوات بالترتيب:
#mermaid-diagram-mermaid-6mb14kp{font-family:"trebuchet ms",verdana,arial,sans-serif;font-size:16px;fill:#ccc;}@keyframes edge-animation-frame{from{stroke-dashoffset:0;}}@keyframes dash{to{stroke-dashoffset:0;}}#mermaid-diagram-mermaid-6mb14kp .edge-animation-slow{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 50s linear infinite;stroke-linecap:round;}#mermaid-diagram-mermaid-6mb14kp .edge-animation-fast{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 20s linear infinite;stroke-linecap:round;}#mermaid-diagram-mermaid-6mb14kp .error-icon{fill:#a44141;}#mermaid-diagram-mermaid-6mb14kp .error-text{fill:#ddd;stroke:#ddd;}#mermaid-diagram-mermaid-6mb14kp .edge-thickness-normal{stroke-width:1px;}#mermaid-diagram-mermaid-6mb14kp .edge-thickness-thick{stroke-width:3.5px;}#mermaid-diagram-mermaid-6mb14kp .edge-pattern-solid{stroke-dasharray:0;}#mermaid-diagram-mermaid-6mb14kp .edge-thickness-invisible{stroke-width:0;fill:none;}#mermaid-diagram-mermaid-6mb14kp .edge-pattern-dashed{stroke-dasharray:3;}#mermaid-diagram-mermaid-6mb14kp .edge-pattern-dotted{stroke-dasharray:2;}#mermaid-diagram-mermaid-6mb14kp .marker{fill:lightgrey;stroke:lightgrey;}#mermaid-diagram-mermaid-6mb14kp .marker.cross{stroke:lightgrey;}#mermaid-diagram-mermaid-6mb14kp svg{font-family:"trebuchet ms",verdana,arial,sans-serif;font-size:16px;}#mermaid-diagram-mermaid-6mb14kp p{margin:0;}#mermaid-diagram-mermaid-6mb14kp .label{font-family:"trebuchet ms",verdana,arial,sans-serif;color:#ccc;}#mermaid-diagram-mermaid-6mb14kp .cluster-label text{fill:#F9FFFE;}#mermaid-diagram-mermaid-6mb14kp .cluster-label span{color:#F9FFFE;}#mermaid-diagram-mermaid-6mb14kp .cluster-label span p{background-color:transparent;}#mermaid-diagram-mermaid-6mb14kp .label text,#mermaid-diagram-mermaid-6mb14kp span{fill:#ccc;color:#ccc;}#mermaid-diagram-mermaid-6mb14kp .node rect,#mermaid-diagram-mermaid-6mb14kp .node circle,#mermaid-diagram-mermaid-6mb14kp .node ellipse,#mermaid-diagram-mermaid-6mb14kp .node polygon,#mermaid-diagram-mermaid-6mb14kp .node path{fill:#1f2020;stroke:#ccc;stroke-width:1px;}#mermaid-diagram-mermaid-6mb14kp .rough-node .label text,#mermaid-diagram-mermaid-6mb14kp .node .label text,#mermaid-diagram-mermaid-6mb14kp .image-shape .label,#mermaid-diagram-mermaid-6mb14kp .icon-shape .label{text-anchor:middle;}#mermaid-diagram-mermaid-6mb14kp .node .katex path{fill:#000;stroke:#000;stroke-width:1px;}#mermaid-diagram-mermaid-6mb14kp .rough-node .label,#mermaid-diagram-mermaid-6mb14kp .node .label,#mermaid-diagram-mermaid-6mb14kp .image-shape .label,#mermaid-diagram-mermaid-6mb14kp .icon-shape .label{text-align:center;}#mermaid-diagram-mermaid-6mb14kp .node.clickable{cursor:pointer;}#mermaid-diagram-mermaid-6mb14kp .root .anchor path{fill:lightgrey!important;stroke-width:0;stroke:lightgrey;}#mermaid-diagram-mermaid-6mb14kp .arrowheadPath{fill:lightgrey;}#mermaid-diagram-mermaid-6mb14kp .edgePath .path{stroke:lightgrey;stroke-width:2.0px;}#mermaid-diagram-mermaid-6mb14kp .flowchart-link{stroke:lightgrey;fill:none;}#mermaid-diagram-mermaid-6mb14kp .edgeLabel{background-color:hsl(0, 0%, 34.4117647059%);text-align:center;}#mermaid-diagram-mermaid-6mb14kp .edgeLabel p{background-color:hsl(0, 0%, 34.4117647059%);}#mermaid-diagram-mermaid-6mb14kp .edgeLabel rect{opacity:0.5;background-color:hsl(0, 0%, 34.4117647059%);fill:hsl(0, 0%, 34.4117647059%);}#mermaid-diagram-mermaid-6mb14kp .labelBkg{background-color:rgba(87.75, 87.75, 87.75, 0.5);}#mermaid-diagram-mermaid-6mb14kp .cluster rect{fill:hsl(180, 1.5873015873%, 28.3529411765%);stroke:rgba(255, 255, 255, 0.25);stroke-width:1px;}#mermaid-diagram-mermaid-6mb14kp .cluster text{fill:#F9FFFE;}#mermaid-diagram-mermaid-6mb14kp .cluster span{color:#F9FFFE;}#mermaid-diagram-mermaid-6mb14kp div.mermaidTooltip{position:absolute;text-align:center;max-width:200px;padding:2px;font-family:"trebuchet ms",verdana,arial,sans-serif;font-size:12px;background:hsl(20, 1.5873015873%, 12.3529411765%);border:1px solid rgba(255, 255, 255, 0.25);border-radius:2px;pointer-events:none;z-index:100;}#mermaid-diagram-mermaid-6mb14kp .flowchartTitleText{text-anchor:middle;font-size:18px;fill:#ccc;}#mermaid-diagram-mermaid-6mb14kp rect.text{fill:none;stroke-width:0;}#mermaid-diagram-mermaid-6mb14kp .icon-shape,#mermaid-diagram-mermaid-6mb14kp .image-shape{background-color:hsl(0, 0%, 34.4117647059%);text-align:center;}#mermaid-diagram-mermaid-6mb14kp .icon-shape p,#mermaid-diagram-mermaid-6mb14kp .image-shape p{background-color:hsl(0, 0%, 34.4117647059%);padding:2px;}#mermaid-diagram-mermaid-6mb14kp .icon-shape rect,#mermaid-diagram-mermaid-6mb14kp .image-shape rect{opacity:0.5;background-color:hsl(0, 0%, 34.4117647059%);fill:hsl(0, 0%, 34.4117647059%);}#mermaid-diagram-mermaid-6mb14kp :root{--mermaid-font-family:"trebuchet ms",verdana,arial,sans-serif;}CodeParsingASTCompilationMachine CodeExecution

🔥 Parsing
المحرك يقرأ الكود ويفهمه.
مثال:
JavaScriptconst x = 23;
المحرك يعرف: const + x + = + 23

🔥 AST (Abstract Syntax Tree)
شجرة داخلية بتمثل الكود.
ملاحظة: AST ملهاش أي علاقة بالـ DOM Tree (يوناس أكد على النقطة دي).

🔥 Compilation & Execution

AST → Machine Code
الكود يتنفذ داخل Call Stack


🔥 Optimization
المحرك (خصوصًا V8):

يشغل نسخة سريعة أولية
يحسن الكود في الخلفية
يبدل النسخة المحسنة بدون توقف


🔥 Runtime
Runtime = البيئة الكاملة اللي JavaScript بتشتغل فيها.

























الجزءوظيفتهEngineتشغيل JavaScriptWeb APIsميزات المتصفحCallback Queueتخزين الـ CallbacksEvent Loopتنظيم التنفيذ

🔥 Web APIs
مش جزء من JavaScript، المتصفح بيوفرها.
أمثلة: setTimeout(), fetch(), DOM, console.log()

🔥 Event Loop (من أهم الأفكار)
شغلته:
ينقل الـ callbacks من الـ Queue للـ Call Stack لما الـ Stack يفضى.

🎯 مثال مهم
JavaScriptconsole.log('1');

setTimeout(() => {
  console.log('2');
}, 0);

console.log('3');
الناتج:
text1
3
2

🔥 Node.js Runtime

مفيش DOM
مفيش Browser Web APIs
بدالهم: C++ bindings + Thread Pool


🚀 أهم فكرة في المحاضرة
JavaScript مش مجرد لغة، دي نظام كامل متكون من:

Engine
Runtime
Event Loop
Memory (Heap + Call Stack)
JIT Compiler


🎯 أهم 5 مصطلحات لازم تحفظهم





























المصطلحمعناهEngineيشغل JSCall Stackتنفيذ الكودHeapتخزين الـ ObjectsEvent Loopإدارة الـ AsyncWeb APIsإمكانيات المتصفح
