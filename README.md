# Byteforce 
NightBites — Surplus Night Food Deals
A self-contained web application where local food vendors post end-of-night surplus food deals with live closing countdowns, real-time stock tracking, coupon-code claiming, and automatic expiration.
Features
Vendor Deal Posting: Vendors can publish surplus bundles with kitchen name, dish title, category, original vs. surplus price, available portions, closing duration (including a 1-minute quick-test preset), and a custom or auto-generated coupon code.
Live Closing Countdown: Every active deal displays a second-by-second countdown timer (HH:MM:SS) with urgency indicators when under 15 minutes remain.
Real-Time Stock Display: Shows exact remaining portions alongside a visual progress bar that updates immediately as coupons are claimed.
Coupon Code Claiming: Customers claim a portion by entering and verifying the deal's coupon code in an in-page modal, generating a digital pickup pass with a unique redemption ID saved under My Coupons.
Automatic Expiration: Deals automatically transition to an expired state (Time Ended or Sold Out) and disable claiming the moment the closing timer hits zero or remaining stock reaches 0.
Search, Filtering & Persistence: Filter deals by status (Active, Expiring Soon, Expired) or food category, search by vendor or dish, and persist state in localStorage with a one-click demo reset.

Setup and run
The backend needs Python 3.10+, the frontend Node 18+. On first start the backend creates the database and loads demo data: 3 vendors and 8 live deals.
# Backend
cd backend
python -m venv venv
venv\Scripts\activate          # Mac/Linux: source venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000

 If using VS code, run this
 
 cd backend
py -m pip install -r requirements.txt
py -m uvicorn app.main:app --reload

# Frontend (dev mode, new terminal)
cd frontend
npm install
npm run dev                     # http://localhost:5173
The built React app is included in frontend/dist, so http://localhost:8000 alone also serves the full app. Demo vendor login: demo@nightbites.in / demo123. Reset demo data with python -m app.seed --reset from backend/.

