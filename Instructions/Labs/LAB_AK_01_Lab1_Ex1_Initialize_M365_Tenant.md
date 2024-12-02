## مستأجرو WWL - شروط الاستخدام

إذا تم تزويدك بحساب مستأجر كجزء من تقديم تدريب بقيادة مدرب، يرجى ملاحظة أن حساب المستأجر متاح لغرض دعم الأنشطة المعملية ضمن التدريب بقيادة المدرب. 

يجب عدم مشاركة حسابات المستأجر أو استخدامها لأغراض خارج الأنشطة المعملية. حساب المستأجر المستخدم في هذه الدورة التدريبية هو حساب مستأجر تجريبي، ولا يجوز استخدامه أو الوصول إليه بعد انتهاء الفصل وهو غير مؤهل للتمديد. 

يجب عدم تحويل حسابات المستأجر إلى اشتراك مدفوع. تظل حسابات المستأجر التي تم الحصول عليها كجزء من هذه الدورة التدريبية ملكًا لشركة Microsoft Corporation ونحتفظ بالحق في الوصول إليها واستعادة ملكيتها في أي وقت. 

# مسار التعليم 1 - النشاط العملي 1 - التدريب 1 - تهيئة مستأجر Microsoft 365 الخاص بك 

شركة Adatum هي شركة تابعة لشركة Contoso Electronics. تقوم Adatum بتشغيل تطبيقاتها القديمة (مثل Microsoft Exchange Server 2019) في توزيع محلي. ومع ذلك، فقد اشتركت مؤخرًا في Microsoft 365، مما أدى إلى إنشاء توزيع هجين يتعين عليه فيه مزامنة عمليات التوزيع المحلية والسحابية. 

بصفتك مسؤول Microsoft 365 في Adatum، تم تكليفك بتوزيع Microsoft 365 في التوزيع الهجين الخاص بـ Adatum باستخدام بيئة نشاط عملي افتراضية. في هذا التمرين، ستقوم بإعداد مستأجر الإصدار التجريبي من Microsoft 365 الخاص بـ Adatum، وسيرشدك المعلم حول كيفية الحصول على بيانات اعتماد Microsoft 365 في بيئة النشاط العملي المستضاف لديك. ستستخدم بيانات الاعتماد هذه في جميع أنحاء الأنشطة العملية المتبقية في هذه الدورة التدريبية. 

في بيئة نشاطك العملي، حصل موفر استضافة النشاط العملي بالفعل على مستأجر تجريبي Microsoft 365 لك. لقد أنشأ موفر نشاطك العملي أيضًا حسابين إداريين ستستخدمهما في بيئة الجهاز الظاهري لنشاطك العملي. 

- حساب مسؤول محلي لبيئة Adatum المحلية (Adatum\Administrator).
- حساب مسؤول مستأجر افتراضي في Microsoft 365 (الاسم المعروض لحساب المستخدم هذا هو مسؤول MOD). 

ستقوم بتسجيل الدخول إلى الحاسوب الشخصي للعميل 1 (LON-CL1) باستخدام حساب Adatum\Administrator المحلي. عند وصولك إلى Microsoft 365 لأول مرة، ستقوم في البداية بتسجيل الدخول باستخدام حساب مسؤول المستأجر في Microsoft 365 (مسؤول MOD). ستقوم بعد ذلك بإعداد مستأجر Microsoft 365 الخاص بـ Adatum لمُعرّف Microsoft Entra والأنشطة العملية اللاحقة باستخدام تنبيهات التدقيق و Microsoft Graph PowerShell.


### المهمة 1- إعداد ملف تعريف مؤسسة Adatum

خلال الأنشطة العملية في هذه الدورة، ستلعب دورًا من خلال تولي شخصية هولي ديكسون ، مسؤولة Microsoft 365 في Adatum. باعتبارك هولي، تم تكليفك بإعداد ملف تعريف الشركة لمستأجر النسخة التجريبية من Microsoft 365. في هذه المهمة، ستقوم بتكوين الخيارات المطلوبة لمستأجر Adatum. نظرًا لأن هولي لم تقم بعد بإنشاء حساب مستخدم Microsoft 365 شخصي لنفسها (ستفعل ذلك في تمرين النشاط العملي التالي)، فستقوم هولي في البداية بتسجيل الدخول إلى Microsoft 365 باستخدام حساب مسؤول المستأجر الافتراضي لـ Microsoft 365 وكلمة المرور التي تم إنشاؤها بواسطة موفر استضافة نشاطك العملي. هذا الحساب هو حساب مسؤول MOD، واسمه المستعار هو "admin". اسم المستخدم لهذا الحساب هو admin@xxxxxZZZZZZ.onmicrosoft.com (حيث xxxxxZZZZZZ هو بادئة المستأجر المعينة من قبل موفر استضافة نشاطك العملي)؛ سيكون اسم العرض لهذا الحساب هو مسؤول MOD.

1. سيقوم موفر استضافة نشاطك العملي بتزويدك بكلمتي مرور يتم استخدامهما مع حسابات المستخدم الوهمية في مستأجر تجربة Microsoft 365 الخاص بك. تم تعيين **كلمة المرور الإدارية** لحساب مسؤول MOD، وهو مسؤول المستأجر الافتراضي. تم تعيين **كلمة مرور المستخدم** لجميع المستخدمين الآخرين - حتى أولئك الذين تم تعيين دور المسؤول لهم. <br>

    لأغراض أمنية، قامت Microsoft بتكوين المستأجر التجريبي الخاص بك بحيث يتعين على جميع المستخدمين المحددين مسبقًا تغيير كلمة المرور الخاصة بهم عند تسجيل الدخول التالي. قد يوفر بعض موفري استضافة الأنشطة العملية حقلين جديدين لكلمة المرور، أحدهما للمسؤولين (في الواقع، مسؤول MOD وهولي ديكسون) والآخر لجميع المستخدمين الآخرين. إذا ظهر هذان الحقلان الخاصان بكلمة المرور الجديدة في جهازك الظاهري، فأدخل كلمة مرور جديدة لكل منهما. سيتم تخزين قيم كلمة المرور الجديدة هذه في الجهاز الظاهري وعرضها في تعليمات النشاط العملي. <br>
 
    قد لا يوفر موفرو استضافة الأنشطة العملية الآخرون حقول كلمة المرور الجديدة هذه. بالنسبة لهذه البيئات، يجب عليك كتابة كلمة المرور الجديدة يدويًا والتي تخطط لتعيينها للمستخدمين الذين يقومون بتسجيل الدخول. <br>

    عند تصميم كلمات المرور الجديدة، ضع في اعتبارك إرشادات كلمة المرور الخاصة بـ Microsoft: <br>

    - 8 أحرف كحد أدنى، مع ما لا يقل عن:
       - حرف كبير واحد
       - حرف صغير واحد
       - حرف خاص واحد لن يتم التحقق من صحة كلمات المرور وفقًا لمتطلبات Microsoft حتى تقوم بتغيير كلمة المرور القديمة عند تسجيل الدخول التالي للمستخدم.

2. عند فتح بيئة الجهاز الظاهري لموفر استضافة نشاطك العملي، يتعين عليك البدء بالجهاز الظاهري للعميل1 (LON-CL1). إذا تم فتح بيئة جهازك الظاهري باستخدام أحد الأجهزة الأخرى (مثل LON-DC1)، فبدّل إلى **LON-CL1** الآن.

3. سجّل الدخول إلى **LON-CL1** باعتبارك حساب **المسؤول** المحلي الذي تم إنشاؤه بواسطة موفر استضافة نشاطك العملي باستخدام كلمة المرور **Pa55w.rd**. 

4. في شريط المهام الموجود أسفل الشاشة، حدد أيقونة **Microsoft Edge**. إذا لزم الأمر، كبّر نافذة المتصفح عند فتحها.

5. في متصفحك Edge، انتقل إلى صفحة **الصفحة الرئيسية لـ Microsoft 365** عن طريق إدخال عنوان URL التالي في شريط العناوين: **https://portal.office.com** 

6. في مربع الحوار **تسجيل الدخول**، أدخل **اسم المستخدم الإداري** المقدم من موفر استضافة نشاطك العملي (هذا هو حساب مسؤول MOD) لمستأجر نسخة Microsoft 365 التجريبية الخاصة بك. يجب أن يكون اسم المستخدم بصيغة **admin@xxxxxZZZZZZ.onmicrosoft.com**، حيث xxxxxZZZZZZ هو بادئة المستأجر المعينة من قبل موفر استضافة نشاطك العملي. حدد **التالي**. <br/>

    **ملاحظة:** في تعليمات النشاط العملي التي تظهر في بيئة الجهاز الظاهري لنشاطك العملي، قد يوفر لك موفر استضافة النشاط العملي القدرة على تحديد زر **نوع النص** (أو ما يعادله) بجوار بيانات الموارد مثل أسماء المستخدمين وكلمات المرور وأوامر PowerShell والبيانات الأخرى التي يجب إدخالها طوال فترة هذه الأنشطة العملية. قد يوفر موفرو استضافة الأنشطة العملية الآخرون طريقة بديلة، مثل القدرة على نسخ ولصق هذه المعلومات. استفد من هذه الوظيفة لتجنب الحاجة إلى إدخال هذه المعلومات يدويًا. 

7. في مربع الحوار **إدخال كلمة المرور**، أدخل **كلمة المرور الإدارية** المحددة مسبقًا والتي قدمها لك موفر استضافة نشاطك العملي، ثم حدد **تسجيل الدخول**. 

8. من المحتمل أن يكون موفر استضافة نشاطك العملي قد قام أو لم يقم بتكوين حساب مسؤول MOD بحيث يتطلب كلمة مرور جديدة عند تسجيل الدخول. إذا فعلوا ذلك، فسيظهر مربع الحوار **تحديث كلمة المرور الخاصة بك**. إذا حدث هذا، أدخل **كلمة المرور الإدارية** المقدمة من موفر استضافة نشاطك العملي في حقل **كلمة المرور الحالية**، ثم أدخل كلمة المرور الإدارية الجديدة في حقلي **كلمة المرور الجديدة** و**تأكيد كلمة المرور** وحدد **تسجيل الدخول**.

9. إذا ظهر مربع الحوار **هل تريد البقاء مسجلًا الدخول؟**، فحدد خانة الاختيار **عدم إظهار هذا مرة أخرى**، ثم حدد **نعم.** 

10. إذا ظهر مربع الحوار **مرحبًا بك في Microsoft 365** في منتصف الشاشة، فلن يكون هناك خيار لإغلاقه. بدلًا من ذلك، على يمين النافذة، حدد أيقونة السهم للأمام (**>**) مرتين، ثم حدد أيقونة علامة الاختيار للتقدم عبر الشرائح في نافذة الرسائل هذه. 

11. إذا ظهر مربع الحوار **البحث عن المزيد من التطبيقات** أو مربع الحوار **إنشاء باستخدام Microsoft 365**، فحدد **X** في الزاوية العلوية من المربعات لإغلاقها. على نحو مماثل، إذا ظهر مربع الحوار تسجيل الدخول إلى Microsoft Edge، حدد الزر **لا شكرًا**.

12. تظهر صفحة **مرحبًا بك في Microsoft 365**في متصفحك Edge في علامة التبويب**الصفحة الرئيسية | Microsoft 365**. هذه هي الصفحة الرئيسية لمسؤول MOD في Microsoft 365. <br/>

    لاحظ ظهور أيقونة أو دائرة تحتوي على "MA" (الأحرف الأولى لـ MOD Administrator) في الزاوية العلوية اليمنى من الشاشة. يعرض بعض مستأجري التجارب أيقونة؛ بينما يعرض البعض الآخر الأحرف الأولى من "MA" داخل دائرة؛ ويعتمد الأمر كله على ما إذا كان موفر استضافة نشاطك العملي قد أضاف أيقونة إلى حساب مسؤول MOD. تمثل الأيقونة أو الأحرف الأولى حساب **مسؤول MOD**، وهو حساب مسؤول المستأجر الذي أنشأه موفر استضافة نشاطك العملي الذي قمت بتسجيل الدخول به للتو. إذا كان أي من حسابات مستخدمي Microsoft 365 الموجودة التي تم إنشاؤها بواسطة موفر استضافة نشاطك العملي تحتوي على صورة مرتبطة بحسابها، فسيتم عرض صورة المستخدم بدلًا من الأحرف الأولى من اسمه عند تسجيل الدخول إلى Microsoft 365 باعتبارك هذا المستخدم. ومع ذلك، عندما لا يكون لدى مستخدم مثل مسؤول MOD صورة معينة له، فسيتم عرض الأحرف الأولى من اسم المستخدم بدلًا من الصورة، أو يتم عرض أيقونة إذا تم تعيين أيقونة للحساب بواسطة موفر استضافة نشاطك العملي. <br/>

    في صفحة **مرحبًا بك في Microsoft 365**، في قائمة أيقونات التطبيق التي تظهر في جزء التنقل، حدد **المسؤول**؛ سيؤدي هذا إلى فتح **مركز إدارة Microsoft 365** في علامة تبويب جديدة للمتصفح. 

13. في **مركز إدارة Microsoft 365**، حدد **إظهار الكل** في جزء التنقل، ثم حدد **الإعدادات**. في المجموعة **الإعدادات**، حدد **إعدادات المؤسسة**. 

14. في صفحة **إعدادات المؤسسة**، يتم عرض علامة التبويب **الخدمات** بشكل افتراضي. حدد علامة التبويب **ملف تعريف المؤسسة**.

15. في علامة التبويب **ملف تعريف المؤسسة**، حدد **معلومات المؤسسة** من قائمة بيانات الملف الشخصي.

16. في جزء **معلومات المؤسسة** الذي يظهر، أدخل المعلومات التالية: <br/>

    - الاسم: **Adatum Corporation** (ملاحظة: Adatum Corporation هي شركة تابعة لشركة Contoso Inc. قد يكون مستأجر الإصدار التجريبي من Microsoft الذي حصل عليه موفر استضافة نشاطك العملي لهذا النشاط العملي قد تم تعيينه في الأصل إلى Contoso. إذا ظهرت **Contoso** (أو أي قيمة أخرى) كاسم المؤسسة، فقم بتغييره إلى **Adatum Corporation**.

    - عنوان الشارع: **555 الشارع الرئيسي**

    - المدينة: **ريدموند**

    - الولاية أو المقاطعة: **واشنطن**

    - الرمز البريدي: **98052**

    - الهاتف: لا يتغير

    - جهة الاتصال الفنية: لا تتغير

    - اللغة المفضلة: **الإنجليزية**

17. حدد **حفظ**.

18. في الجزء العلوي من جزء **معلومات المؤسسة**، لاحظ الرسالة التي تشير إلى أنه تم حفظ التغييرات. حدد **X** في الجزء العلوي الأيمن من الجزء لإغلاقه.

19. ابق مسجلًا الدخول إلى **LON-CL1** مع فتح Microsoft Edge على **مركز مسؤولي Microsoft 365** للمهمة التالية.

### المهمة 2- إنشاء نسق مخصص لفريق المشروع التجريبي لـ Adatum

في المهمة السابقة، تعلمت أنه عندما يقوم شخص ما بتسجيل الدخول إلى Microsoft 365، سيعرض النظام إما صورته (إذا تم توفير صورة)، أو الأحرف الأولى من اسمه إذا لم يتم توفير أي صورة. لا تكتفي هولي ديكسون، مسؤولة Microsoft 365 في Adatum، برؤية صورة أو الأحرف الأولى من اسم المستخدم الذي قام بتسجيل الدخول. تريد إنشاء نسق مخصص لأعضاء فريق مشروعها التجريبي بحيث تعرض أيضًا اسم المستخدم الذي قام بتسجيل الدخول. في نهاية المشروع التجريبي، إذا فضل أعضاء فريق المشروع التجريبي هذا التصميم، فسوف تقوم بتكوين نفس هذا الخيار في النسق الافتراضي بحيث ينطبق على جميع المستخدمين. 

يجب أن تكون النسق المخصصة مقترنة بمجموعة واحدة أو أكثر من مجموعات Microsoft 365. لذلك، لتنفيذ هذا التغيير، يجب على هولي أولًا إنشاء مجموعة Microsoft 365 لأعضاء فريق المشروع التجريبي. يمكنها بعد ذلك إنشاء نسق مخصص مرتبط بهذه المجموعة والذي يتيح للإعداد عرض اسم المستخدم الذي قام بتسجيل الدخول. في هذه المهمة، ستقوم بإنشاء مجموعة Microsoft 365 لأعضاء فريق المشروع التجريبي لـ Microsoft 365 في Adatum. ستقوم بعد ذلك بإنشاء نسق مخصص يعرض اسم المستخدم الذي قام بتسجيل الدخول، وستقوم بتعيين فريق المشروع التجريبي لهذا النسق. كما ستقوم أيضًا بمراجعة الخيارات الأخرى التي يمكن تكوينها باستخدام النُسق المخصصة، ويمكنك إجراء أي تغييرات في الألوان ترغب فيها.

**هام:** في نهاية هذه المهمة، ستحاول حفظ النسق المخصص الذي قمت بإنشائه. هناك مشكلة معروفة في النظام الأساسي في مركز مسؤولي Microsoft 365 حيث يحفظ أحيانًا النسق المخصص بشكل جيد، وفي أحيان أخرى يقوم بإرجاع رسالة تقول "عذرًا، تعذر علينا حفظ النسق الخاص بك. الرجاء المحاولة مره أخرى لاحقا." إذا تلقيت هذه الرسالة، فلا يوجد شيء يمكنك القيام به سوى المضي قدمًا. عادة ما تكون نتيجة محاولة حفظ النسق في وقت لاحق بإرجاع نفس الخطأ. لن تؤثر هذه المشكلة على أي معامل مستقبلية، بخلاف أنها لن تعرض اسم المستخدم بجوار أيقونة المستخدم أو الأحرف الأولى من اسمك على سطر العنوان. على الرغم من هذه المشكلة المعروفة، ما زلنا نريد منك تنفيذ هذه المهمة لاكتساب الخبرة في إنشاء نسق، على الرغم من أنه قد لا تستطيع حفظها في الإصدار التجريبي.

1. يجب أن تستمر حالة تسجيل الدخول في LON-CL1 كحساب **adatum\مسؤول محلي**، وفي متصفح Edge، يجب أن تستمر حالة تسجيل الدخول Microsoft 365 كـ **مسؤول MOD**. 

2. في **مركز مسؤولي Microsoft 365**، حدد **Teams والمجموعات** في جزء التنقل، وضمنه، حدد **الفرق والمجموعات النشطة**. 

3. في صفحة**الفرق النشطة والمجموعات**، توجد علامة تبويب لعرض كل نوع من أنواع المجموعات. يتم عرض علامة التبويب **Teams ومجموعات Microsoft 365** بشكل افتراضي. تعرض علامة التبويب هذه مجموعات Microsoft 365 الموجودة.  <br/>

    حدد الخيار **+إضافة مجموعة Microsoft 365** الذي يظهر على شريط القوائم أعلى قائمة Teams ومجموعات Microsoft 365. سيؤدي هذا إلى بدء تشغيل معالج **إضافة مجموعة Microsoft 365**. 

4. في معالج **إضافة مجموعة Microsoft 365**، في صفحة **إعداد الأساسيات**، أدخل **إصدار تجريبي لمشروع M365** في حقل **الاسم**، ثم أدخل **أعضاء فريق إصدار تجريبي لمشروع Microsoft 365** في حقل **الوصف** (ملاحظة: حتى إذا لم تقم بإدخال وصف، فلا يزال يتعين عليك تحديد هذا الحقل لتمكين زر **التالي**). حدد **التالي**.

5. ستقوم الآن بتعيين مسؤول MOD كمالك لمجموعة **مشروع M365 التجريبي**. في نافذة **تعيين الملّاك**، حدد **+تعيين ملّاك**.
    
6. في جزء **تعيين الملّاك** الذي يظهر، حدد خانة الاختيار بجوار **مسؤول MOD**، ثم حدد الزر **إضافة (1)** في أسفل الجزء.

7. في صفحة **تعيين الملّاك**، يجب أن يظهر مسؤول MOD كمالك للمجموعة. حدد **التالي**.

8. ستقوم الآن بتعيين أعضاء إلى مشروع M365 التجريبي. في صفحة **إضافة أعضاء**، حدد **+إضافة أعضاء**.

9. في جزء **إضافة أعضاء** الذي يظهر، حدد مربعات الاختيار بجوار المستخدمين التاليين (بالرتيب الأبجدي): **أليكس ويبر**، **ألان ديونج**، **ديجيو سيسلياني**، **إشعياء لانغر**، **جوني شيرمان**، **ليني روبينز**، **ميجان بوين**، **مسؤول MOD**، **نيستور ويلكي**، و**باتي فيرنانديز**. حدد زر **إضافة (10)** في أسفل الجزء.

10. في صفحة **إضافة أعضاء**، تحقق من إدراج هؤلاء المستخدمين العشرة كأعضاء في المجموعة. إذا فاتك مستخدم، فحدد **+إضافة أعضاء** ثم أضف أي من المستخدمين العشرة الذين فاتوك. عندما يظهر جميع المستخدمين العشرة في هذه الصفحة، حدد **التالي**.

11. في صفحة **تحرير الإعدادات**، أدخِل المعلومات التالية: <br/>

    - أدخل **m365pilotproject** في **حقل عنوان البريد الإلكتروني للمجموعة**.
    - في حقل **الخصوصية**، حدد **خاص**.
    - ضمن قسم **إضافة Microsoft Teams إلى مجموعتك**، تحقق من تحديد خانة الاختيار **إنشاء فريق لهذه المجموعة** (حددها إذا كانت فارغة)، ثم حدد **التالي**.

12. في صفحة **مراجعة المجموعة والانتهاء من إضافتها**، راجع المحتوى الذي أدخلته. إذا كان هناك أي شيء يحتاج إلى إصلاح، فحدد **تحرير** ضمن المنطقة المحددة التي تحتاج إلى تعديل، وقم بإجراء أي تصحيحات ضرورية، ثم حدد **التالي** للمتابعة مرة أخرى إلى هذه الصفحة. بمجرد أن يكون كل شيء صحيحًا، حدد **إنشاء مجموعة**.

13. بمجرد ظهور نافذة **إنشاء مجموعة المشاريع التجريبية M365**، لاحظ التعليق في أعلى الصفحة أنه قد يستغرق ظهور المجموعة الجديدة في قائمة المجموعات النشطة 5 دقائق.  </br>

    حدد **إغلاق**. يؤدي ذلك إلى إرجاعك إلى صفحة **الفرق والمجموعات النشطة**، التي يجب أن تعرض علامة التبويب **Teams ومجموعات Microsoft 365**. نظرًا لأن مجموعة المشاريع التجريبية M365 كانت مجموعة Microsoft 365، يجب عرضها في النهاية على علامة التبويب هذه. إذا لزم الأمر، حدد خيار **تحديث** على شريط القوائم حتى ترى مجموعة المشروع التجريبي M365 في قائمة Teams ومجموعات Microsoft 365.

14. في **مركز مسؤولي Microsoft 365**، حدد **الإعدادات** في جزء التنقل ثم حدد **إعدادات** المؤسسة. 

15. في صفحة **إعدادات المؤسسة**، يتم عرض علامة التبويب **الخدمات** بشكل افتراضي. حدد علامة التبويب **ملف تعريف المؤسسة**.

16. تعرض علامة التبويب **ملف تعريف المؤسسة** قائمة بيانات ملف تعريف المؤسسة. في قائمة البيانات، حدد **تخصيص النسق**.

17. في الجزء **تخصيص Microsoft 365 لمؤسستك** الذي يظهر، يمكنك تخصيص النسق الافتراضي الذي يراه المستخدمون عند تسجيل الدخول إلى Microsoft 365، ويمكنك إضافة نُسق مخصصة إضافية. تريد إنشاء نسق مخصص جديد ينطبق فقط على أعضاء **مجموعة المشاريع التجريبية M365** التي قمت بإنشائها مسبقًا، لذا حدد الخيار **+إضافة نسق**.

18. في جزء **نسق المجموعة الجديد** الذي يظهر، يتم عرض علامة التبويب **عام** بشكل افتراضي. أدخل **نسق المشروع التجريبي M365** في حقل **الاسم**.

19. حدد داخل حقل **المجموعات**. في قائمة المجموعات التي تظهر، حدد **مشروع M365 التجريبي** إذا ظهر في قائمة المجموعات. <br/>

    **ملاحظة:** إذا لم يظهر **المشروع التجريبي M365** في قائمة المجموعات، فأدخل **M365** في حقل **المجموعات**. يجب أن يظهر مربع نتائج البحث الذي يعرض مجموعة **المشروع التجريبي M365**. حدد **مشروع M365 التجريبي**. 

20. حدّد خانة الاختيار **إظهار الاسم المعروض للمستخدم**. هذا هو الإعداد الذي تريد هولي تخصيصه لأعضاء فريق مشروع M365 التجريبي. يعرض هذا الخيار اسم المستخدم الذي قام بتسجيل الدخول بجوار الأحرف الأولى من اسمه في كل عنوان نافذة.
 
21. حدد علامة التبويب **الشعارات** وخذ بعض الوقت لمراجعة خياراتها. قم بنفس الشيء بالنسبة لعلامة التبويب **الألوان**. لاحظ خيارات النسق والعلامات التجارية المختلفة المتاحة لك للتحديث. <br/>

    لغرض هذا النشاط العملي، يمكنك تغيير أي من الخيارات أو ترك القيم الافتراضية كما هي. على سبيل المثال، في بيئتك الواقعية، يمكنك إضافة شعار شركتك وتعيين صورة الخلفية كصورة افتراضية لجميع المستخدمين لديك. بالنسبة لهذا النشاط العملي، لا تتردد في تغيير ألوان جزء التنقل، ولون النص، ولون الأيقونة، ولون التمييز. <br/>

    **استمر في استكشاف الخيارات المختلفة لهذا المظهر الذي سيستخدمه أعضاء فريق مشروع Microsoft 365 التجريبي. قم بإجراء أي تغييرات ترغب فيها.** <br/>

    **تلميح:** بعض أنماط الألوان تشتت انتباه المستخدمين من الناحية الجمالية. إذا قمت بتغيير أي من الألوان، فمن المستحسن تجنب استخدام الألوان ذات التباين العالي معًا، مثل ألوان النيون والألوان عالية الدقة مثل اللون الوردي الفاتح والأبيض.

22. حدد **حفظ**. 

    **ملاحظة:** كما ذكرنا سابقًا في بداية هذه المهمة، توجد مشكلة معروفة في النظام الأساسي في مركز مسؤولي Microsoft 365 حيث يتم في بعض الأحيان حفظ نسق مخصص جديد، وفي أحيان أخرى يتم إرجاع رسالة تقول "نأسف، لم نتمكن من حفظ نسقك. الرجاء المحاولة مره أخرى لاحقا." إذا تلقيت هذه الرسالة، فلن تؤثر على أي نشاطات عملية مستقبلية. نظرًا لأن نسقك المخصص لم يتم حفظه، فلن يعرض النظام ببساطة اسم المستخدم بجوار أيقونة المستخدم أو الأحرف الأولى من اسمه على سطر العنوان (بالإضافة إلى أن أي تغييرات في اللون ربما أجريتها لن تظهر). مازلنا نطلب منك القيام بهذه المهمة على الرغم من أنك قد تتلقى هذه الرسالة من أجل اكتساب الخبرة في إنشاء موضوع مثل هذا. لذلك إذا تلقيت هذا الخطأ، فتخط الخطوة التالية، التي تختبر النسق المخصص. ومع ذلك، لا يزال بإمكانك تنفيذ الخطوات المتبقية باتباع الخطوة التالية للتعرف على النسق الافتراضي. سواء تم حفظ نسقك المخصص أم لا، فأغلق جزء **نسق مشروع M365 التجريبي**.

23. إذا لم يتم حفظ نسقك المخصص، فانتقل إلى الخطوة التالية. ومع ذلك، إذا تم حفظ نسقك المخصص، فحدد أيقونة **تحديث** في الجزء العلوي من الشاشة، على يسار شريط العناوين. بمجرد تحديث الشاشة، لاحظ كيف يظهر اسم **مسؤول MOD** على يسار الدائرة التي تحتوي على الأحرف الأولى من MA أو الأيقونة المحددة لهذا الحساب بواسطة موفر استضافة نشاطك العملي. عندما يقوم أعضاء فريق مشروع Microsoft 365 التجريبي بتسجيل الدخول إلى Microsoft 365، سيعرض هذا النسق المخصص اسم المستخدم الخاص بهم، تمامًا كما يظهر اسم مسؤول MOD هنا. 

24. في قائمة بيانات ملف تعريف المؤسسة، حدد **النُسق المخصصة**.

25. في جزء **تخصيص Microsoft 365 لمؤسستك** الذي يظهر، لاحظ كيفية عرض **النسق الافتراضي** و**نسق مشروع M365 التجريبي** (إذا تم حفظ النسق في الخطوة السابقة). حدد **النسق الافتراضي**. 

26. في جزء **النسق الافتراضي**، لاحظ كيف لم يتم تحديد خيار **إظهار الاسم المعروض للمستخدم** للنسق الافتراضي. إذا قررت هولي لاحقًا جعل خيار **إظهار الاسم المعروض للمستخدم** ميزة دائمة، فستحدد هذا الخيار في جزء **النسق الافتراضي** حتى ينطبق على جميع مستخدمي Adatum، وستحذف **نسق مشروع M365 التجريبي**. <br/>

    **ملاحظة:** إذا تلقيت رسالة "عذرًا، لم نتمكن من حفظ نسقك. الرجاء المحاولة مره أخرى لاحقا." رسالة الخطأ التي تظهر لك عند محاولتك حفظ النسق المخصص مسبقًا، ثم حدد خيار **إظهار الاسم المعروض للمستخدم** في النسق الافتراضي، ثم حدد **حفظ**. نريدك أن ترى ما يحدث عند تحديد هذا الخيار، حتى لو لم تتمكن من حفظ نسقك المخصص. إذا عيّنت هذا الخيار على النسق الافتراضي، فحدد أيقونة **تحديث** في الجزء العلوي من الشاشة، على يسار شريط العناوين. بمجرد تحديث الشاشة، لاحظ كيف يظهر اسم **مسؤول MOD** على يسار الدائرة التي تحتوي على الأحرف الأولى من MA أو الأيقونة المحددة لهذا الحساب بواسطة موفر استضافة نشاطك العملي.
 
27. أغلق جزء **النسق الافتراضي**.

28. ابق مسجلًا الدخول إلى **LON-CL1** مع فتح Microsoft Edge على **مركز مسؤولي Microsoft 365** للمهمة التالية.

### المهمة 3 – تثبيت Microsoft Graph PowerShell 

يعد Microsoft Graph PowerShell ضروريًا لأداء العديد من مهام التكوين عند تثبيت Microsoft 365. نظرًا لأن تمارين الأنشطة العملية المستقبلية ستقوم بتنفيذ العديد من هذه المهام باستخدام Windows PowerShell، فيجب عليك البدء بتثبيت وحدة Microsoft Graph PowerShell. تتيح لك هذه الوحدة تنفيذ العديد من مهام إدارة المستخدمين والمؤسسات في Microsoft 365 عبر PowerShell. إنه رائع للمهام المجمعة مثل إعادة تعيين كلمة المرور، ونُهج كلمة المرور، وإدارة التراخيص وإعداد التقارير، وما إلى ذلك.  

1. في LON-CL1، يجب أن تظل مسجلًا الدخول بحساب **adatum\administrator** المحلي. لتثبيت Microsoft Graph PowerShell، يجب عليك فتح مثيل غير مقيد من **Windows PowerShell**. اكتب **power** في مربع البحث الذي يظهر في الزاوية اليسرى السفلية من شريط المهام. في قائمة نتائج البحث، انقر بزر الماوس الأيمن فوق **Windows PowerShell** (لا تحدد Windows PowerShell ISE) وحدد **تشغيل كمسؤول** في القائمة المنسدلة التي تظهر. 

2. كبّر نافذة PowerShell الخاصة بك. في **Windows PowerShell**، اكتب الأمر التالي في موجه الأوامر لتثبيت وحدة Microsoft Graph PowerShell من معرض PowerShell، ثم اضغط على Enter: <br/>

        Install-Module Microsoft.Graph -Scope CurrentUser

3. سيتم مطالبتك بتأكيد ما إذا كنت تريد تثبيت الوحدة من مستودع غير موثوق به (PSGallery). أدخل **A** لتحديد **[A] نعم للكل** ثم اضغط على Enter.  <br/>

    **ملاحظة:** سيؤدي ردك إلى بدء تثبيت كافة وحدات Microsoft Graph الفرعية. بمجرد الانتهاء من عرض جميع رسائل التثبيت لكل وحدة فرعية، سيستغرق الأمر ما يقرب من 5 إلى 10 دقائق إضافية لإكمال تثبيت Microsoft Graph PowerShell. خلال هذا الوقت، سيستمر المؤشر في الوميض أسفل رسالة المستودع غير الموثوق به. <br/>

    **قد يكون هذا وقتًا مناسبًا لأخذ استراحة قصيرة.**

4. سيظهر موجه الأوامر بمجرد تثبيت Microsoft Graph PowerShell. سيتم الآن عرض قائمة الوحدات الفرعية التي تم تثبيتها. للقيام بذلك، شغّل الأمر التالي:

        Get-InstalledModule Microsoft.Graph.* | select *name*

5. تأكد من أن قائمة الوحدات الفرعية المثبتة تتضمن الوحدات الفرعية الثلاث التالية التي سيتم استخدامها في تمارين النشاط العملي اللاحقة: 

    - مجموعات Microsoft Graph
    - إدارة دليل الهوية باستخدام Microsoft Graph
    - مستخدمو Microsoft Graph
    
    إذا ظهرت الوحدات الفرعية الثلاث في قائمة الوحدات الفرعية المثبتة، فانتقل إلى الخطوة التالية. ومع ذلك، إذا لم تظهر أي من هذه الوحدات الفرعية الثلاث في القائمة، فشغّل أمر PowerShell التالي لتثبيت الوحدة الفرعية المفقودة يدويًا:

        Install-Module -Name <module name> -Scope CurrentUser

    على سبيل المثال، إذا لم يتم تثبيت وحدة إدارة دليل الهوية باستخدام Microsoft Graph، فستقوم بتشغيل الأمر التالي:

        Install-Module -Name Microsoft.Graph.Identity.DirectoryManagement

6. تُحدد إعدادات نهج تنفيذ PowerShell ما هي نصوص PowerShell التي يمكن تشغيلها على نظام Windows. يؤدي تعيين هذا النهج على **غير مقيد** إلى تمكين هولي من تحميل جميع ملفات التكوين وتشغيل جميع البرامج النصية. من موجه الأوامر، اكتب الأمر التالي، ثم اضغط على Enter:   <br/>

        Set-ExecutionPolicy unrestricted

    إذا طُلب منك التأكد من رغبتك في تغيير نهج التنفيذ، فأدخل **A** لتحديد **[A] نعم للكل.** 

7. اترك نافذة PowerShell مفتوحة ولكن قُم بتصغيرها. ستستخدمه في تمرين نشاط عملي لاحق.


**تهانينا! لقد أكملت جميع الخطوات اللازمة لتهيئة مستأجر نشاطك العملي. أنت الآن جاهز لأداء تمارين الأنشطة العملية المتبقية.**

# نهاية النشاط العملي 1
