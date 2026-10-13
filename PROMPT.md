# Build a sample online shop for Otis & Allen (Burlington, ON)

You are building a **sales sample** that STOHRX will show to the owners of Otis & Allen, a locally owned pet shop, to win a website and online-store redesign. Their current Shopify store at https://otis-allen.myshopify.com/ is a half-finished default theme: stock photos, eight "Your product's name" placeholder products at $19.99, one real product with no photo, no address, no hours, no phone, and a catalogue page that says "1 product". When the owners see this sample next to that, they should immediately understand what their shop could look like online, and want to buy it.

Work in this folder: `C:\Users\zacbe\Desktop\STOHRX WORK\SAMPLES\Otis and Allen\`

If a `frontend-design` skill is available to you, invoke it before you start designing.

## What to deliver

- **One file: `index.html`.** Self-contained, vanilla HTML, CSS and JS. No frameworks, no build step, no Tailwind, no external JS libraries. Google Fonts are allowed (preconnect + one stylesheet link). Nothing else external at runtime.
- **A working demo shop**, not a brochure. Browsing, filtering, a product panel with sizes, a cart that survives reload, and a checkout that ends in a confirmation screen. Everything client-side; nothing is actually charged, and the confirmation must say so.
- Images in `images/` next to the HTML, converted to **webp** at sensible widths. Keep `images/reference/` untouched.
- Must open by double-clicking the file (file:// protocol). No absolute paths, no fetch() of local files (file:// blocks it), so the catalogue lives in a JS array inside the page.
- Must look great at 375, 768, 1280 and 1920 px wide. No horizontal scroll. 16px minimum side gutter on phones.
- Lighthouse-minded: lazy-load below-the-fold images, `width`/`height` on every `<img>`, `<meta name="description">`, semantic landmarks, skip link, visible focus states, `prefers-reduced-motion` respected, real alt text.
- Follow the conventions of the other samples in `../`, especially `../Coffeed/index.html`, which is the closest thing to this brief: a single-page shop with a catalogue array, `<dialog>` product panel, `<dialog>` cart and checkout, `localStorage` cart, and pickup vs. delivery logic. Read it before you start. **Match its conventions and its level of polish, not its visual design.** This shop must not look like Coffeed.

## About the business (all real; do not invent facts)

- **Name:** Otis & Allen. Also listed as "Otis & Allen Healthy Pet Foods". The Shopify header uses the tagline "Friends and Furry Friends".
- **What they are:** a locally owned pet boutique for dogs and cats. Their own words: "Retailer of top notch pet products and services. Healthy dog and cat food." and "Pet Boutique for your dogs and cats, featuring healthy food, treats, grooming and all things fun!"
- **Address:** 2500 Appleby Line, Unit D11, Burlington, ON L7L 0A2. This is the Millcroft plaza in north Burlington.
- **Phone:** 905-335-7036
- **Email:** otisandallen@gmail.com
- **Facebook:** https://www.facebook.com/OtisandAllenBurlington/ (724 followers, 94% recommend from 26 reviews). No Instagram found under this name.
- **Services (from their Facebook page and their Fromm retailer listing):** grooming ("the best groomer ever"), an in-store bakery, delivery, curbside pickup, in-store pickup, in-store shopping, and hands-on nutrition advice.
- **Hours:** directories disagree, so do not print a day-by-day table as fact. The most consistent reading is roughly 10 a.m. to 6 p.m. weekdays, 9 or 10 to 5 Saturday, shorter Sunday. Show "Open 7 days" with a clearly marked placeholder comment for exact hours, and note "Closed holidays" (a Facebook post confirms they close Sunday and Monday of Thanksgiving).
- **Values, in their own words from the current site (reuse, lightly edited):**
  - Healthy Food: "None of the food we carry contain wheat, corn or by-products! Check your ingredients, do your research and stop by anytime for hands on advice!"
  - Treats: "All of our treats are healthy and Canadian sourced as much as possible."
  - Accessories: "We pride ourselves on finding fun and unique items for your pets and homes. We try to source locally and Canadian as much as possible!"
  - "Pets Are Part of the Family. Our pets sleep in our beds these days. Treat them with the best care and nutrition possible."
- **One real review (Yellow Pages, 2017):** "Friendly service and very professional. Have always been very helpful and informative. Great selection of pet foods and needs." You may use it with the attribution "Yellow Pages review". Do not invent other reviews.

### What they actually stock

The Shopify catalogue is empty on the public side, but its collection list is real and tells you the brands and the shape of the range:

| Collection | Count | Notes |
|---|---|---|
| Accessories & Merchandise | 406 | the biggest category |
| Treats for Dogs | 183 | |
| Toys for Dogs | 93 | |
| FROMM | 61 | authorized retailer; carries Four-Star, Gold, Pâté, Frommbalaya stews, Crunchy Os treats, and Fromm cat Four-Star |
| ACANA | 50 | |
| Dry Food for Dogs | 47 | |
| OPEN FARM | 36 | |
| go! (Petcurean) | 32 | |
| Orijen | 27 | |
| Bowser Beds | 25 | Canadian-made dog beds |
| Supplements for Dogs | 24 | |
| Canned Food for Dogs | 18 | |
| Holiday | 8 | seasonal |
| GRAND CRU | 6 | Canadian raw/dehydrated |
| Dry Food for Cats | 6 | |
| Hot Dogs Leather | 3 | Canadian leather collars/leads |
| Preston Collars and Leashes | 2 | ribbon collars |
| Supplements for Cats | 1 | |
| Cat treats, toys, canned | 0 | thin on cat right now |

Two collections are named **"Food - Auto"** and **"Treats - Auto"**. Treat that as a hint that they want (or already do) repeat orders, and build an auto-ship option into the demo (see below).

The one real product on the live store is the **Outward Hound Hide N' Slide dog puzzle, $43.99**. Include it.

A directory listing suggests the Burlington shop may once have been a **Bark & Fitz** franchise. Do not mention this anywhere on the page.

## Catalogue to build (demo data)

Build about **28 products** in a JS array, each with: id, name, brand, category (`food`, `treats`, `toys`, `beds`, `walk` for collars/leads, `health` for supplements, `bakery`), pet (`dog`, `cat`, or both), price, optional sizes with their own prices (dry food comes in 2 kg / 6 kg / 11.4 kg style bags), a one-line description, two or three "good for" tags (e.g. "Grain-free", "Puppy", "Sensitive stomach", "Senior", "Canadian-made", "Made in-store"), and flags for `autoship` (food and treats only), `pickupOnly` (bakery and big bags of food), and `soldOut` (one or two items).

Use the real brands above and real product lines you can verify on the brands' own websites (Orijen Original, Acana Grasslands, Fromm Four-Star Duck & Sweet Potato, Open Farm Grass-Fed Beef, go! Solutions Carnivore, Grand Cru dehydrated, Bowser bed styles, Outward Hound puzzles). Prices must be realistic Canadian retail and marked in a comment as **placeholders until the shop sends real pricing**. Give the in-store bakery three or four items of your own naming (pupcakes, a birthday cake, peanut butter bones) marked "Made in-store, pickup only".

**Product photos.** Download official packshots from the brand manufacturers' websites for the demo (Champion Petfoods for Orijen and Acana, frommfamily.com, openfarmpet.com, petcurean.com, bowserpetproducts.com, outwardhound.com). Convert to webp at ~800px, name them by product id, and add a comment at the top of the file listing where each came from and that they are **for this sample only, to be replaced with the shop's own photos**. If a packshot cannot be fetched, render that product as a clean CSS "bag" placeholder in the brand's colour with the product name set in type, not a grey box with a camera icon.

## What makes this one interesting

The framing sample was a quiet single page. This one is a shop, and it should feel alive. Build these, in priority order:

1. **Shop by pet, then by need.** The top of the shop has a Dog / Cat toggle that filters everything below, then chips for category and for "good for" tags (Puppy, Senior, Grain-free, Sensitive stomach, Canadian-made). The URL hash should reflect the filter (`#dog/food`) so a link can be shared. Counts on the chips update live.
2. **Product panel with real variants.** Clicking a product opens a `<dialog>` with the photo, sizes as radio buttons with the price updating, an "Add to bag" button, the "good for" tags, and the autoship choice where allowed.
3. **Auto-ship.** On food and treats, offer "One time" or "Every 2 / 4 / 6 weeks, save 5%". The bag shows the schedule on each line. The checkout confirmation explains when the next delivery would come. This is the feature that turns a one-time buyer into a regular, and it is the thing the owners should notice.
4. **Bag and checkout.** `localStorage` bag with a count in the header, quantity steppers, remove, subtotal. Checkout with three fulfilment options: **Pick up in store** (free, 2500 Appleby Line), **Curbside pickup** (free, "we will bring it to your car"), and **Local delivery** (Burlington and Oakville, free over $75, otherwise $6.99, with a postal-code check that accepts prefixes L7L, L7M, L7N, L7P, L7R, L7S, L7T, L6H, L6J, L6K, L6L, L6M and politely declines others). HST 13%. Pickup-only items block delivery with a clear message, as Coffeed does. Order number, a sentence saying nothing was charged.
5. **Food finder.** A small three-question tool: pet (dog/cat), life stage (puppy or kitten / adult / senior), and one concern (none / sensitive stomach / weight / allergies / picky eater). It returns two or three products from the catalogue with a one-line reason each, and a line that says "Not sure? Bring the bag you're using now and we'll compare labels at the counter." Keep it honest: the recommendations are rules you write in JS, not AI.
6. **Grooming request.** A short form: pet's name, breed or size, service (bath and brush / full groom / nail trim), preferred day. It does not send anywhere; it shows a "We'll call you to confirm" message and has a comment marking where it would post. Grooming is a real service they are proud of, so give it a real section, not a footer line.
7. **Visit.** Address with a Google Maps link, phone (tel:), email (mailto:), hours placeholder, and the list of services (shop, pickup, curbside, delivery, grooming, bakery).

Skip: customer accounts, search, reviews widgets, blog, gift cards, wishlists, Instagram feeds, chat bubbles, cookie banners, announcement bars. If something above cannot be done well, drop it and say so in your report rather than shipping a weak version.

## Reference images (already in `images/reference/`)

These are the stock photos the current Shopify theme uses. They are Shopify Burst stock, free to reuse, but they are not the shop's own photos, so use them sparingly and never as the main hero.

| File | What it is | Suggested use |
|---|---|---|
| `hero-dog-walk-woods.jpg` | Two people and a dog walking a leafy trail in autumn, warm light. 4096px. | Could work as a band behind "Local delivery in Burlington and Oakville" or the grooming section. Not the hero. |
| `dog-awaiting-treat.jpg` | Studio portrait of a Bernese mountain dog on black, looking up. 3224x4096. | Strong. Hero candidate or the food-finder section. |
| `teddy-bear-dog.jpg` | Close crop of a golden retriever's face on dark navy. 2964x4096. | Strong. Hero candidate or treats section. |
| `black-dog-doorway.jpg` | Black lab mix grinning in a sunny back-door doorway. 4096px. | Curbside/pickup or grooming section. |
| `working-from-home.jpg` | Pug asleep on a bed beside a laptop. 4096px. | Pairs with the "Pets Are Part of the Family" copy or the auto-ship section. |
| `tile-1.png`, `tile-2.png`, `tile-3.png` | The three black line icons the current site uses: food bowl, paw print, leash. | Do not use. Draw your own inline SVG icons if you need any. |
| `current-site-fullpage.jpg` | Full-page screenshot of the existing Shopify store. | Look at it once so you know what we are beating. |

There are no photos of the actual shop, the groomer, or the bakery. Do not fake them. Where a section needs a visual and no photo fits, use type, colour, and product packshots.

## Design direction

The current site is the default Shopify "Debut" theme in Figtree with grey stock-photo bands. It reads as nobody's. The new one must read as **a neighbourhood pet shop run by people who read ingredient labels**: knowledgeable, warm, a bit playful, never cutesy.

- **Tone:** plain, friendly, specific. Talk about ingredients, Canadian brands, and the groomer by name of service. No "fur babies", no "pawsome", no puns in headings. One pun in a bakery product name is allowed.
- **Typography:** a rounded or soft-edged sans for headings with real personality (not Figtree, not Inter, not Poppins, not Nunito), paired with a highly legible sans or humanist serif for body and product data. Prices and sizes should sit in tabular figures.
- **Colour:** pick a two-colour identity and commit. Options that fit a pet shop on Appleby Line in autumn: a warm cream base with a deep forest green and a mustard accent, or a soft oat base with a brick red and navy. Avoid the pastel blue and the lime-green Shopify "Subscribe" button that the current site has. No gradients, no glassmorphism, no purple.
- **One memorable element.** Choose one and do it well: the Dog/Cat toggle as a big tactile switch that recolours the shop; the auto-ship card; or the food finder. Everything else stays disciplined.
- **Product cards:** the photo on a tinted plinth, name, brand in small text, price (or "from $X" when sized), one "good for" tag, and a quick-add button that is visible on touch devices without hover.
- **Motion:** quick-add confirmation, the bag count ticking up, dialogs opening. Nothing autoplaying, no scroll-in fades on every section.
- **No cookie banner, no "Powered by Shopify".**

### Page outline (single page, anchored nav, dialogs for product/bag/checkout)

1. **Header:** wordmark "Otis & Allen" (text; a small inline SVG paw or ampersand mark is fine if it's clean), nav: Shop, Food finder, Grooming, Visit, and a Bag button with count. Phone on desktop. Sticky.
2. **Hero:** headline in plain words about what they are and where. Direction: "Healthy food, honest treats, and a groomer your dog will actually like. Appleby Line, Burlington." Two CTAs: "Shop dog" / "Shop cat". One strong dog photo.
3. **Promise strip:** no wheat, corn or by-products in any food we carry; Canadian-sourced where possible; local delivery and curbside; grooming on-site.
4. **Shop:** pet toggle, chips, product grid, with "Sold out" and "Pickup only" states.
5. **Auto-ship explainer:** three lines, one card showing an example schedule, "Set it up in your bag".
6. **Food finder.**
7. **Grooming:** what it includes, how to request, the form.
8. **Bakery:** three or four made-in-store items, pickup only.
9. **Pets are part of the family:** their copy, the pug photo.
10. **Visit:** address, phone, email, hours placeholder, services, "Get directions" (`https://maps.google.com/?q=2500+Appleby+Line+Unit+D11+Burlington+ON`). No iframe map.
11. **Footer:** name, address, phone, email, Facebook link, newsletter line (demo only), "© 2026 Otis & Allen", "Website by STOHRX".

## Process

1. Read `../Coffeed/index.html` end to end. Note how it structures the catalogue array, the dialogs, the cart, and checkout validation. Reuse the patterns, not the styling.
2. Look at every file in `images/reference/`.
3. Fetch brand packshots, convert everything to webp into `images/` (Pillow, sharp, cwebp, or ImageMagick, whatever is on the machine), and record the commands and sources in a comment at the top of `index.html`.
4. Write `index.html`.
5. Test in a browser (Playwright if available) at 375, 768, 1280 and 1920: filters, product panel, sizes, autoship, bag persistence after reload, all three fulfilment paths including a declined postal code and a pickup-only conflict, food finder results, grooming form, and the menu on mobile. Screenshot each width.
6. Accessibility pass: heading order, alt text, contrast, keyboard access to every dialog and the pet toggle, focus returns to the trigger when a dialog closes, `aria-live` on the bag count and form messages.
7. Report what you built, what you verified with evidence, which products have real packshots vs. placeholders, and what is left as a placeholder (prices, hours, form endpoints).

Do not pad. Every section above should earn its place; if one does not, drop it and say so.
