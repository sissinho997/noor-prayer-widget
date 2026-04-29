# Noor - Islamic Prayer Times & Du'a Widget

A beautiful Rainmeter widget that displays live Islamic prayer times and rotating Quranic du'a (supplications) with an elegant dark interface.

![Noor Widget](https://img.shields.io/badge/Rainmeter-Widget-blue) ![Version](https://img.shields.io/badge/version-1.0.0-gold)

---

## Features

- **Live Prayer Times** — Fetched automatically from the [Aladhan API](https://aladhan.com/prayer-times-api) for any city in the world
- **3 Content Sources** — Rotating between Quran ayat, Quranic du'a, and Prophetic hadith
  - **Quran Ayat** — Random verses from all 6236 ayahs via [Al Quran Cloud API](https://alquran.cloud/) (Arabic + English)
  - **Du'a (Quranic)** — 21 authentic Quranic supplications (Rabbana prayers, etc.)
  - **Hadith (Prophetic)** — Sayings of the Prophet ﷺ from 6 major collections (Bukhari, Muslim, Abu Dawud, Tirmidhi, Nasa'i, Ibn Majah) via [Hadith API](https://api.hadith.gading.dev/)
- **Hijri & Gregorian Date** — Both calendars displayed with Arabic month names
- **Next Prayer Countdown** — Shows upcoming prayer with time remaining (English & Arabic)
- **3 Beautiful Themes** — Gold & Black, Emerald & Navy, Rose Gold & Charcoal
- **16 Calculation Methods** — Supports ISNA, MWL, Egyptian, Umm al-Qura, and many more
- **Fully Configurable** — Edit the .ini file or use the built-in burger menu
- **Toggle Display Elements** — Show/hide translation, Bismillah, dates, prayer strip, content sources, and more
- **Responsive Layout** — Hidden elements free up space; du'a text enlarges when translation is off

---

## Requirements

- [Rainmeter](https://www.rainmeter.net/) (4.5+)
- [WebView Plugin](https://forum.rainmeter.net/viewtopic.php?t=36AWebView) — Place `WebView.dll` in your Rainmeter `Plugins` folder:
  - **Standard install**: `C:\Program Files\Rainmeter\Plugins\`
  - **Portable install**: `<Rainmeter>\Plugins\`
- Internet connection (for prayer times API and Google Fonts)

---

## Installation

1. Download and extract the `PrayerTimes` folder
2. Place it in your Rainmeter Skins directory:
   ```
   C:\Users\<YourName>\Documents\Rainmeter\Skins\PrayerTimes\
   ```
3. Make sure you have `WebView.dll` in your Rainmeter Plugins folder
4. Right-click the Rainmeter tray icon → **Skins** → **PrayerTimes** → **CustomPrayer.ini**

---

## Configuration

### Quick Setup (Edit the .ini file)

Open `CustomPrayer.ini` in any text editor and modify the `[Variables]` section:

#### Location
```ini
City=Quebec City
Country=Canada
```

**How to find your city name:**
- Use your city's common English name (e.g. `London`, `Dubai`, `Istanbul`, `New York`)
- For cities with spaces, just type them normally: `Quebec City`, `Kuala Lumpur`, `Mexico City`
- If your city isn't recognized, try the nearest major city
- Test your city at: https://api.aladhan.com/v1/timingsByCity?city=YOUR_CITY&country=YOUR_COUNTRY

#### Calculation Method
```ini
Method=2
```

| Method | Organization | Common Regions |
|--------|-------------|----------------|
| 1 | Egyptian General Authority | Egypt, Africa |
| 2 | ISNA | North America |
| 3 | Muslim World League (MWL) | Europe, Far East |
| 4 | Umm al-Qura | Saudi Arabia |
| 5 | University of Karachi | Pakistan |
| 7 | Institute of Geophysics, Tehran | Iran |
| 8 | Gulf Region | UAE, Oman |
| 9 | Kuwait | Kuwait |
| 10 | Qatar | Qatar |
| 11 | MUIS | Singapore |
| 12 | UOIF | France |
| 13 | Diyanet | Turkey |
| 14 | JAKIM | Malaysia |
| 15 | Ministry of Religious Affairs | Tunisia |
| 16 | Ministry of Religious Affairs | Algeria |

#### Theme
```ini
Theme=gold
```
- `gold` — Gold & Black (classic Islamic elegance)
- `emerald` — Emerald & Navy (mosque dome vibes)
- `rosegold` — Rose Gold & Charcoal (soft modern)

#### Display Toggles
Set any to `0` to hide, `1` to show:
```ini
ShowTranslation=1      ; English translation of du'a
ShowReference=1        ; Du'a source (Quran verse / Hadith)
ShowBismillah=1        ; Bismillah header
ShowGregorianDate=1    ; Gregorian date
ShowHijriDate=1        ; Hijri date
ShowPrayerStrip=1      ; Entire prayer footer section
ShowPrayerRow=1        ; Individual prayer times row
ShowBurgerMenu=1       ; In-widget settings menu (set 0 for clean look)
ShowAyat=1             ; Quran ayat from API (random verses)
ShowDuaa=1             ; Quranic du'a (supplications)
ShowHadith=1           ; Prophetic hadith from API
```

**Tip:** Set `ShowTranslation=0` and `ShowReference=0` for a du'a-focused Arabic-only display — the Arabic text will automatically enlarge to fill the space.

**Tip:** Enable/disable content sources independently — e.g. set `ShowAyat=0` and `ShowHadith=0` to show only Quranic du'a, or `ShowDuaa=0` to show only API-sourced content. When multiple sources are enabled, the widget rotates between them.

#### Widget Size
```ini
Width=680
Height=546
GrabHeight=30
```

### Right-Click Context Menu

You can also change settings by right-clicking the widget:
- **Change City** — Type your city name
- **Change Country** — Type your country name
- **Change Theme** — Type: `gold`, `emerald`, or `rosegold`
- **Change Method** — Type the method number (1-16)

### Burger Menu (In-Widget)

Click the ☰ icon (top-left) to open the built-in settings panel with:
- City & Country inputs
- Method & Theme dropdowns
- Toggle switches for all display options
- Content source toggles (Quran Ayat, Du'a, Hadith)
- Apply & Save button (saves to browser localStorage)

---

## Dragging the Widget

Drag the widget by grabbing the **title bar** at the top ("Noor - Prayer Times"). The WebView content area captures mouse events, so drag from the title bar only.

---

## Files

| File | Description |
|------|-------------|
| `CustomPrayer.ini` | Rainmeter skin configuration |
| `custom-prayer-widget.html` | Widget HTML/CSS/JS (do not edit unless customizing) |
| `README.md` | This file |

---

## Troubleshooting

**Widget shows "Loading prayer times..."**
- Check your internet connection
- Verify your city/country spelling
- Test the API URL in your browser: `https://api.aladhan.com/v1/timingsByCity?city=YOUR_CITY&country=YOUR_COUNTRY`

**Widget appears blank**
- Make sure `WebView.dll` is in your Plugins folder
- Restart Rainmeter after adding the DLL

**Skin deactivates with "no meters" error**
- Make sure `CustomPrayer.ini` is not corrupted — re-download if needed

**Times seem wrong**
- Change the calculation method to match your region (see table above)
- The API handles daylight saving time automatically

**Can't drag the widget**
- Drag from the title bar at the top only

---

## Credits

- Prayer times data: [Aladhan API](https://aladhan.com/)
- Quran text: [Al Quran Cloud API](https://alquran.cloud/)
- Hadith data: [Hadith API](https://api.hadith.gading.dev/) (Bukhari, Muslim, Abu Dawud, Tirmidhi, Nasa'i, Ibn Majah)
- Fonts: [Amiri](https://fonts.google.com/specimen/Amiri) (Arabic), [Poppins](https://fonts.google.com/specimen/Poppins)
- Built with the [Rainmeter WebView Plugin](https://forum.rainmeter.net/)

---

## License

Creative Commons Attribution-NonCommercial 4.0 (CC BY-NC 4.0)

Free to use, share, and modify for non-commercial purposes. Just credit the original author. See [LICENSE](LICENSE) for details.

---

**بِسْمِ ٱللَّهِ ٱلرَّحْمَـٰنِ ٱلرَّحِيمِ**

*May this widget be a source of remembrance and benefit. JazakAllahu Khairan.*
