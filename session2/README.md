![](/blog/image.axd?picture=/extjs/sencha-cmd-hero.png)

همانطور که در انتهای [جلسه گذشته](/blog/post/setting-up-extjs-and-sencha-cmd) عنوان کردم برای اینکه توسعه نرم‌افزارها با Ext JS آسان تر شود باید ابزاری به نام Sencha CMD را نصب کنید. این نرم افزار برای ویندوزُ مکینتاش و لینوکس ارائه شده است.

> Sencha CMD ابزاری الزامی برای کار کردن با Ext JS نیست ولی استفاده از آن زندگی را راحت تر میکند ;-) بنابراین توصیه اکید میکنم این ابزار را حتما نصب کنید.

## Sencha CMD

Sencha CMD یک ابزار قدرتمند تحت command است (دستورات آن از طریق command-line قابل فراخوانی است). این ابزار با اتوماتیک سازی بسیاری از کارها توسعه و تولید محصول را بسیار سریع‌تر می‌کند. تعدادی از قابلیت‌های آن عبارتند از: scaffolding، مدیریت پکیج ها، کامپایلر JS، ساخت اسکریپت ها، کار با تم ها و ...

پیش از نصب Sencha CMD شما نیاز دارید JRE را نصب کنید. (البته همانطور که گفتم تمام آموزش ها برای Ext JS 6 می باشد ولی برای Ext JS 5 باید Ruby را هم نصب کنید)

## Java Runtime Environment یا JRE

برای اینکه چک کنید آیا جاوا روی سیستم شما نصب هست یا نه دستور زیر را در terminal (در مکینتاش) یا cmd (در ویندوز) اجرا کنید.

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">java -version</pre>

اگر جاوا به درستی روی سیستم شما نصب باشد پاسخی شبیه به این دریافت خواهید کرد (بسته به اینکه JRE یا JDK را نصب کرده باشید):

<span style="background-color: #ff99cc;">نکته:</span> JRE را میتوانید از سایت های ایرانی دانلود کنید چون سایت Oracle بر روی کاربران ایرانی بسته است.

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">java version "1.6.0_39"
Java(TM) SE Runtime Environment (build 1.6.0_39-b04)
Java HotSpot(TM) Client VM (build 20.14-b01, mixed mode, sharing)</pre>

اگر خطایی میبینید باید مسیر نصب جاوا را در PATH اضافه کنید.

> ناگفته نماند در حال حاضر میتوانید Sencha CMD را به همراه JRE به صورت یک پکیج از وب سایت sencha دانلود کنید.

## نصب Sencha CMD

الآن Sencha CMD را دانلود و نصب کنید. آدرس Sencha CMD در وب سایت شرکت sencha به قرار زیر است:

[https://www.sencha.com/products/sencha-cmd/](https://www.sencha.com/products/sencha-cmd/ "دانلود Sencha CMD")

پس از نصب مطمپن شوید که Sencha CMD به درستی نصب شده و در دسترس است برای این کار در terminal مکینتاش یا cmd وسندوز دستور زیر را اجرا کنید:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">sencha which</pre>

> ناگفته نماند در حال حاضر میتوانید Sencha CMD را به همراه JRE به صورت یک پکیج از وب سایت sencha دانلود کنید.

اگر به درستی نصب شده باشد شما باید در terminal یا cmd نتیجه ای مشابه زیر مشاهده نمایید:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">Sencha Cmd v6.0.2.14
C:/Users/armandar/bin/Sencha/Cmd/6.0.2.14/</pre>

اگر خطایی دریافت کردید شما باید Path مسیر نصب Sencha CMD را به PATH های سیستم اضافه کنید. در مکینتاش:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">export PATH=~/bin/Sencha/Cmd/6.0.0.92:$PAT</pre>

> در دستور بالا مسیر نصب Sencha CMD را در سیستم خود وارد کنید.

و در ویندوز:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">set PATH=%PATH%;C:\Sencha\Cmd\6.0.0.92</pre>

> در دستور بالا مسیر نصب Sencha CMD را در سیستم خود وارد کنید.

## ایجاد اولین نرم‌افزار Ext JS با استفاده از Sencha CMD

terminal (مکینتاش) یا command prompt (ویندوز) خود را باز کنید و دستور زیر را اجرا کنید:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">sencha generate app --ext ArmandarApp ./armandarapp</pre>

> با توجه به سرعت اینترنت در ایران بهتر است از این دستور فعلا استفاده نکنید. به این دلیل که با استفاده از این دستور کل پکیج Ext JS که حجم بالایی هم دارد شروع به دانلود می شود. توصیه میکنم Ext JS را جداگانه دانلود کرده و با استفاده از دستوراتی که در ادامه توضیح خواهم داد نرم‌افزار خود را ایجاد نمایید.

دستور بالا ساختار (scaffold) یک برنامه Ext JS را با نام ArmandarApp ایجاد کرده و  تمام فایل ها را در زیر فولدری به نام armandarapp کپی می‌کند.

توجه داشته باشید که دستور بالا نرم‌افزاری شامل هر دو تولکیت etxjs شامل modern و classic را ایجاد خواهد کرد. اگر شما فقط یکی از این تولکیت‌ها را به تنهایی می‌خواهید پس از عبارات modern-- یا classic--  را به دستور بالا اضافه کنید:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">sencha generate app --ext --modern ArmandarApp ./armandarapp</pre>

همانطور که گفتم با این دستور Ext JS6 به صورت اتوماتیک دانلود می شود، اگر این اتفاق نیفتاد یا اگر Ext JS 6 را جداگانه دانلود کرده اید از دستور زیر استفاده کنید:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">sencha -sdk /path/to/sdk generate app ArmandarApp /path/to/armandarapp</pre>

Sencha CMD از نسخه Ext JS 4.1.1a و Sencha touch 2.1 به بالا را پشتیبانی می‌کند. شما می توانید نسخه های مختلف sdk را در سیستم خود داشته باشید و با تمام آنها از طریق Sencha CMD کار کنید.

کدی که در مثال زیر آورده شده یه نرم‌افزار Ext JS6 با عنوان ArmandarAPP را در فولدر d:/projects/armandar/armandarapp تولید می‌کند.

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">sencha -sdk d:/ext/6.0.1/ generate app ArmandarApp  d:/projects/armandar/armandarapp</pre>

اکنون برای مشاهده نرم‌افزار تولید شده دستورات زیر را در terminal یا cmd وارد کنید:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">cd d:/projects/armandar/armandarapp
sencha app watch</pre>

در این زمان شما می بینید که Sencha CMD یک سری کارها را انجام داده، نتیجه آن را به شما نمایش می دهد، در پایان عملیات دو خط زیر را خواهید دید:

<pre class="brush:ps;auto-links:false;toolbar:false" contenteditable="false">[INF] Application available at http://localhost:1842
[INF] Waiting for changes...</pre>

عملیات watch منتظر هر نوع تغییر می ماند و به محض تغییر در کدها مرورگر را رفرش می کند تا کدهای جدید قابل نمایش باشد. اگر نرم افزار خود را از طریق آدرس پیش‌فرض [http://localhost:1842](http://localhost:1842) باز کنید تصویر مشابه زیر خواهید دید: ![](/blog/image.axd?picture=/extjs/ArmandarApp.png)

به صورت پیشفرض وقتی شما با مرورگر دسکتاپی خود به آدرس [http://localhost:1842](http://localhost:1842/) می روید نرم افزار به صورت اتوماتیک تشخیص داده و تولکیت classic را به شما نشان خواهد داد. برای مشاهده نسخه موبایل و تبلت یا تولکیت modern به انتهای آدرس خود ?profile=modern را اضافه کنید. نتیجه در نسخه موبایل به صورت زیر است: ![](blob:http%3A//armandar.com/6247fc91-02bd-495d-a6af-09ae9e7e3e2c)

محتویات فولدر ArmandarApp مشابه شکل زیر است. به زودی به بعضی از فایل های مهم آن نگاهی می اندازیم. نرم افزار شامل model، store و application.js می‌باشد. store را مجموعه ای از نمونه ها (instance ها)یی از مدل در نظر بگیرید. store اطلاعات را از طریق یک proxy خوانده و عملیاتهایی نظیر مرتب سازی، فیلتر کردن، صفحه بندی و غیره را برای شما فراهم می‌آورد. در آینده بیشتر درباره store صحبت خواهیم کرد. در اسکرین شات پایین فولدرهای modern و classic را ببینید. این فولدرها شامل کدهایی است که برای تولکیت های modern و classic نوشته شده اند. ![](/blog/image.axd?picture=/extjs/Scaffold.png)

شکل زیر محتویات فولدرهای classic و modern را نمایش می‌دهد. این فولدرها هر کدام شامل یک فولدر  src هستند که ظاهر برنامه در هر یک از toolkit های عنوان شده را مشخص می کنند در حقیقت view های مرنبط با هر تولکیت در این فولدرها قرار می‌گیرد. main.scss شامل style های مختص نمایش در مرورگرهای دستکتاپ و موبایل است. یک فولدر saas در ریشه قرار دارد که استایل های رایج برنامه در آن قرار می‌گیرد. SAAS یا Syntactically Awesome Stylesheets یک زبان برای نوشتن stylesheet است. از SAAS در Ext JS بسیار زیاد استفاده شده است. در آینده در رابطه با style ها و themeها در extjs به صورت مفصل توضیح خواهم داد. 

دقت کنید اینها کدهای sdk نیستند اینها کدهای نرم‌افزار شما هستند. اگر میخواهید کدهای sdk مربوط به تولکیت های modern و classic را ببینید به فولدر ext بروید. ![](/blog/image.axd?picture=/extjs/ModernClassicToolkit.png)

> در جلسه آینده در رابطه با MVC و تعدادی از فایلهایی که Sencha CMD در هنگام تولید نرم‌افزار ArmandarApp تولید کرده است صحبت خواهیم کرد.