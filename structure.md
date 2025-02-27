<div dir="rtl">

# بنية المجلد في لارافل 

- [مقدمة](#introduction)
- [المجلد الرئيسي](#the-root-directory)
    - [مجلد  `app` ](#the-root-app-directory)
    - [مجلد `bootstrap` ](#the-bootstrap-directory)
    - [مجلد `config` ](#the-config-directory)
    - [مجلد `database` ](#the-database-directory)
    - [مجلد `lang` ](#the-lang-directory)
    - [مجلد `public` ](#the-public-directory)
    - [مجلد `resources` ](#the-resources-directory)
    - [مجلد `routes` ](#the-routes-directory)
    - [مجلد `storage` ](#the-storage-directory)
    - [مجلد `tests` ](#the-tests-directory)
    - [مجلد `vendor` ](#the-vendor-directory)
- [مجلد `App` ](#the-app-directory)
    - [مجلد `Broadcasting` ](#the-broadcasting-directory)
    - [مجلد `Console` ](#the-console-directory)
    - [مجلد `Events` ](#the-events-directory)
    - [مجلد `Exceptions` ](#the-exceptions-directory)
    - [مجلد `Http` ](#the-http-directory)
    - [مجلد `Jobs` ](#the-jobs-directory)
    - [مجلد `Listeners` ](#the-listeners-directory)
    - [مجلد `Mail` ](#the-mail-directory)
    - [مجلد `Models` ](#the-models-directory)
    - [مجلد `Notifications` ](#the-notifications-directory)
    - [مجلد `Policies` ](#the-policies-directory)
    - [مجلد `Providers` ](#the-providers-directory)
    - [مجلد `Rules` ](#the-rules-directory)

<a name="introduction"></a>
## المقدمة 

توفر لارافل بنية افتراضية تسهل عليك بداية المشاريع سواء كانت مشاريع كبيرة أو مشاريع صغيرة,  وأيضا لديك الحرية بتنظيم ملفاتك بالشكل الذي تراه مناسباً.

لاتفرض لارفل أية قيد على مكان وجود أي صف Class  طالما أنه يتم تحميله بشكل تلقائي (Autoload ) عن طريق Composer 

<a name="the-root-directory"></a>
## المجلد الرئيسي root directory 

<a name="the-root-app-directory"></a>
#### أولا: مجلد التطبيق App 
مجلد التطبيق `app` يحوي الكود الرئيسي لتطبيقك (Core Code), سيتم توضيح هذا المجلد بشكل مفصل في الفقرات التالية.

ولكن بشكل عام يمكن القول أن هذا المجلد يحوي الصفوف (Classes) الخاصة بالمنطق في تطبيقك.


<a name="the-bootstrap-directory"></a>
####  مجلد الإقلاع Bootstrap 
يحوي هذا المجلد ملف `app.php` والذي يقوم بإقلاع إطار العمل لارافل, وأيضا يحتوي هذا المجلد على المجلد الفرعي `cache` والذي يحوي ملفات الذاكرة المخبئية التي يتم توليدها بشكل تلقائي من خلال اطار العمل لتحسين الأداء على سبيل المثال ملفات مخبئية تخص المسارات (Routes) أو ملفات مخبئية خاصة بالخدمات (Services).

بأغلب الحالات ومن المستحسن ألا تقوم بتعديل أي ملف ضمن هذا المجلد

<a name="the-config-directory"></a>
#### مجلد الإعدادات Config 

مجلد الاعدادات (config) كما يشير الاسم, يحوي جميع ملفات الاعدادات الخاصة بالتطبيق.

ومن المهم جدا الاطلاع على هذه الملفات بُغية معرفة كافة الخيارات المتاحة ضمنها والتغيير فيها عند الحاجة بحسب طبيعة التطبيق الخاص بك.

<a name="the-database-directory"></a>
#### مجلد قاعدة البيانات Database 

يحوي هذا المجلد ملفات ترحيل قاعدة البيانات (migrations), مصانع البيانات (Factories) وملفات (Seeds).

وأيضا يمكن استخدام هذا المجلد لتخزين قواعد البيانات من النوع SQLite.

<a name="the-lang-directory"></a>
#### مجلد اللغة Lang 

يحوي هذا المجلد جميع ملفات اللغة الخاصة بالتطبيق.

<a name="the-public-directory"></a>
#### المجلد العام Public 

يحوي هذا المجلد الملف `index.php` والذي يعتبر نقطة الانطلاق لجميع الطلبات الواردة للتطبيق ويضبط أيضا عملية التحميل التلقائي للصفوف (Classes Autoloading).

كما يستخدم هذا المجلد لتخزين ملفات الأصول (Assets) كالصور وملفات جافاسكريبت أو ملفات CSS.

<a name="the-resources-directory"></a>
#### مجلد الموارد Resources 
يحوي هذا المجلد  ملفات الواجهات [views](views.md) كما يحوي الملفات الخام, والغير مترجمة من ملفات جافاسكريبت أو CSS. 

<a name="the-routes-directory"></a>
#### مجلد المسارات Routes 
مجلد `routes` يحوي تعريف كل المسارات في التطبيق افتراضياً يوجد عدة ملفات ضمن هذا الملف وهي `web.php` و `api.php` و`console.php` و `channels.php`.

ملف `web.php` يحوي المسارات التي يصنفها `RouteServiceProvider` ضمن مجموعة البرمجيات الوسيطة(Middlewares) الخاصة بالـWeb, والتي تزود حالة الجلسة (Session State), حماية CSRF وتشفير ملفات تعريف الارتباط (Cookies). في حال كان تطبيقك لا يقدم خدمات عديمة الحالة Stateless أو RESTful APIs فإنه من الشائع جداً تعريف جميع المسارات الخاصة بالتطبيق في هذا الملف.

ملف `api.php` يحوي جميع  المسارات التي يصنفها RoutueServiceProvider ضمن مجموعة البرمجيات الوسيطة (Middlewares) الخاصة بالـAPI.
تكون هذه المسارات عديمة الحالة (Stateless) والذي يعني أن الطلبات الواردة للتطبيق لا تملك وصول لحالة الجلسة ويمكن مصادقتها (Authenticate) من خلال [ tokens](sanctum.md)  

ملف `console.php` هو الملف الذي يتم تعريف أوامر التحكم Console Commands والمعتمدة على Closures. 
كل منها يتم ربطه بأمر Command بحيث تقدم طريقة بسيطة للتفاعل الدخل والخرج الخاص بهذا الأمر.

يجب ملاحظة أن هذه المسارات في هذا الملف هي ليست مسارات HTTP وإنما هي مسارات يمكن التفاعل بها مع التطبيق من خلال Console.

ملف `channels.php` يتم تخزين جميع قنوات أحداث البث العام [event broadcasting](broadcasting.md) التي يدعمها تطبيقك. 

<a name="the-storage-directory"></a>
#### مجلد التخزين Storage 
مجلد التخزين `storage` يحوي جميع ملفات السجلات (logs), قوالب Blade المترجمة, ملفات الجلسات, ملفات الذاكرة المخبئية, والعديد من الملفات الأخرى التي يتم توليدها من قبل إطار العمل لارافل.
هذا المجلد مقسم الى المجلدات الفرعية التالية `app` و `framework` و `logs`.

مجلد `app` يستخدم لتخزين الملفات التي يولدها التطبيق

مجلد `framework` يستخدم لتخزين الملفات المولدة من قبل اطار العمل وملفات الذاكرة المخبئية.

وأخيرا مجلد `logs` يستخدم لتخزين السجلات الخاصة بتطبيقك كسجلات الطلبات أو سجلات الأخطاء وغيرها.

مجلد `storage/app/public` يستخدم لتخزينن الملفات التي يقوم المستخدم بتوليدها أو رفعها على سبيل المثال الصور الشخصية Avatars, يجب أن يكون هذا المجلد قابل للوصول بشكل عام Publicly Accessible من خلال اضافة وصلة رمزية Symbolic Link في `public/storage` تشير لهذا المجلد.

يمكن انشاء هذه الوصلة من خلال أمر Artisan التالي `php artisan storage:link`

<a name="the-tests-directory"></a>
#### The Tests Directory

The `tests` directory contains your automated tests. Example [PHPUnit](https://phpunit.de/) unit tests and feature tests are provided out of the box. Each test class should be suffixed with the word `Test`. You may run your tests using the `phpunit` or `php vendor/bin/phpunit` commands. Or, if you would like a more detailed and beautiful representation of your test results, you may run your tests using the `php artisan test` Artisan command.

<a name="the-vendor-directory"></a>
#### The Vendor Directory

The `vendor` directory contains your [Composer](https://getcomposer.org) dependencies.

<a name="the-app-directory"></a>
## The App Directory

The majority of your application is housed in the `app` directory. By default, this directory is namespaced under `App` and is autoloaded by Composer using the [PSR-4 autoloading standard](https://www.php-fig.org/psr/psr-4/).

The `app` directory contains a variety of additional directories such as `Console`, `Http`, and `Providers`. Think of the `Console` and `Http` directories as providing an API into the core of your application. The HTTP protocol and CLI are both mechanisms to interact with your application, but do not actually contain application logic. In other words, they are two ways of issuing commands to your application. The `Console` directory contains all of your Artisan commands, while the `Http` directory contains your controllers, middleware, and requests.

A variety of other directories will be generated inside the `app` directory as you use the `make` Artisan commands to generate classes. So, for example, the `app/Jobs` directory will not exist until you execute the `make:job` Artisan command to generate a job class.

> {tip} Many of the classes in the `app` directory can be generated by Artisan via commands. To review the available commands, run the `php artisan list make` command in your terminal.

<a name="the-broadcasting-directory"></a>
#### The Broadcasting Directory

The `Broadcasting` directory contains all of the broadcast channel classes for your application. These classes are generated using the `make:channel` command. This directory does not exist by default, but will be created for you when you create your first channel. To learn more about channels, check out the documentation on [event broadcasting](/docs/{{version}}/broadcasting).

<a name="the-console-directory"></a>
#### The Console Directory

The `Console` directory contains all of the custom Artisan commands for your application. These commands may be generated using the `make:command` command. This directory also houses your console kernel, which is where your custom Artisan commands are registered and your [scheduled tasks](/docs/{{version}}/scheduling) are defined.

<a name="the-events-directory"></a>
#### The Events Directory

This directory does not exist by default, but will be created for you by the `event:generate` and `make:event` Artisan commands. The `Events` directory houses [event classes](/docs/{{version}}/events). Events may be used to alert other parts of your application that a given action has occurred, providing a great deal of flexibility and decoupling.

<a name="the-exceptions-directory"></a>
#### The Exceptions Directory

The `Exceptions` directory contains your application's exception handler and is also a good place to place any exceptions thrown by your application. If you would like to customize how your exceptions are logged or rendered, you should modify the `Handler` class in this directory.

<a name="the-http-directory"></a>
#### The Http Directory

The `Http` directory contains your controllers, middleware, and form requests. Almost all of the logic to handle requests entering your application will be placed in this directory.

<a name="the-jobs-directory"></a>
#### The Jobs Directory

This directory does not exist by default, but will be created for you if you execute the `make:job` Artisan command. The `Jobs` directory houses the [queueable jobs](/docs/{{version}}/queues) for your application. Jobs may be queued by your application or run synchronously within the current request lifecycle. Jobs that run synchronously during the current request are sometimes referred to as "commands" since they are an implementation of the [command pattern](https://en.wikipedia.org/wiki/Command_pattern).

<a name="the-listeners-directory"></a>
#### The Listeners Directory

This directory does not exist by default, but will be created for you if you execute the `event:generate` or `make:listener` Artisan commands. The `Listeners` directory contains the classes that handle your [events](/docs/{{version}}/events). Event listeners receive an event instance and perform logic in response to the event being fired. For example, a `UserRegistered` event might be handled by a `SendWelcomeEmail` listener.

<a name="the-mail-directory"></a>
#### The Mail Directory

This directory does not exist by default, but will be created for you if you execute the `make:mail` Artisan command. The `Mail` directory contains all of your [classes that represent emails](/docs/{{version}}/mail) sent by your application. Mail objects allow you to encapsulate all of the logic of building an email in a single, simple class that may be sent using the `Mail::send` method.

<a name="the-models-directory"></a>
#### The Models Directory

The `Models` directory contains all of your [Eloquent model classes](/docs/{{version}}/eloquent). The Eloquent ORM included with Laravel provides a beautiful, simple ActiveRecord implementation for working with your database. Each database table has a corresponding "Model" which is used to interact with that table. Models allow you to query for data in your tables, as well as insert new records into the table.

<a name="the-notifications-directory"></a>
#### The Notifications Directory

This directory does not exist by default, but will be created for you if you execute the `make:notification` Artisan command. The `Notifications` directory contains all of the "transactional" [notifications](/docs/{{version}}/notifications) that are sent by your application, such as simple notifications about events that happen within your application. Laravel's notification feature abstracts sending notifications over a variety of drivers such as email, Slack, SMS, or stored in a database.

<a name="the-policies-directory"></a>
#### The Policies Directory

This directory does not exist by default, but will be created for you if you execute the `make:policy` Artisan command. The `Policies` directory contains the [authorization policy classes](/docs/{{version}}/authorization) for your application. Policies are used to determine if a user can perform a given action against a resource.

<a name="the-providers-directory"></a>
#### The Providers Directory

The `Providers` directory contains all of the [service providers](/docs/{{version}}/providers) for your application. Service providers bootstrap your application by binding services in the service container, registering events, or performing any other tasks to prepare your application for incoming requests.

In a fresh Laravel application, this directory will already contain several providers. You are free to add your own providers to this directory as needed.

<a name="the-rules-directory"></a>
#### The Rules Directory

This directory does not exist by default, but will be created for you if you execute the `make:rule` Artisan command. The `Rules` directory contains the custom validation rule objects for your application. Rules are used to encapsulate complicated validation logic in a simple object. For more information, check out the [validation documentation](/docs/{{version}}/validation).
</div>
