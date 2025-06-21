this lab is for recon with osint but very deep 

first if you got any image then just check its metadata using strings in cmd or exiftool


if you got any kind of data then just search it on google

here are some notes 



Bilkul! 👇 Yahan main **THM's OHSINT lab** ke liye **short, English notes** bana raha hoon — just enough to jog your memory later 🔁
You can copy-paste or save this for future reference.

---

### 🧠 **THM: OHSINT Lab - Quick Reference Notes**

#### 🎯 **Goal:**

Use OSINT (Open Source Intelligence) to gather publicly available data and track down a target.

---

### 🧩 **Key Techniques Used:**

1. **Username Enumeration:**

   * Use name + common handles on:

     * [Namechk](https://namechk.com)
     * [WhatsMyName](https://whatsmyname.app)

2. **Social Media Deep Dive:**

   * Look for clues in:

     * Twitter bios, images, hashtags, URLs.
   * Use tools:

     * [Twint](https://github.com/twintproject/twint) (if installed)
     * Manual search with Google `site:twitter.com "username"`

3. **Image Metadata & Reverse Search:**

   * Use:

     * [ExifTool](https://exiftool.org/)
     * [Google Reverse Image Search](https://images.google.com)
     * [Yandex Reverse Image Search](https://yandex.com/images)

4. **Email Footprinting:**

   * Try:

     * [HaveIBeenPwned](https://haveibeenpwned.com/)
     * Email format guessing from company name
     * Breach info / leaks

5. **Website Enumeration (if found):**

   * `whois`, `theHarvester`, or passive lookup
   * Archive data:

     * [Wayback Machine](https://archive.org/web)
     * [URLScan.io](https://urlscan.io/)

6. **Location Clues:**

   * Check photo backgrounds, social bios, timezone clues.
   * Use [GeoGuessr](https://geoguessr.com) style thinking.
   * Tools:

     * [GeoTips](https://www.geotips.net)
     * [Suncalc](https://www.suncalc.org)

---

### 🕵️‍♂️ **Mindset Tips:**

* **Everything is a clue**: Even emojis, likes, or retweets.
* **Check usernames across platforms** (cross-platform identity).
* **Look for reused info**: emails, nicknames, photos.
* **Google dorking** is your friend.

---

### 🔗 **Tools Summary:**

| Tool                 | Use                           |
| -------------------- | ----------------------------- |
| namechk, WhatsMyName | Username tracking             |
| ExifTool             | Metadata in images            |
| Google/Yandex        | Reverse image search          |
| HaveIBeenPwned       | Email breach info             |
| Wayback Machine      | Old versions of websites      |
| urlscan.io           | Website details + IP, JS etc. |
| Google Dorking       | Advanced keyword search       |

---
