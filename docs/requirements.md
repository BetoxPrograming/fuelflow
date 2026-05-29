# ⛽ FuelFlow MVP — Requirements Documentation

## 📌 Overview

FuelFlow is a fuel consumption tracking application designed to provide more accurate fuel estimations than traditional vehicle dashboards.

The MVP focuses on:

* Vehicle fuel tracking
* Refill registration
* Fuel cost estimation
* Virtual tank estimation
* Historical fuel reports
* User-based vehicle management

> [!IMPORTANT]
>
> The user stories and requirements listed in this document are **not numbered in a perfectly sequential order**.
>
> During this first development stage (MVP Phase 1), some user stories and requirements were intentionally excluded to be implemented in a future second phase.
>
> Those omitted requirements and user stories are not included in this document for now and will be documented once Phase 2 development begins.

---

# 📖 User Stories

### HU-04 — Global Vehicle Report

As a user, I want to view a global vehicle report to understand the real fuel performance of my vehicle.



### HU-05 — Virtual Fuel Tank

As a user, I want to view a more accurate virtual fuel tank than the vehicle dashboard to better estimate the remaining fuel.



### HU-06 — Fuel Refill Registration

As a user, I want to register partial or full fuel refills to maintain a more accurate estimation of fuel consumption and remaining fuel.



### HU-08 — Vehicle Management

As a user, I want to register one or multiple vehicles to calculate fuel consumption independently for each one.



### HU-12 — User Authentication

As a user, I want to create an account and log into the system so my vehicles, refills, and reports are associated with my profile.



### HU-13 — User Profile Management

As a user, I want to create and edit my profile to keep my personal and access information updated.



# ⚙️ Functional Requirements

# EPIC RF-02 — Fuel Reports

## RF-02.2 — Global Vehicle Report

The global vehicle report must be calculated using the refill history of the selected vehicle.

The report must display:

* Total registered mileage
* Total liters refilled
* Accumulated fuel cost
* Average fuel performance
* Estimated autonomy in km/L
* Estimated virtual tank

---

## RF-02.3 — Report by Period

The application must allow the user to view the same information shown in the global vehicle report filtered by:

* Day
* Week
* Month
* Year

---

# EPIC RF-03 — Virtual Tank

## RF-03.1 — Virtual Tank Indicator

The application must display a visual virtual tank indicator showing:

* Estimated fuel percentage
* Estimated autonomy in kilometers
* Historical average fuel performance in km/L

---

## RF-03.2 — Historical Performance Adjustment

The application must recalculate the estimated autonomy using the historical average fuel performance of the vehicle.

---

# EPIC RF-04 — Fuel Refills

## RF-04.1 — Partial and Full Refill Registration

The application must allow registering partial or full fuel refills with:

* Date and time
* Liters refilled
* Price per liter
* Total paid
* Fuel type
* Vehicle
* Odometer

---

## RF-04.2 — Vehicle-Based Autocomplete

When registering a refill, the application must allow selecting a previously registered vehicle.

After selecting the vehicle, the application must automatically fill:

* Vehicle name
* Fuel type
* Tank capacity
* Estimated odometer

If the user only has one registered vehicle, the application must automatically select it.

The user must be able to manually modify any automatically filled value before saving the refill.

---

## RF-04.7 — Manual Fuel Price Registration

The application must allow manually registering the fuel price per liter for each refill.

---

# EPIC RF-05 — Vehicle Management

## RF-05.1 — Vehicle Registration

The application must allow registering:

* Vehicle name
* Brand
* Model
* Year
* Plate
* Initial odometer
* Tank capacity in liters
* Fuel type

---

## RF-05.3 — Manual Vehicle Data Editing

The application must allow manually editing vehicle information.

---

# EPIC RF-09 — User Authentication

## RF-09.1 — User Registration

The application must allow user registration using:

* Email
* Username
* Password

---

## RF-09.2 — User Login

The application must allow logging in using email and password.

---

## RF-09.3 — Secure Password Storage

Passwords must be stored using hash encryption instead of plain text.

---

## RF-09.8 — Secure Logout

The application must allow users to securely close their session.

---

## RF-09.9 — Password Recovery

The application must allow password recovery using the registered email address.

---

# EPIC RF-10 — User Profile Management

## RF-10.1 — User Profile Creation

The application must automatically create a user profile after successful registration.

---

## RF-10.2 — Profile Visualization

The application must allow viewing:

* Email
* Username
* Phone number

---

## RF-10.3 — Profile Editing

The application must allow editing:

* Username
* Phone number
* Password

---

## RF-10.4 — Email Modification

The application must allow changing the email address with confirmation of the new email.

---

## RF-10.6 — Password Change

The application must allow changing the password by requesting:

* Current password
* New password

---

## RF-10.7 — Profile Data Validation

The application must validate:

* Email format
* Phone number format
* Username format
* Password format

---

# 🛡️ Non-Functional Requirements

## RNF-01 — Usability

The application must provide a simple, visual, and fast interface for registering vehicles, fuel refills, and viewing reports.

---

## RNF-02 — Estimated Precision

All calculations must be presented as estimations instead of exact values.

---

## RNF-03 — Currency Support

The MVP must support:

* Costa Rican Colones (CRC)
* United States Dollars (USD)

---

## RNF-06 — Manual Data Editing

Any automatically calculated value must be manually editable by the user.

---

# 💼 Business Requirements

## RN-01 — Main Problem

The application aims to solve the lack of precision in vehicle fuel autonomy estimations.

---

## RN-02 — User Value

The application must help users understand how much fuel money is spent per:

* Trip
* Time period
* Vehicle

---

## RN-04 — MVP Scope

The first MVP must work without depending on:

* Waze
* Google Maps
* External navigation APIs

---

# 📚 Related Documentation

➡️ Next document: [Use Cases Documentation](use-cases.md)

This document contains the complete UML use case specifications and use case flows for the FuelFlow MVP.
