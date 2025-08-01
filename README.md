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
    ```

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

21. 