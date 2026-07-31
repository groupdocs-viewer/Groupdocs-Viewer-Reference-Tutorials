---
date: '2026-04-01'
description: تعلم كيفية تقسيم رسومات CAD إلى بلاطات باستخدام GroupDocs Viewer for
  Java، مما يعزز أداء العرض ويسهل التعامل مع الملفات الكبيرة.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: كيفية تقسيم رسومات CAD إلى بلاطات باستخدام GroupDocs Viewer
type: docs
url: /ar/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# كيفية تقسيم رسومات CAD إلى مربعات باستخدام GroupDocs Viewer

إذا كنت تتساءل **كيفية تقسيم CAD** إلى ملفات أصغر وأكثر قابلية للإدارة، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنستعرض الخطوات الدقيقة اللازمة لتقسيم رسومات CAD الكبيرة إلى مربعات باستخدام **GroupDocs Viewer for Java**. في النهاية ستحصل على حل جاهز للاستخدام يحسن سرعة العرض، يقلل استهلاك الذاكرة، ويسهل عرض الرسومات في تطبيقات الويب أو الجوال.

![تقسيم رسومات CAD باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## إجابات سريعة
- **ما الذي تحققه “تقسيم CAD”?** إنه يقسم رسمًا ضخمًا إلى صور أصغر (مربعات) تُحمَّل بسرعة أكبر وتستهلك ذاكرة أقل.  
- **ما الصيغة المستخدمة للمربعات؟** يتم إنشاء ملفات PNG بشكل افتراضي، لكن صيغًا أخرى مدعومة عبر خيارات Viewer.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يعمل للتطوير؛ يلزم ترخيص مدفوع للإنتاج.  
- **هل يمكنني تغيير حجم المربع؟** نعم – قم بضبط حسابات `tileWidth` و `tileHeight` لتناسب احتياجاتك.  
- **هل هذه الطريقة آمنة للخطوط المتعددة؟** إن عرض كل مربع في نسخة `Viewer` خاصة باستخدام try‑with‑resources آمن للتنفيذ المتوازي.

## ما هو “كيفية تقسيم CAD”؟
يشير تقسيم CAD إلى تقسيم رسم CAD واحد، غالبًا ما يكون ضخمًا، إلى عدة أقسام مستطيلة (مربعات). يتم عرض كل مربع بشكل مستقل، مما يتيح لك تحميل الأجزاء التي يحتاجها المستخدم فقط—مناسب لخرائط الويب، بوابات المستندات، وعارضات الجوال.

## لماذا نستخدم GroupDocs Viewer for Java؟
يوفر GroupDocs Viewer دعمًا جاهزًا لأكثر من 100 تنسيق ملف، بما في ذلك DWG وDXF وDWF. تتيح لك واجهة برمجة تطبيقات المربعات (tile API) تحديد الإحداثيات الدقيقة، بحيث يمكنك عرض المنطقة التي تهمك بالضبط دون معالجة الملف بالكامل أولاً. هذا يوفر دورات المعالج، يقلل استهلاك النطاق الترددي، ويقدم تجربة مستخدم أكثر سلاسة.

## المتطلبات المسبقة
- **المكتبات**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: أي مجموعة تطوير Java حديثة (Java 8+).  
- **IDE**: IntelliJ IDEA أو Eclipse أو أي بيئة تطوير متوافقة مع Java.  
- **أداة البناء**: Maven (تعمل أدوات بناء أخرى طالما تم إضافة الاعتماد).

## إعداد GroupDocs.Viewer for Java
أضف مستودع GroupDocs والاعتماد إلى ملف `pom.xml` الخاص بك:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### الحصول على الترخيص
GroupDocs.Viewer offers a free trial license for evaluation:

- **نسخة تجريبية مجانية**: زر [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) لتنزيل المكتبة.  
- **ترخيص مؤقت**: قدِّم طلبًا على [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **ترخيص كامل**: اشترِ ترخيص إنتاج على [Purchase Page](https://purchase.groupdocs.com/buy).

### التهيئة الأساسية
أنشئ نسخة `Viewer` بسيطة للتحقق من تحميل المكتبة بشكل صحيح:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## دليل خطوة بخطوة لتقسيم رسومات CAD إلى مربعات

### الخطوة 1: تعريف دليل الإخراج
سنخزن كل مربع كملف PNG منفصل. استخدام طريقة مساعدة يحافظ على منطق المسار نظيفًا وقابلًا لإعادة الاستخدام.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### الخطوة 2: تكوين خيارات العرض
حدد صيغة العرض إلى PNG وأخبر الـ Viewer بعدم تحميل كل صفحة مسبقًا (مما يوفر الذاكرة).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### الخطوة 3: حساب أبعاد المربعات
أولاً نحصل على العرض والارتفاع الأصليين للرسم، ثم نقسمه إلى أربعة أرباع متساوية.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### الخطوة 4: عرض وحفظ المربعات
أضف المربعات المحسوبة إلى خيارات العرض ودع `Viewer` يولد ملفات PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### نصائح استكشاف الأخطاء وإصلاحها
- **مسار البناء** – تأكد من وجود ملفات JAR الخاصة بـ GroupDocs في classpath.  
- **الأذونات** – يجب أن يكون مجلد الإخراج قابلًا للكتابة من قبل عملية Java.  
- **الاستثناءات** – إذا رأيت `ViewerException`، فتحقق مرة أخرى من أن ملف DWG غير تالف وأن الترخيص الصحيح مطبق.

## حالات الاستخدام الشائعة لتقسيم مربعات CAD
1. **خرائط الويب** – تحميل الجزء المرئي فقط من مخطط الطابق عندما يقوم المستخدم بالتمرير/التكبير.  
2. **إدارة المستندات** – تخزين كل مربع بشكل منفصل لتوليد معاينات أسرع.  
3. **العرض على الجوال** – تقليل استهلاك النطاق الترددي بتنزيل المربعات المطلوبة فقط للشاشة الحالية.

## اعتبارات الأداء
- **حجم المربع** – المربعات الأكبر تعني ملفات أقل لكن عرضًا أبطأ؛ ابحث عن التوازن بناءً على احتياجات واجهة المستخدم.  
- **مراقبة الذاكرة** – استخدم أدوات تحليل Java (مثل VisualVM) لمراقبة استهلاك الذاكرة عند معالجة رسومات ضخمة جدًا.  
- **تنظيف الموارد** – نمط try‑with‑resources الموضح أعلاه يحرر الموارد الأصلية تلقائيًا.

## الأسئلة المتكررة

**س: هل يمكنني تقسيم أنواع ملفات أخرى (PDF، صور) إلى مربعات باستخدام نفس النهج؟**  
**ج:** نعم. يدعم GroupDocs Viewer العديد من الصيغ؛ عليك فقط استخدام فئة الخيارات المقابلة (مثل `PdfViewOptions`).

**س: كيف يمكنني تغيير جودة الصورة الناتجة؟**  
**ج:** اضبط `viewOptions.setResolution(int dpi)` أو عيّن إعدادات الضغط على كائن `PngOptions`.

**س: تطبيقِي يستهلك كل الذاكرة عند معالجة ملفات DWG الكبيرة جدًا—ماذا أفعل؟**  
**ج:** قلل أبعاد المربعات، زد حجم ذاكرة JVM (`-Xmx`)، أو اعرض المربعات بشكل متسلسل في نسخ `Viewer` منفصلة.

**س: هل يمكن عرض المربعات بشكل غير متزامن؟**  
**ج:** بالتأكيد. غلف كل استدعاء عرض مربع في `CompletableFuture` أو استخدم خدمة تنفيذ لتوازي عبء العمل.

**س: هل أحتاج إلى ترخيص منفصل لكل مربع؟**  
**ج:** لا. ترخيص GroupDocs Viewer واحد صالح يغطي جميع عمليات العرض داخل تطبيقك.

## الموارد
- [التوثيق](https://docs.groupdocs.com/viewer/java/)
- [مرجع API](https://reference.groupdocs.com/viewer/java/)
- [تحميل GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [شراء ترخيص](https://purchase.groupdocs.com/buy)
- [نسخة تجريبية مجانية](https://releases.groupdocs.com/viewer/java/)
- [ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)
- [منتدى الدعم](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-04-01  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs