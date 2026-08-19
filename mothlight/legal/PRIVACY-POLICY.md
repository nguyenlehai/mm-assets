<!--
  [Ngày 19] Nội dung chính sách riêng tư — viết bằng TIẾNG ANH có chủ đích (tài
  liệu pháp lý đi cùng App Store submission, App Store Connect + đa số reviewer/
  user đọc bằng tiếng Anh; khớp quyết định "English (U.S.) cho ASC metadata" đã
  ghi trong PLAN.md §9/CK-§18). Nội dung dưới đây phản ánh ĐÚNG THẬT những gì code
  hiện tại làm — không viết "an toàn hơn thực tế" (rủi ro pháp lý) và không viết
  "kém an toàn hơn thực tế" (rủi ro marketing) — xem chú thích [source] cuối mỗi
  mục trỏ về đúng file code chịu trách nhiệm.

  CẦN LÀM TRƯỚC KHI SUBMIT (việc của Hải, ngoài phạm vi code):
  1. Host nội dung này ở 1 URL công khai, ổn định (GitHub Pages từ chính repo
     này, Notion public page, hoặc trang tĩnh bất kỳ) — Apple YÊU CẦU link hoạt
     động được, không chấp nhận file .md thô trong app bundle.
  2. Điền URL thật vào `REVENUECAT_API_KEY`-style biến môi trường hoặc trực tiếp
     `src/constants/legalLinks.ts` (đã ghi rõ trong file đó).
  3. Đọc lại 1 lượt trước khi host — đây là bản do AI soạn dựa trên code thật,
     không thay thế tư vấn pháp lý; nếu có luật sư/cố vấn, nên rà lại.
-->

# Mothlight — Privacy Policy

_Last updated: August 19, 2026_

Mothlight is built around one promise: **the worry you write never leaves your
device.** This policy explains exactly what that means in practice.

## What we collect

**Nothing you write.** When you release a worry, its text lives only in your
device's memory for the length of the release ritual. It is written to disk
only inside the certificate you receive after it "dissolves" — and that
certificate never contains the original text, only a description of when and
where it dissolved (e.g. "Dissolved at 5:47 over the skies of Mongolia"). The
original words are discarded the moment the ritual ends and are never
transmitted anywhere, to us or to anyone else. [source: `src/stores/releaseStore.ts`,
`src/services/releaseService.ts` — no network call exists in either file]

**Location.** If you grant location permission, we use it once to compute
where your released worry "flies" — this happens entirely on your device using
offline astronomical calculations. If you decline, you can pick a city
manually, or the app falls back to an estimate based on your device's time
zone. In every case, this location is stored **only on your device** and is
never sent to us or any third party. [source: `src/services/locationService.ts`,
`src/screens/Settings/CityPickerSheet.tsx`]

**Purchases.** If you buy Mothlight Premium, the purchase is processed by
Apple/Google and relayed through RevenueCat, the subscription-management
service we use. RevenueCat receives a device/purchase identifier to know which
purchases belong to which install — this identifier is not linked to your
name, email, or any other personal information we hold, because we don't hold
any. See [RevenueCat's own privacy policy](https://www.revenuecat.com/privacy)
for how they handle this data. This is the only network connection that
carries any identifier tied to your purchases or your device. [source:
`src/stores/purchaseStore.ts`]

**App images and artwork.** The moth illustrations, night-sky art, certificate
backgrounds, and other pictures used throughout the app are downloaded once —
the first time you open Mothlight — from a public file server we control,
instead of being packed into the app you download from the App Store. This
means we can fix or improve the artwork later without shipping a new app
version. The download itself carries no information about you: no account, no
device identifier, nothing you've written — it's a plain, anonymous request
for image files, the same way a web browser loads pictures on a page, and the
server has no way to tell one install of Mothlight from another. Once
downloaded, the images are cached on your device and no further downloads
happen until we publish new artwork. If this first download hasn't finished
yet (for example, if you open the app for the very first time with no
internet connection), you'll briefly see a "Preparing the night" loading
screen until it can connect. [source: `src/services/assetPackService.ts`,
`src/components/AssetPackGate.tsx`]

**Usage counts.** The app keeps a small local log of anonymous counts (e.g.
"a worry was released," "the garden was visited") to help us understand which
parts of the app are used — never the content of anything you wrote, never
even its length. This log stays on your device and you can view it any time,
or delete it along with everything else, from Settings → Advanced. It is never
transmitted anywhere. [source: `src/services/analytics.ts`]

**Notifications.** Mothlight schedules local notifications on your device
(e.g. "your worry has dissolved") using your device's own operating system.
There is no push notification server — we could not send you anything even if
we wanted to. [source: `src/services/notificationService.ts` — uses `notifee`,
a local-only notification library]

## What we don't do

- No account or sign-in of any kind.
- No advertising, no ad networks, no ad identifiers.
- No analytics SDK that phones home (Firebase, Mixpanel, Amplitude, etc. are
  not present in this app).
- No sharing, selling, or renting of any data, because we don't collect any
  data to share, sell, or rent.
- No social features, no way for anyone else to ever see what you wrote.

## Deleting your data

Settings → Advanced → "Delete all data" permanently erases every certificate,
your night garden, your settings, and your local usage log from your device.
Since nothing is stored anywhere else, this is a complete and permanent
deletion — there is no server-side copy to also ask us to remove.

## Children's privacy

Mothlight does not knowingly collect any information from anyone, including
children, because it does not collect personal information from any user.

## Changes to this policy

If this policy changes, the "Last updated" date above will change too. Since
the app collects nothing, changes are expected to be rare and minor.

## Contact

haithangtho@gmail.com
