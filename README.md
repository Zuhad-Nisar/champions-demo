<p align="center">
  <img src="logo.png" alt="Champions" width="150" />
</p>

<h3 align="center">Champions — Restaurant Ordering & Delivery App</h3>

<p align="center">
  Multi-branch restaurant app with menu browsing, cart, checkout, real-time order tracking, and admin management.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-In%20Development-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Flutter-Dart-02569B?style=flat-square&logo=flutter" />
  <img src="https://img.shields.io/badge/Firebase-Firestore-FFCA28?style=flat-square&logo=firebase" />
  <img src="https://img.shields.io/badge/Platforms-iOS%20%7C%20Android%20%7C%20Web-green?style=flat-square" />
</p>

> **This is a demo repository.** It showcases the architecture and features of Champions. The full source code is in a private repository. Screenshots coming soon.

---

## What Is Champions?

A complete restaurant ordering platform for a multi-branch food business. Customers select a branch, browse the menu, build a cart, checkout, and track their order in real-time. Owners manage everything from an admin panel.

---

## Features

### Customer Experience
- **Branch selection** — choose from multiple restaurant locations
- **Menu browsing** — categorised menu with item details, images, and descriptions
- **Item detail** — full item view with customisation options
- **Cart** — add, remove, adjust quantities with running total
- **Favourites** — save frequently ordered items
- **Checkout** — delivery details and order confirmation
- **Order tracking** — real-time status updates (Preparing → Ready → Delivered)
- **Order history** — view past orders with full details
- **Profile management** — edit name, phone, delivery address

### Admin
- **Admin panel** — manage menu items, branches, and orders
- **Order management** — update order status in real-time
- **Push notifications** — alert customers when order status changes

### Authentication
- **Firebase Auth** — email/password and Google sign-in
- **Persistent sessions** — stay logged in across app restarts

---

## Architecture

```
┌──────────────────────────────────────────────┐
│            FLUTTER APP (iOS/Android/Web)      │
│                                              │
│   Screens:                                   │
│   Splash → Auth → Branch Select → Home       │
│   → Menu → Item Detail → Cart → Checkout     │
│   → Confirmation → Order Tracking            │
│   → Orders History → Profile → Admin         │
│                                              │
│   State: Provider (7 providers)              │
└──────────────────┬───────────────────────────┘
                   │
         ┌─────────▼─────────┐
         │     FIREBASE       │
         │                    │
         │  Auth              │
         │  Firestore (DB)    │
         │  Cloud Functions   │
         │  Cloud Messaging   │
         └────────────────────┘
```

## App Structure

```
lib/
├── main.dart
├── firebase_options.dart
├── data/                    # Static data (menu items)
├── models/
│   ├── branch.dart          # Restaurant branch
│   ├── menu_item.dart       # Menu item with price, image, category
│   ├── cart_item.dart       # Cart entry with quantity
│   ├── order.dart           # Order with status tracking
│   └── user_profile.dart    # Customer profile
├── providers/
│   ├── auth_provider.dart       # Firebase Auth state
│   ├── branch_provider.dart     # Selected branch
│   ├── cart_provider.dart       # Cart management
│   ├── favourites_provider.dart # Saved items
│   ├── firebase_provider.dart   # Firestore access
│   ├── orders_provider.dart     # Order history & tracking
│   └── profile_provider.dart    # User profile
├── services/
│   ├── auth_service.dart            # Auth logic
│   ├── notification_service.dart    # Push notifications
│   ├── order_service.dart           # Order CRUD
│   ├── order_status_listener.dart   # Real-time order updates
│   └── profile_service.dart         # Profile CRUD
├── screens/
│   ├── splash/          # App launch
│   ├── auth/            # Sign in / Sign up
│   ├── branch_select/   # Choose restaurant branch
│   ├── home/            # Main landing page
│   ├── menu/            # Menu browsing
│   ├── item_detail/     # Item view + customisation
│   ├── cart/            # Shopping cart
│   ├── checkout/        # Delivery details
│   ├── confirmation/    # Order confirmed
│   ├── tracking/        # Live order status
│   ├── orders/          # Order history
│   ├── profile/         # User profile
│   └── admin/           # Admin management
├── router/              # App navigation
├── theme/               # Design tokens
└── widgets/             # Shared UI components
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| **Framework** | Flutter 3 (Dart) — iOS, Android, Web |
| **Auth** | Firebase Authentication |
| **Database** | Cloud Firestore |
| **Backend** | Firebase Cloud Functions (Node.js 20) |
| **Notifications** | Firebase Cloud Messaging |
| **State** | Provider pattern (7 providers) |
| **Security** | Firestore security rules |

---

## Contact

**Zuhad Nisar** — Full-Stack & Mobile App Developer (AI Enhanced)

[![Email](https://img.shields.io/badge/Email-Zuhadnisar@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:Zuhadnisar@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Zuhad--Nisar-181717?style=flat-square&logo=github)](https://github.com/Zuhad-Nisar)
