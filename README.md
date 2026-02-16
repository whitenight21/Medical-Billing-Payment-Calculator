# Medical Billing - Payment Calculator

A simple, offline-friendly web tool designed for vision/medical billing staff (especially Davis Vision & Superior Vision claims) to quickly calculate patient responsibility vs. payments received and determine next steps (OK, Bill to Patient, or Refund).

https://github.com/whitenight21/payment-balance-calculator

## Features

- Enter **Patient Responsibility** amount
- Add as many **Payment** lines as needed (press Enter to create new field)
- Real-time calculation:
  - Total payments within **$9.99 under** → **OK**
  - More than $9.99 under → **Bill to Patient** + difference
  - Overpayment → **Refund** + negative amount
- One-click copy of the final amount (including negative for refunds)
- Quick-copy buttons for common insurance notes / denial reasons:
  - Davis Vision / Superior Vision responsibility & overpayment phrases (Exam, Lens, Frame, CLE, CL)
  - Generic phrases: "Not in EOB", "Keeping payment for claim", "CO-11", "Reversal payment", etc.
- Clean mobile-friendly layout (Davis buttons blue/left, Superior yellow/right)
- No backend, no login, works completely offline after first load

## Demo

You can try it live here:  
→ https://whitenight21.github.io/payment-balance-calculator/  

or just download `index.html` and open it in any browser.

## Usage

1. Open `index.html` in Chrome / Edge / Firefox / Safari
2. Enter the **Patient Responsibility** amount
3. Add payment amounts (press **Enter** after each to add more lines)
4. See instant result:
   - **OK** → green
   - **Bill to Patient** → green + amount to bill
   - **Refund** → red + negative amount
5. Click the big result button to copy the dollar amount (with `-` sign for refunds)
6. Use the blue/yellow buttons to copy full notes for claims/EFT comments

## Customization

All editable text lives in one object near the top of `index.html`:

```javascript
const TEXTS = {
  // change labels, full copied phrases, add/remove categories here
  categories: [
    { label: "Davis Exam",   davis: "...", superior: "..." },
    // ...
  ],
  // ...
}
