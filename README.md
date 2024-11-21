# Fix inputs font-size < 16px

  - Выставляем font-size = 16px;
  - Устанавливаем font-size-adjust меньше стандартного

## Как получить дефолтное значение font-size-adjust

  - Если нужны точные значения font-size-adjust, то нужно любым доступным инструментом достать из шритфа две метрики: unitsPerEm и xHeight.
  - Например идём на https://seek-oss.github.io/capsize/, там выбираем шрифт либо из гугловых, либо из системных, можно файлом загрузить.
  - Затем там пояснительную картинку меняем на {} JSON и из него забираем unitsPerEm и xHeight.
  - Делим второе на первое — это и есть дефолтный fons-size-adjust для этого шрифта.

Ну а дальше уменьшаем дефолтный font-size-adjust до необходимого нам значения.

**Например, мы используем шрифт golos-text.**

xHeight = 530, unitsPerEm = 1000

Default font-size-adjust = 530 / 1000 = 0.53

Если нам в инпуте нужен шрифт 14px, тогда новый font-size-adjust = 0.53 * 14 / 16 ~ 0.464

```
.font-adjust {
  -webkit-font-size-adjust: 0.464;
  font-size-adjust: 0.464;
}
```
