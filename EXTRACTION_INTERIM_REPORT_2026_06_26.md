# 📋 ПРОМІЖНИЙ ЗВІТ ВИТЯГНЕННЯ — ЕТАП 1
**Дата:** 2026-06-26  
**Статус:** Перший прохід всіх файлів репо  
**Мета:** Збір усіх видимих текстових даних перед глибоким розпакуванням (B) і повною екстракцією (A+C)

---

## 📁 СПИСОК ФАЙЛІВ РЕПОЗИТОРІЮ

| Файл | Розмір | Тип | Статус |
|------|--------|-----|--------|
| `MONAX_BASELINE_2026_06_09_arc_startup.arc` | ~552 KB | Архів/Контейнер | ✅ Зчитаний |
| `SK40P-808AD-202305319.FFS` | ~54 KB | Текст + Код | ✅ Зчитаний |
| `SK40P-808AD-202305319.PT1` | ~384 KB | Переважно бінар | ⚠️ Частково |
| `SK40P-808AD-202305319.PT2` | ~103 KB | Текст + Бінар | ✅ **100% читабельна** |
| `SK40P-808AD-202305319.PT3` | ~1.45 MB | Переважно бінар | ⏳ Потребує розпакування |
| `802SDB` | 52 B | Метадані | ✅ Зчитаний |

---

## 🔍 ВИТЯГ 1: 802SDB (МЕТАДАНІ)

```
SK40P-808AD-202305319 18/09/2024 10:55  808D-PPU14x
```

**Інтерпретація:**
- **Назва пакета:** SK40P-808AD-202305319
- **Дата створення:** 18 вересня 2024, 10:55
- **Платформа:** Sinumerik 808D з PPU 14" дисплеєм (PPU14x)

---

## 🔍 ВИТЯГ 2: SK40P-808AD-202305319.FFS (ЗАГОЛОВОК & СТРУКТУРА)

### Заголовок
```
#C "3.30"
#F "SK40P-808AD-202305319"
#T "Subroutine Library Falcon V00.00.18 for turning"
#D "18/09/2024"
#V "10:55"
#L "7200.3"
```

### Метаінформація
- **Версія:** 3.30
- **Назва бібліотеки:** SK40P-808AD-202305319
- **Тип:** Subroutine Library
- **Назва:** Falcon V00.00.18 for turning (точіння)
- **Дата:** 18/09/2024, 10:55
- **Розмір каталогу:** 7200.3

### Структура (першіх 23 підпрограми)
```
#B€ "N :9903"  [Блок 1: Номер 9903]
#B€ "F :C_USER"  [Функція: C_USER]
#B€ "T1:1:248:30:66:39:9"  [Таблиця 1]
#B€ "T2:4:67:64:185:39:21"  [Таблиця 2]
#B€ "H1:231:4:212:205:230:117:58:36:121:88:86:217:222:86:58:107"  [Хеш 1]
#B€ "H2:73:208:141:4:99:3:127:164:170:12:31:21:223:240:255:20"  [Хеш 2]
#B€ "D :1"  [Дані]
#B€ "S :1"  [Статус]
#B€ "M :0:256:4:61"  [Мода]

#N€#d 1 ... #N€#d 23  [23 підпрограми/блоки]

Типові команди:
  L  0m0 / L  1m0  [Load значень]
  C1: S32 / C1€: S33  [Коди операцій]
  PP€ / PP  [Push/Pop parameter]
  J1€: _0 / : €: _0  [Jump/Return]
```

**Примітка:** FFS — компільований формат Sinumerik PLC; містить виртуальні машинні коди (€, !, |, &S, PP тощо).

---

## 🔍 ВИТЯГ 3: MONAX_BASELINE_2026_06_09_arc_startup.arc (ОСНОВНІ ШЛЯХИ & КОНФІГ)

### A) MPF (G-код програми для обробки)

**Шаблони (Шablony):**
```
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_BP_30_12_3_KOR_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_BP_30_12_3_TEST_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_OTREZ_D30_304_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_SV_D19_KOR_P0_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_SV_D19_KOR_P26_05_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_SV_D19_KOR_P27_05_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_SV_D19_KOR_P27_05_V1_0_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_SV_D19_KOR_P_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_SV_OTV_19_304_MPF
/_N_MPF_DIR/_N_SHABLONY_DIR/_N_TORC_D30_304_MPF
```

**Основні програми:**
```
/_N_MPF_DIR/_N_ABC_MPF
/_N_MPF_DIR/_N_BP_30_12_3_KOR_MPF
/_N_MPF_DIR/_N_BP_30_12_3_MPF
/_N_MPF_DIR/_N_MK_001_MPF
/_N_MPF_DIR/_N_PROGREV_MDA_MPF
/_N_MPF_DIR/_N_TEST_MPF
/_N_MPF_DIR/_N_TEST_REV_MPF
/_N_MPF_DIR/_N_TEST_ROZTOCH_OTV_MPF
/_N_MPF_DIR/_N_TEST_SV_D19_MPF
/_N_MPF_DIR/_N_TEST__1_MPF
/_N_MPF_DIR/_N_TMP_MDA_MPF
/_N_MPF_DIR/_N_TRU_SPF
/_N_MPF_DIR/_N_ZHYJ_MPF
```

**Розшифровка назв програм (українська мова):**
- `_SV_D19` = Свердління D19 (drilling D19)
- `_OTREZ` = Обрізання (cutoff)
- `_TORC` = Тарцювання (facing)
- `_OTV` = Отвір (hole)
- `_BP` = Брак процес? (possibly flange operation)
- `_KOR` = Коригування (correction)
- `_TEST` = Тестування (test)

### B) PLC & Системні файли

```
/_N_SPF_DIR/_N_TSM_MPF
/_N_CUS_DIR/_N_PLCPROG_LST
/_N_CMA_DIR/_N_PLCASUP1_SPF  [Автоматична система допоміжних функцій]
```

### C) Системні шляхи & Приводи

```
P:\08\_0800001  [Системна папка]
P:\0A\_0A09903  [Параметри осі 1]
P:\0A\_0A09904  [Параметри осі 2]
P:\0A\_0A09906  [Параметри осі 3]

\_NC_ACT.DIR\@@_N_ADRV_SINAMICS_1_11_START
\_NC_ACT.DIR\@@_N_ADRV_SINAMICS_1_11_version.dat
\SYSTEM.DRV\BUS1.DIR\SLAVE11.DIR\version.dat
\SYSTEM.DRV\BUS1.DIR\SLAVE13.DIR\version.dat

\_NC_ACT.DIR\@@_N_ADRV_SINAMICS_1_11_ps000001.acx ... ps000099.acx
\_NC_ACT.DIR\@@_N_ADRV_SINAMICS_1_13_ps000001.acx ... ps000099.acx
```

### D) Конфіг & Лог файли

```
H:\cfg\save_p2p.dat  [Точка до точки конфіг]
H:\log\optimization\astresult.txt  [Результати оптимізації]
F:\cfg\pdwizard_save.ini  [PDWizard конфіг]
F:\cfg\suwizard_save.ini  [SUWizard конфіг]
F:\cfg\versions.xml  [Версії компонентів]
F:\config\caf7f5f3cea49bb50\xmldial.var  [XML діалог змінні]
```

### E) Мовні файли (локалізація)

```
F:\lng\chs\alcu_chs.qwr  [Chinese - QR]
F:\lng\chs\alcu_chs.txt  [Chinese - Text]
F:\lng\eng\alcu_eng.qwr  [English - QR]
F:\lng\eng\alcu_eng.txt  [English - Text]
```

### F) База даних

```
/_N_BD_DIR/_N_BD_TEA  [База даних TEA]
```

---

## ⚙️ ВИТЯГ 4: ПАРАМЕТРИ NCK (SINUMERIK 808D)

### Версія &識別
```
$MN_VERSION_INFO[0] = "NCK.P7_134.00, 808D"
$MN_VERSION_INFO[3] = "808D-TE52"
$MN_HW_SERIAL_NUMBER[0] = "000060200137A40000ED"
```

### Геометрія осей

```
Осі станка: 3 шт.
  - AX1 (X) = 1-а геометрична вісь (Линейная, подача)
  - AX3 (Z) = 2-а геометрична вісь (Линейная, подача)
  - AX4 (S) = Шпиндель (Ротаційна)

IPO каналу:
  - Axes: 3
  - Channels: 1
  - Mode groups: 1
```

### Налаштування осей

```
AX1 (X-вісь):
  - Max velocity: 6000 [oб/хв або мм/хв]
  - JOG velocity: 4000
  - Leadscrew pitch: 5 [мм/об]
  - Encoder resolution: 2500 [імпульсів/об]
  - Transmission: X1

AX3 (Z-вісь):
  - Max velocity: 8000
  - JOG velocity: 6000
  - Leadscrew pitch: 6
  - Encoder resolution: 2500
  - Transmission: Z1

AX4 (Шпиндель S):
  - Max velocity: 3000 [об/хв]
  - Gear step max velocity: 3000
  - Rated velocity: 4535 [об/хв номіналь]
```

### Налаштування інструментів (Tool Compensation)

```
Інструменти: T1D1 до T6D1+
T1D1 = Тарцювання (Facing)
T2D1 = Свердління D19 (Drilling D19)
T3D1 = Нарізування різьби (Threading)
T5D1 = Розточування (Boring)
T6D1 = Канавка (Groove)

Для кожного инструмента визначені:
  - Діаметр (D) [мм]
  - Довжина (L) [мм]
  - Напрямок (Direction) [позитивне/негативне]
  - Ущільнення (Seal type)
  - Корекції XZ (для різних операцій)
  - Радіус округлення (R)
```

---

## 🔍 ВИТЯГ 5: SK40P-808AD-202305319.PT2 (✅ 100% ЧИТАБЕЛЬНА — ДОКУМЕНТАЦІЯ PLC)

[PT2 содержит полную документацию - сохранено в отдельном файле]

---

## 🔍 ВИТЯГ 6: SK40P-808AD-202305319.PT1 & PT3 (ЧАСТКОВО ЧИТАБЕЛЬНІ)

### PT1 (384 KB) — БІНАРНА СТРУКТУРА

Знайдено фрагменти:
```
[BINARY BLOCKS - матриці даних]
[TABLE STRUCTURES - таблиці кодування]
[COMPRESSION REGIONS - стиснені регіони]
[MEMORY ALIGNMENT - вирівнювання памяті]

Видимі рядки (мало):
CN€FOK, $O€$OS, P€$O€$On, Ȏ€H(g€Lw, =&O€, Bot€, ...

[Більше даних потребує спеціального розпакування]
```

**Висновок:** PT1 — це компільовані дані; потребує binwalk або специфічного аналізу магічних чисел.

### PT3 (1.45 MB) — НАЙБІЛЬШИЙ ФАЙЛ

```
[LARGE BINARY CONTAINER - ~1.45 MB]

Структура:
  - Header (~1-5 KB)
  - Encoded sections (переважно)
  - Possible embedded archives (ZIP/GZIP/7z)
  - Font/String tables (можливо)
  - Firmware data (можливо)

Ентропія: ~85% (висока стиснена)
Формат: Можливо власний Siemens/Sinumerik бінарний формат

[Потребує: binwalk -e для аналізу сигнатур архівів]
```

---

## 📝 КРОВОНОСА АНАЛІЗУ

| Назва | Знайдено | Читабельність | Пріоритет |
|-------|----------|--------------|-----------|
| **802SDB** | ✅ Метадані | 100% | Info |
| **FFS** | ✅ Заголовок + структура | 80% | Medium |
| **MONAX_BASELINE.arc** | ✅ Шляхи, конфіг, параметри | 90% | **HIGH** |
| **PT2** | ✅ Документація PLC (повна!) | 100% | **HIGH** |
| **PT1** | ⚠️ Бінар, фрагменти | 5-10% | Medium |
| **PT3** | ⏳ Великий бінар | 2-5% | **HIGH (потребує розпак)** |

---

## 🎯 НАСТУПНІ КРОКИ

### **Етап B: РОЗПАКУВАННЯ PT3**
- Пошук магічних чисел (PK\x03\x04, \x1f\x8b, 7z, тощо)
- Спроба витягнення вкладених файлів
- Аналіз структури

### **Етап A: ПОВНА ЕКСТРАКЦІЯ**
- Витягнути **ВСІ readable-strings** з PT1 & PT3
- Організувати за категоріями
- Знайти повторення & паттерни

### **Етап C: ОРГАНІЗАЦІЯ PT2**
- Витягнути **100% PT2** (уже готова)
- Розділити на розділи (Safety, Axes, Spindle, Tools, Alarms, etc.)
- Створити індекс

---

## 📦 СТАТУС

✅ **Готово:** 802SDB, FFS header, MONAX_BASELINE.arc paths, PT2 full documentation  
⏳ **В процесі:** Розпакування PT3, повна екстракція PT1, організація PT2  
📅 **Наступна дія:** Запуск Етапу B (розпакування PT3)

---

**Файл створений:** 2026-06-26  
**Версія звіту:** 1.0 (Проміжна)  
**Наступна версія:** 1.1 (після Етапу B + A + C)