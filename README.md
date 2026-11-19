# RYS Camera Rental Management System

A front-end-only prototype built with HTML5, CSS3, vanilla JavaScript, LocalStorage, and the browser File API. No framework or build process is required.

## Run locally
1. Extract the `RYS-Camera-Rental` folder.
2. Open the folder in Visual Studio Code.
3. Install/enable the **Live Server** extension if needed.
4. Right-click `index.html` and choose **Open with Live Server**.
5. Public visitors start at the home page. There is no customer login or registration.

## Demo administrator access
Open the direct URL `admin-login.html` through the same Live Server origin.
- Username: `admin@ryscamerarental.local`
- Password: `RYSdemo2026!`

The admin login is intentionally not linked from the public site. The direct URL is not a security boundary. Authentication is simulated in the browser and must not be used for real customer information.

## Main files
- `index.html` — public home, catalog, about, contact.
- `equipment-details.html` — equipment detail and date check.
- `booking.html` — booking request, price estimate, mock ID selection.
- `track-booking.html` — reference + email booking lookup.
- `admin-login.html` / `admin.html` — separate demo admin interface.
- `js/main.js` — shared LocalStorage data model and helpers.
- `js/equipment.js`, `js/booking.js`, `js/tracking.js` — public interactions.
- `js/auth.js`, `js/admin.js` — admin session and management.

## Prototype behavior and limitations
- Sample equipment is initialized once. Changes persist in the same browser and origin.
- Customer booking requests begin as **Pending**. Approval requires the mock ID status to be **Verified** and an availability check.
- Selected ID file contents are not uploaded or saved. Only filename and mock status are stored.
- This prototype does not collect payment or verify real identity documents.
- Browser LocalStorage is not a secure database. A production system requires a backend, server-side authorization, secure authentication, and protected document storage.
- Demo data can be reset from Admin → Settings.
- Equipment photos use remote Unsplash URLs and need internet access. If unavailable, a fallback photo is used.

## Test checklist
1. Browse and filter equipment from the public home page.
2. Open an item, choose dates, and continue to booking.
3. Submit a booking without an account; note its reference.
4. Track using both the reference and the exact email used on the booking.
5. Open `admin-login.html` directly and sign in.
6. In Booking Management, verify the ID status then approve (if dates are available), or reject with a remark.
7. Check the customer tracking page again to see the changed status.
8. Add equipment and check that it appears in the public catalog.
9. Release approved equipment, then record a return and condition inspection.
10. Sign out; `admin.html` should redirect to the login page.


### Public navigation update
The homepage now focuses on the RYS introduction, how-it-works, and contact information. The complete equipment catalog is on `equipment.html` and opens when visitors click **Explore Equipment** or **equipment** in the navigation.
