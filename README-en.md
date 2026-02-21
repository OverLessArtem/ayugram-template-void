# AyuGram Desktop for Void Linux


![AyuGram](https://github.com/AyuGram/AyuGramDesktop/raw/dev/.github/AyuGram.png) ![AyuChan](https://github.com/AyuGram/AyuGramDesktop/raw/dev/.github/AyuChan.png) ![VoidBTW](https://github.com/void-linux/void-packages/blob/master/srcpkgs/void-artwork/files/icons/void-logo-128.png)

Unofficial build of the [AyuGram](https://github.com/AyuGram/AyuGramDesktop) mod for **Void Linux**.

## Two installation methods

### Method 1 — Easiest (pre-built binary package, x86_64-glibc only)

```bash
# Add our repository
echo "repository=https://github.com/OverLessArtem/ayugram-template-void/releases/latest/download" | sudo tee /etc/xbps.d/20-ayugram.conf

# Sync package index
sudo xbps-install -S

# Install AyuGram
sudo xbps-install -S ayugram-desktop
```

### Method 2 — Build it yourself

```bash
# Clone the template
git clone https://github.com/OverLessArtem/ayugram-template-void.git

# Clone official void-packages
git clone https://github.com/void-linux/void-packages.git

# Copy our package sources
cp -r ayugram-template-void/srcpkgs/* void-packages/srcpkgs/

# Enter directory
cd void-packages

# Build the package (takes ~10–40 minutes depending on your machine)
./xbps-src pkg ayugram-desktop

# Install the built package
sudo xbps-install -R hostdir/binpkgs ayugram-desktop
```
