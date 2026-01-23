---
date: '2026-01-23'
description: تعلم كيفية تقسيم رسومات CAD إلى بلاطات باستخدام GroupDocs.Viewer للغة
  Java، مما يتيح عرضًا أسرع وتكاملًا سهلاً في تطبيقاتك.
keywords:
- GroupDocs.Viewer Java
- split CAD drawings into tiles
- rendering large CAD files
title: تقسيم رسم CAD إلى بلاطات باستخدام GroupDocs.Viewer Java
type: docs
url: /ar/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# تقسيم رسومات CAD إلى بلاطات باستخدام GroupDocs.Viewer Java

## المقدمة
هل تواجه صعوبة في إدارة وعرض رسومات CAD الكبيرة بكفاءة في تطبيق Java الخاص بك؟ سيوضح هذا الدليل كيفية **تقسيم رسمة CAD** إلى بلاطات قابلة للإدارة باستخدام GroupDocs.Viewer for Java. من خلال تقسيم الرسمة إلى أقسام أصغر، يمكنك تحسين الأداء بشكل كبير وتسهيل التعامل معها.

## إجابات سريعة
- **ماذا يحقق تقسيم رسمة CAD؟** يقلل من حمل العرض عن طريق معالجة بلاطات صور أصغر بدلاً من معالجة الملف بالكامل مرة واحدة.  
- **ما المكتبة المطلوبة؟** GroupDocs.Viewer for Java (الإصدار 25.2 أو أحدث).  
- **هل أحتاج إلى ترخيص؟** يتوفر ترخيص تجريبي مجاني؛ يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج.  
- **هل يمكنني تخصيص حجم البلاطة؟** نعم، يمكنك تحديد أبعاد البلاطة لتناسب احتياجات الأداء والتفاصيل.  
- **هل هذا النهج مناسب لتطبيقات الويب أو الجوال؟** بالتأكيد – الصور المبلطة تُحمَّل أسرع وتستهلك نطاقًا أقل.

![تقسيم رسومات CAD باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

**ما ستتعلمه:**
- إعداد وتكوين GroupDocs.Viewer for Java.  
- عملية خطوة بخطوة لتقسيم بلاطات.  
- التكوينات الرئيسية وتقنيات التحسين.  
- التطبيقات العملية وإمكانيات التكامل.

لنبدأ بالتأكد من أن بيئتك جاهزة بالمتطلبات الأساسية اللازمة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- **المكتبات**: GroupDocs.Viewer for Java (الإصدار 25.2 أو أحدث).  
- **إعداد البيئة**: مجموعة تطوير Java (JDK) تعمل وبيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
- **المتطلبات المعرفية**: مهارات برمجة Java الأساسية ومعرفة بـ Maven.

## إعداد GroupDocs.Viewer for Java
لاستخدام GroupDocs.Viewer، أضفه كاعتماد في مشروعك. إذا كنت تستخدم Maven:

**تكوين Maven:**
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
يقدم GroupDocs.Viewer ترخيصًا تجريبيًا مجانيًا لاستكشاف جميع إمكاناته:
- **نسخة تجريبية مجانية**: زر [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) لتنزيل واختبار المكتبة.  
- **ترخيص مؤقت**: قدِّم طلبًا للحصول على ترخيص مؤقت عبر [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **شراء**: اشترِ ترخيصًا كاملاً من خلال [Purchase Page](https://purchase.groupdocs.com/buy).

### التهيئة الأساسية والإعداد
لتهيئة GroupDocs.Viewer في تطبيق Java الخاص بك:
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
بعد إكمال الإعداد، ننت إلى تنفيذ الميزة.

## كيفية تقسيم رسمة CAD إلى بلاطات
يوضح هذا القسم كيفية تقسيم رسمة CAD إلى بلاطات أصغر لتسهيل المعالجة والعرض بشكل أكثر كفاءة. كل بلاطة ستكون ربع حجم الأصل.

### الخطوة 1: تحديد مسار دليل الإخراج
ابدأ بتحديد مكان حفظ الصور التي تم عرضها:
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
يستخدم هذا الإعداد طريقة مساعدة للحصول على المسار، مما يضمن إمكانية إعادة الاستخدام والوضوح.

### الخطوة 2: تكوين خيارات العرض
قم بإعداد الخيارات لعرض كل قسم على حدة:
```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```
المقتطف يضبط عرض PNG دون معالجة جميع الصفحات مرة واحدة.

### الخطوة 3: حساب أبعاد البلاطة
حدد أبعاد كل بلاطة:
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

### الخطوة 4: عرض وحفظ البلاطات
أضف كل بلاطة محسوبة إلى خيارات العرض ثم قم بالعرض:
```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```
هذه الخطوة النهائية تعرض المستند بناءً على البلاطات المحددة، وتحفظ كل واحدة كملف PNG منفصل.

### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من أن مسار بناء المشروع يحتوي على ملفات JAR الخاصة بـ GroupDocs.Viewer.  
- تحقق من أن دليل الإخراج قابل للكتابة من قبل تطبيقك.  
- ابحث عن أي استثناءات أثناء العرض لتشخيص المشكلات المتعلقة بملفات الرسومات المحددة.

## التطبيقات العملية
يمكن أن يكون تقسيم رسومات CAD إلى بلاطات مفيد:
1. **رسم الخرائط على الويب** – تحميل مخططات معمارية كبيرة على خرائط الويب بكفاءة دون تحميل موارد الخادم.  
2. **أنظمة إدارة المستندات** – إدارة أسهل ووصول أسرع إلى أقسام محددة من الرسومات الكبيرة.  
3. **تطبيقات الجوال** – تحسين الأداء عن طريق عرض الأجزاء الضرورية فقط من الرسمة بناءً على تفاعل المستخدم.

## اعتبارات الأداء
لتحسين أداء تطبيقك:
- استخدم البلاطات بشكل استراتيجي لتحقيق توازن بين التفاصيل ووقت المعالجة.  
- راقب استهلاك الذاكرة، خاصةً عند التعامل مع رسومات كبيرة جدًا.  
- اعتمد أفضل ممارسات Java لإدارة الذاكرة بفعالية، مثل try‑with‑resources للتنظيف التلقائي.

## الخلاصة
لقد تعلمت الآن كيفية **تقسيم رسمة CAD** إلى بلاطات باستخدام GroupDocs.Viewer for Java. لا يحسن هذا النهج أداء العرض فحسب، بل يعزز أيضًا قابلية استخدام تطبيقك عند التعامل مع ملفات مستندات كبيرة.

**الخطوات التالية:**
- جرّب أحجام بلاطات مختلفة بناءً على حالات الاستخدام المحددة.  
- استكشف ميزات أخرى يقدمها GroupDocs.Viewer لتعزيز قدرات معالجة المستندات لديك.

هل أنت مستعد لتطبيق هذا الحل في مشروعك؟ جرّبه وشاهد تحسينات الأداء بنفسك!

## الأسئلة المتكررة

**س: ما هي بعض الأخطاء الشائعة عند استخدام GroupDocs.Viewer Java؟**  
ج: تشمل المشكلات الشائعة مسارات ملفات غير صحيحة، أذونات غير كافية على أدلة الإخراج، أو تبعيات مفقودة.

**س: هل يمكنني بكفاءة في للحفاظ على استهلاك الذاكرة ضمن نطاق معقول.

**س: هل يمكن تخصيص جودة الصورة الناتجة؟**  
ج: نعم، يتيح لك PNGViewOptions ضبط الدقة وإعدادات الضغط للتحكم في جودة الصورة.

**س: ماذا لو نفدت الذاكرة في تطبيقى أثناء العرض؟**  
ج: قلل أبعاد البلاطات، وزد حجم الذاكرة المخصصة للـ JVM (مثلاً `-Xmx2g`)، وتأكد من التخلص من كائنات Viewer بسرعة.

## الموارد
- [التوثيق](https://docs.groupdocs.com/viewer/java/)  
- [مرجع API](https://reference.groupdocs.com/viewer/java/)  
- [تحميل GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [شراء ترخيص](https://purchase.groupdocs.com/buy)  
- [نسخة تجريبية مجانية](https://releases.groupdocs.com/viewer/java/)  
- [ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)  
- [منتدى الدعم](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-01-23  
**تم الاختبار مع:** GroupDocs.Viewer Java 25.2  
**المؤلف:** GroupDocs