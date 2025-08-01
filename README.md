# intrvyu

### Question


1. Pythonda mutable va immutable obyektlari mavjud!
    
    Mutable (uzgaruvchan) - Bu turdagi obyektlar yaratilgandan sung ularning qiymati yoki tarkibi o'zgartirilishi mumkin. Ya'ni obyektning xotiradagi manzili uzgarmasdan, uning ichidagi malumotlari uzgartiriladi.
    (List, Dictionary, Set, Bytearray)

    Immutable (uzgarmas) - BU turdagi obyektlar yaratilgandan sung ularning qiymati yoki tarkibi uzgartirilmaydi. Agar uzgartirish kerak bo'lsa yangi obyrkt yaratiladi eskisi hech qachon uzgarmaydi va o'zgartirib ham bo'lmaydi.
    (INteger, STring, Float, Tuple, Frozenset, Boolen, Bytes)

2. Python’da mutable va immutable obyektlar nima? Misollar bilan tushuntiring.

    🔹 Mutable obyektlar – qiymatini o‘zgartirish mumkin bo‘lganlar (list, dict, set),

    🔹 Immutable obyektlar – qiymatini o‘zgartirib bo‘lmaydiganlar (int, float, str, tuple).

3. Nima uchun tuple immutable hisoblanadi lekin ichida mutable bo'lsa o'zgartirib bo'ladimi?

    Ha tuple immutable hisoblanadi lekin tuple ning ichida mutable bo'lsa uni uzgartirsa bo'ladi.
    ```
    a = ([1,2,3], 5)
    a[0].appemd(5)
    print(a)
    ```

4. += operatori immutable va mutable obyektlariga nisbatan qanday ishlaydi?

    list += [...] - o'zgaradi (in-palce)
    str += ... - yangi string yaratadi
    ```
    lst = [1]
    lst += [2]

    s = "a"
    s += "b"
    ```

5. Nima uchun id() funksiyasi immutable obyektlar bilan ishlaganda o'zgaradi?

    immutable obyekt ustida uzgarish qilinsa, Python yangi obyekt yaratadi.
    ```
    a = 'salom'
    print(id(a))
    a += 'hello'
    print(id(a))
    ```

6. List Dictionary da kalit qiymati sifatida kela oladimi?

    list mutable, shuninguchun u dict kalit sifatida ishlamaydi.
    ```
    my_dict = {[1, 4]: 'value'} # ❌ TypeError
    ```

7. copy() va deepcopy() mutable obyektlar bilan qanday farqlandai?

    copy() - sirtqi nusxa
    deepcopy() - chuqur nusxa (nested obyebtlar bilan ishlaydi)

8. str obyektini 'zgartirish uchun qanday  yondashuv ishlatiladi?

    str immutable, lekin join, replace yordamida yangi str yaratamiz.
    ```
    s = 'hello'
    s = s.replace('h', 'H')
    print(s)
    ```

9. Lambda funksiyasi nima va qachon ishlatiladi?

    🔄 Lambda - bu nomsiz funksiya bo`lib qisqa va oddiy funksiyalarni yaratishda ishlatiladi. U asosan map(), sorted() va filter() funksiyalari bilan ishlatiladi

    Lambda - birgina ifoda bajaradi va return suzisiz natija qaytaradi.

10. Pythonda list, tuple, dict va set tuzilmalarining asosiy farqlari nimalardan iborat?
    
    ✅ List - tartibli va uzgaruvchan (mutable) tuzulma,

    ✅ tuple - tartible lekin uzgarmas (immutable) tuzilma,

    ✅ dict - kalit - qiymat juftligidan iborat va tartibli tuzulma,

    ✅ set - noyob elementkar tuplami, tartibsiz

11. Pythonda for va while sikillari qanday ishlaydi?

    ✅ for sikli odatda elementlar ustida ketma ket yurishda ishlatiladi (iterable obyektlar - list, string, range).

    ✅ while sikli esa berilgan shart bajarilguncha ishlaydi.(for malumot bilan while esa holat bilan ishlaydi)

12. break, continue va pass operatorlarining vazifasi va farqi nima?

    ✅ break - sikildan chiqadi(yani kodni tuxtatadi)

    ✅ continue - hozirgi iteratsiyani tashlab keyingisiga utkazadi.

    ✅ pass - kodning urnini vaqtincha bosh qoldirish uchun ishlatiladi.

13. Python’dagi range() funksiyasi nima?

    ✅ range() funksiyasi butun sonlar ketma-ketligini hosil qiladi. U ko‘p hollarda for sikli bilan birga ishlatiladi. U start, stop, step parametrlarini oladi.

14. *args va **kwargs nima va ularni qachon ishlatish kerak?

    ✅ *args - pozitsion argumentlar uchun

    ✅ **kwargs - kalit-qiymat argumentlar uchun.

    misol
    ```
    def api_handler(*args, **kwargs):
    print(args, kwargs)

    api_handler(1, 2, user="Akobir", status="active")
    ```
    Natija: (1, 2) {'user': 'Akobir', 'status': 'active'}

15. Decorator nima va uni qanday yaratamiz?

    ✅ Decorator - bu funksiyani qabul qilib, unga qushimcha xatti xarakatni qushadigan funksiyadir

    Decoratorlar API xavfsizligi(token, validation, rate limiting) uchun decoratorlar ishlatiladi.

    misol
    ```
    def auth_required(func):
    def wrapper(*args, **kwargs):
        print("Checking Auth...")
        return func(*args, **kwargs)
    return wrapper

    @auth_required
    def view_dashboard():
        print("Welcome!")

    view_dashboard()
    ```

16. Iteratot va Ginerator urtasidagi farq nima?

    ✅ Iterator - __iter__(), va __next__() metodlariga ega obyekt.

    ✅ Ginerator- yield orqali ishlaydiga funksiya avtomatik iterator hosil qiladi.

    Katta fayllarni satrma satr uqishda streming API uchun ginerator ishlatiladi.

    misol:
    ```
    def my_gen():
    for i in range(3):
        yield i

    for x in my_gen():
        print(x)
    ```

17. Python'da context manager nima va u qanday yaratiladi?

    ✅ Context manager with operatori orqali ishlatiladi, resurslarni avtomatik ochib yopadi.

18. Python'da module va package nima va ularning farqi?

    ✅ Module - bu py fayllar 

    ✅ Package - __init__.py bolgan katalog.

    Katta tizimlarda kodni modullarga bulib packge sifatida tarqatiladi. Masalan utils, core, services.

19. Duc typing nima?

    ✅ Typening obyekt nomiga emas uning metod/xatti-xarakatiga qarab baxolanadi. 'Biror narsa uzini usha kabi tutsa - u ushadir'. 

    Generic intrfeyslar (.save(), .validate()) buyicha har xil turdagi klasslar bilan ishlaganda ishlatiladi.

20. Python'da metaclass nima ?

    ✅ Klasslar qanday yaratilishini boshqaradigan klass.

    Yani - ORM yaratganda (Model klasslarida), DRY prinsipida custom field validation qilish uchun.

21. Matn metodlaridan upper(), lower(), replace(), strip() qanday ishlatiladi?

    ✅ upper() - matinni katta harflarga utkazib beradi.

    ✅ lover() - matinni kichik harflarga utkazib beradi.

    ✅ replace(old, new) - eski qismni yangisiga almashtiradi.

    ✅ stript() - bush joylarni olib tashledi.

22. if ichida yana if (nested if) yozish qachon kerak bo`ladi?

    ✅ Nested if faqat birinchi shart True bo'lgandagina ikkinchi shartni tekshirish kerak bo'lganda ishlatiladi.Mahsulot mavjud bo‘lsa va chegirma mavjud bo‘lsa, foydalanuvchiga narxni ko‘rsatish:

23.  Boolean qiymatlar va if qanday ishlaydi?

    ✅ Javob: Python’da if sharti True yoki False ga baholanadi. Quyidagi qiymatlar False sifatida qabul qilinadi: 0, 0.0, None, False, bo‘sh string '', bo‘sh ro‘yxat [], bo‘sh dict {}. Boshqa barcha qiymatlar True hisoblanadi.

24. if shartida qiymat to'g'ridan to'g'ri baholash (truthy/falsy) afzalliklari va havflari qanday?

    ✅ Bunday yondashuv kodni qisqa qiladi, ammo qiymat False haholansa, lekin semantik jihatdan bu False emas bo'lishi mumkin. BU xatolik manbai bo'lladi

    misol
    ```
    users = []
    if not users:
        print("Foydalanuvchilar yo‘q")
    ```

25. Ternary operator(x if condition else y) qanday ishlaydi va qachon ishlatilishi kerak?

    ✅ BU qisqa if else ko'rinishidir. Shartga qarab qiymat tanlanadi. KIchik va o'qilishi oson holatlarda foydalaniladi.

    misol:
    ```
    age = 40
    status = "yosh" if age < 30 else "katta"
    print(status) 

    ```

26. elif dan kop foydalanganda kod o'qilishi pasayadimi yani Alternativa bormi?

    ✅ Ha juda kop elif kodni o'qilishini qiyinlashtiradi. Altirnative sifatida match-case(Python.3.10+) dict-based dispatch ishlatiladi.

    midol
    ```
    def handle_status(code):
        return {
            200:'ok',
            404:'Not Found',
            500:'Server ERROR',
        }.get(code, 'Unknown')
        ```

27. match-case konstruksiyasi qanday ishlaydi va 'if va elif' ga nisbatan afzalligi qanday?

    ✅ match-case Python 3.10 dan boshlab kiritilgan. Bu 'switch-case' ga o'xshash. Yaxshi strukturaviy yondashuv beradi, ayniqsa kop holatlarni tahlil qilish kerak bo`lsa.

    misol:
    ```
    status_code = 404
    match status_code:
        case 200:
            print("OK")
        case 404:
            print("Topilmadi")
        case _:
            print("Noma’lum holat")

    ```

28. if blokida bajarilayotgan kodda return, break, continue mavjud bo‘lsa, bu qanday ta’sir qiladi?

    ✅ Javob: Bu operatorlar if ichidagi blokdan keyingi kodni bajarilishini to‘xtatadi. return — funksiya tugaydi, break — sikldan chiqadi, continue — sikl keyingi iteratsiyasiga o‘tadi.

    Misol:
    ```
    for i in range(5):
        if i == 2:
            continue
        print(i)
    ```

29. Savol: if blok ichida try-except ishlatishning afzalliklari?

    ✅ Javob: Dastur shart bajarilayotgan holatlarda xatolik yuz bersa, try-except blok bilan bu holatni boshqarish imkonini beradi va ilovani qulab tushishdan saqlaydi.

