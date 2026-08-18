# 🎂 A Sweet Surprise — Personalized Birthday Cake Gift

Create a personalized birthday surprise and share it as a single link — like gift sites such as
[giftfeels.com](https://giftfeels.com/birthday-gifts). The **sender** writes their wishes,
promises and a note, gets a shareable link, and the **receiver** opens it to a full interactive
celebration: pick a knife, cut the cake, blow out candles, and read a personal letter. 💖

## ✨ How it works

**For the sender (landing page):**
1. Fill in who the gift is for, your name, a birthday wish, promises, and a note
2. Click **Create their gift** — everything is packed into a single shareable URL
3. Copy the link or share it directly to **WhatsApp / Telegram**
4. Preview the experience as the recipient before sending

**For the receiver (opens the link):**
1. A personalized intro — *"Today is all about Sarah!"*, from Alex
2. Pick a knife (Classic Silver, Golden Glow, Rosy Pink) — your cursor becomes the knife
3. Tap the 8 pastel cake slices to serve them; blow out the 5 candles (individually or all at once)
4. Confetti + floating hearts celebrate you
5. The grand finale: a letter with the sender's wish, promises and note, signed with love

## 🚀 Getting Started

No build step, no dependencies, no backend — the gift data travels inside the URL.

```bash
git clone https://github.com/<your-username>/birthday-cake.git
cd birthday-cake
start index.html          # Windows
open index.html           # macOS
```

Host it anywhere (GitHub Pages, Netlify, Vercel, a USB stick) — the link works as long as the
file is reachable.

## 🔒 Privacy note

All gift data is **URL-encoded** (base64, UTF-8 safe) into the `#hash` fragment of the link.
The fragment is never sent to any server, so the message stays between you and the recipient —
but anyone who gets the link can open it.

## 🖼️ Replacing the Cat

The cat photo (`cat.webp`) appears on the intro, celebration and creator screens. Swap your
own photo in:

```bash
cp /path/to/your-photo.webp cat.webp    # keep the same name
```

Or edit `index.html` and point the `<img src="cat.webp">` tags at your own image.
Images are circular crops (`object-fit: cover`), so square photos crop best.

## 🧩 Project Structure

```
birthday-cake/
├── index.html           # the entire experience (HTML + CSS + JS, ~60 KB)
├── cat.webp             # the birthday cat
└── README.md
```

## 🛠️ Customization

| What | Where |
| ---- | ----- |
| Colors | `:root` CSS variables (`--rose`, `--peach`, `--gold`, …) |
| Slice colors | `SLICE_COLORS` array at the top of the `<script>` |
| Candle colors | `CANDLE_COLORS` array |
| Field limits | `MAX` object (name lengths, wish / note / promise limits) |
| Copy / messages | Plain text inside the `<section class="screen">` blocks |

## ♿ Accessibility

- All interactive elements are real `<button>`s and `<input>`s with `aria` labels
- `prefers-reduced-motion: reduce` disables all animation
- Fully keyboard-navigable (Tab + Enter)

---

Made with 💖 for someone special.