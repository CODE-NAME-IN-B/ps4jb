# GamerHack verification

تم فتح الموقع الرسمي: https://gamerhack.github.io/

صفحة الموقع الرئيسية تعرض رابطاً باسم `GoldHEN 7.00 - 13.00` يشير إلى:
https://gamerhack.github.io/g2all/index.html

صفحة `g2all/index.html` تعرض نصاً صريحاً: `Only for PS4 with Firmware 7.00 to 13.00`، وتشكر Al-Azif وChendoChap وKameleonre وSiSTR0 وAbc.

هذه النتيجة تثبت أن GamerHack يعلن وجود Host لنطاق 7.00–13.00، لكنها لا تثبت وحدها أن كل ملف داخله يطابق بنية `webkit/*.js` و`kexploit/*.js` في المشروع الحالي. يجب فحص HTML والملفات المرتبطة قبل نسخها أو إعادة تسميتها.

## Exact routing observed in `g2all/index.html`

The page parses the PS4 User-Agent and routes by range. For 7.00–8.52 it redirects to `cache700.html` when the AppCache is empty, otherwise loads `700/alert.js`. For 9.00–9.60 it uses `cache900.html` or `900/alert.js`. For 10.00–11.02 it uses `cachecss.html` or `css/main.js`. For 11.50–12.02 it uses `cacheslopkit.html` or `slopkit/chain_lapse.js`. For 12.50–13.00 it uses `cacheslopkit.html` or `slopkit/chain_poops.js`.

The code therefore advertises 7.00–13.00, but it is not one universal exploit file. It is a dispatcher that selects different subchains. It also leaves explicit gaps between 11.02 and 11.50 and between 12.02 and 12.50 in its routing conditions. The page source does not expose all dependent files directly; they must be collected as a consistent directory tree from the same host.
