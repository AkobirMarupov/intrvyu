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

9. 