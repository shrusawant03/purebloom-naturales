# PureBloom Naturales

A responsive e-commerce web application for natural skincare, haircare, body care, baby care and wellness products. It includes a shopping cart, a multi-step checkout, a face-scan skin analyzer and an AI-style product suggester, all built with plain HTML, CSS and JavaScript.

> Live demo: add your GitHub Pages link here after you enable it (see "Deploy" below).

## Features

**Shopping**
- 22 products across 5 categories: Face Care, Hair Care, Body Care, Baby Care and Wellness
- Search, category filters and sorting (popular, price low to high, price high to low, biggest discount)
- Product cards with price, MRP, discount badge, size and key ingredients
- Shopping cart with quantity controls, free-shipping progress bar and coupon codes
- Cart is saved in the browser, so it survives a page refresh

**Checkout**
- Delivery details form with validation (name, 10 digit mobile number, email, PIN code)
- Payment options: UPI, Card and Cash on Delivery
- Card number check (Luhn algorithm), expiry date check and UPI ID format check
- Order confirmation with order ID and estimated delivery date
- The payment step is a simulation. No real money is charged.

**AI Studio**
- **Face scan:** upload a photo and the app finds the face, then estimates oiliness, dryness, redness, dullness and uneven tone. It suggests your skin type and matching products.
- **Product suggester:** choose a category, concerns, skin type and budget to get the top matching products with the reason for each pick.
- The scan runs entirely in the browser. Photos are never uploaded or stored.

**Design**
- Mobile-first responsive layout
- Automatic light and dark theme
- Keyboard-friendly with visible focus states and ARIA labels
- Product packaging is drawn with inline SVG, so no image files are needed

## Tech Stack

| Area | Technology |
| --- | --- |
| Structure | HTML5 |
| Styling | CSS3 (Grid, Flexbox, CSS variables) |
| Logic | JavaScript (ES6), no frameworks |
| Graphics | SVG |
| Image analysis | Canvas API, FaceDetector API (where the browser supports it) |
| Storage | localStorage |
| Fonts | Google Fonts (Bricolage Grotesque, Figtree) |

## How It Works

- **Recommendation engine:** every product has tags for skin types and concerns. Each product is scored against the user's answers (concern match, skin type match, category and budget), and the highest scores are shown.
- **Face scan:** the photo is drawn to a canvas. The app locates the face (using the browser's FaceDetector when available, otherwise the centre of the image), keeps only skin-coloured pixels using YCbCr colour ranges, then measures brightness, highlights and colour variation to estimate each skin score.
- **Cart and checkout:** cart state is kept in a JavaScript object and mirrored to localStorage. Totals, discounts and shipping are recalculated on every change.

## Run Locally

No installation is needed.

1. Download or clone this repository.
2. Open `index.html` in any modern browser (Chrome or Edge recommended).

An internet connection is only needed to load the Google Fonts.

## Deploy (free live link)

1. Push this repository to GitHub.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and the `/ (root)` folder, then save.
4. After a minute, your site will be live at `https://<your-username>.github.io/<repository-name>/`.

## Coupon Codes (for testing)

| Code | Offer |
| --- | --- |
| `PURE10` | 10% off the order |
| `BLOOM100` | Rs. 100 off orders of Rs. 699 or more |

Free shipping applies to orders of Rs. 499 or more. Otherwise shipping is Rs. 49.

## Limitations

- There is no backend or database. Products are stored in the JavaScript file, and orders are not saved anywhere.
- Payments are simulated. A real launch needs a payment gateway such as Razorpay, Cashfree or Stripe plus a server to create and verify orders.
- The skin scan is a lightweight image-analysis estimate, not a trained machine-learning model or a medical diagnosis. Lighting and camera quality affect the results.
- Browsers without a built-in FaceDetector use the centre of the photo instead of detecting the face.

## Future Improvements

- Node.js and Express backend with a database (MongoDB or MySQL) for products, users and orders
- User accounts, order history and wishlist
- Real payment gateway integration
- A trained face and skin-condition model (for example TensorFlow.js)
- Product reviews and an admin dashboard

## Author

**Shrusti Sandeep Sawant**
B.Sc. Information Technology, VIVA College
LinkedIn: [linkedin.com/in/shrusti-sawant-15b94441b](https://linkedin.com/in/shrusti-sawant-15b94441b)
GitHub: [github.com/shrusawant03](https://github.com/shrusawant03)
