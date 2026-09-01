# Embedding the Foil Cap Tool in Shopify

You have 3 ways to add this to Shopify. **Option A (iframe) is recommended** — easiest, and it auto-updates whenever we push changes.

---

## ✅ OPTION A — iframe (RECOMMENDED)

The tool stays hosted on GitHub Pages. You just embed a window to it.
**Any future change we make appears automatically. No re-pasting ever.**

### Steps:
1. Shopify Admin → **Online Store → Pages → Add page**
2. Title it: `Foil Racing Caps` (URL becomes `/pages/foil-racing-caps`)
3. In the content editor, click the **`< >` "Show HTML"** button (top-right of editor toolbar)
4. Paste this:

```html
<iframe
  src="https://swimnerdtim.github.io/foil-caps-calculator/"
  style="width:100%; min-height:1500px; border:none; border-radius:16px;"
  title="Foil Racing Cap Pricing"
  loading="lazy">
</iframe>
```

5. Save. Done.

> If the page has extra padding/margins around it, that's your theme. Fine to leave.

---

## OPTION B — Custom Liquid section (fully native, no iframe)

Use this if you want the tool rendered directly in your theme (no iframe box).

### Steps:
1. Shopify Admin → **Online Store → Themes → Customize**
2. Navigate to the page you want it on (or create a new page + template)
3. Click **Add section → Custom Liquid**
4. Paste the **entire contents** of `shopify-embed.html` (the standalone file in this repo)
5. Save

This preserves all interactivity (scripts + styles inline).

> Note: Some themes constrain width. If it looks cramped, add the section to a
> full-width template or wrap it in a full-width container.

---

## OPTION C — Page with inline HTML

Same as Option A steps 1–3, but paste the entire `shopify-embed.html` contents
instead of the iframe. **Risk:** Shopify's page editor can strip `<script>` tags
on save, breaking interactivity. If that happens, use Option A or B.

---

## Which should you use?

| Goal | Use |
|------|-----|
| Fastest, auto-updates | **Option A (iframe)** |
| Native look, no iframe box | Option B (Custom Liquid) |
| Simple page, willing to risk script-stripping | Option C |

**Recommendation: Option A.** One line, always current.
