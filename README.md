# AyuGram Desktop для Void Linux
[English](README-en.md)

![AyuGram](https://github.com/AyuGram/AyuGramDesktop/raw/dev/.github/AyuGram.png) ![AyuChan](https://github.com/AyuGram/AyuGramDesktop/raw/dev/.github/AyuChan.png) ![VoidBTW](https://github.com/void-linux/void-packages/blob/master/srcpkgs/void-artwork/files/icons/void-logo-128.png)

Неофициальная сборка мода [AyuGram](https://github.com/AyuGram/AyuGramDesktop) под **Void Linux**.

## Два способа установки

### Способ 1 — самый простой (готовый бинарный пакет, только x86_64-glibc)

```bash
# Добавляем наш репозиторий
echo "repository=https://github.com/OverLessArtem/ayugram-template-void/releases/latest/download" | sudo tee /etc/xbps.d/20-ayugram.conf

# Обновляем список пакетов
sudo xbps-install -S

# Устанавливаем AyuGram
sudo xbps-install -S ayugram-desktop
```

### Способ 2 — собрать самому
```bash
# Клонируем шаблон
git clone https://github.com/OverLessArtem/ayugram-template-void.git

# Клонируем официальный репозиторий void-packages
git clone https://github.com/void-linux/void-packages.git

# Копируем наш пакет в srcpkgs
cp -r ayugram-template-void/srcpkgs/* void-packages/srcpkgs/

# Переходим в директорию
cd void-packages

# Собираем пакет (может занять 10–40 минут)
./xbps-src pkg ayugram-desktop

# Устанавливаем собранный пакет
sudo xbps-install -R hostdir/binpkgs ayugram-desktop
```
