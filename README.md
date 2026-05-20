# 🚑 RescueBus

> An ambulance booking web application built with HTML, CSS, Bootstrap, JavaScript, jQuery, and ASP.NET MVC.

---

## 📋 Project Overview

RescueBus is an emergency ambulance booking system built for the city of Townsville. The system allows citizens to book an ambulance by selecting a service type, choosing a driver and vehicle, and submitting their details. An SOS feature enables instant emergency bookings. All data is persisted using `localStorage`.

---

## ✨ Features

### 🏠 Home Page
- **Book Ambulance** button navigates to the service selection screen
- **S.O.S. button** instantly creates an emergency booking using a random available driver and vehicle, then redirects to the Booking Confirmed screen

### 🩺 Select a Service
Six clickable service options:
- Advanced Life Support (ALS)
- Basic Life Support (BLS)
- Patient Support
- Medical Utility Vehicle
- Event Medical Ambulance
- Air Ambulance

### 📝 Booking Form
- Displays the selected service name
- Fields: Full Name, Phone, Pick-Up Time, Reason, Vehicle (dropdown), Driver (dropdown), Pick-Up Address
- Vehicle and Driver dropdowns are filtered by the selected service type
- On submission, generates a **GUID** as the Booking ID, records the booking date, and saves everything to `localStorage`
- Redirects to the Booking Confirmed screen on success

### ✅ Booking Confirmed
- Displays full booking details: Booking ID (GUID), date booked, pick-up time, and pick-up address
- Shows driver details (name, phone number) with their photo
- Shows ambulance details (type, registration number) with its photo

### 📜 Ride History
- Lists all past bookings
- S.O.S. bookings are visually distinct from standard bookings
- Clicking a booking navigates to its Booking Confirmed details screen

### ⚙️ Driver & Vehicle Management (`/Manage`)
- Full **CRUD** (Create, Read, Update, Delete) for both Drivers and Vehicles
- Each driver and vehicle is associated with a specific service type and has a saved photo
- **Driver search** by first name and/or service type (fields can be left blank)
- **Vehicle export** to a `.txt` file
- Minimum of 10 pre-loaded drivers with varied names for search demonstration

---

## 🗂️ Application Structure

```
RescueBus/
├── App_Start/
├── Content/
│   ├── CSS/
│   │   └── styles.css
│   ├── HTML/
│   │   ├── bookingConfirmed.html
│   │   ├── bookingForm.html
│   │   ├── home.html
│   │   ├── manage.html
│   │   ├── rideHistory.html
│   │   └── selectService.html
│   ├── Images/
│   │   ├── ambulance1.jpg
│   │   └── ambulance2.jpg
│   ├── Javascript/
│   ├── Site.css
│   └── bootstrap.css (+ variants)
├── Controllers/
├── Properties/
├── Scripts/
├── Views/
├── Global.asax
├── Web.config
└── packages.config
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| ASP.NET MVC | Application framework |
| HTML5 & CSS3 | Structure and styling |
| Bootstrap | Responsive web design (RWD) |
| JavaScript & jQuery | DOM manipulation and interactivity |
| localStorage | Client-side data persistence |
| GUID generation | Unique Booking IDs |

---

## 🚀 Getting Started

1. Clone the repository
2. Open the `.sln` file in **Visual Studio**
3. Build and run the project (`F5` or `Ctrl+F5`)
4. Navigate to the Home page in your browser

> No database setup is required — all data is stored in `localStorage`.

---

## 📌 Notes

- Data is persisted in the browser's `localStorage`; clearing browser data will reset the application state
- Each driver and vehicle must be associated with exactly one service type — this drives the filtered dropdowns on the Booking Form
- The S.O.S. feature selects a random driver and vehicle regardless of service type
