# BubbleBlizz — Beverage Ordering Android Application

<div align="center">

  **A Modern Beverage Shopping Experience**

  A native Android application for exploring drinks, managing a shopping cart, saving favourites, and navigating a multi-step checkout experience.

  **Built with Kotlin and Jetpack Compose**

</div>

---

## 🌟 Overview

BubbleBlizz is an Android beverage-ordering application designed to provide users with a convenient way to browse drinks, explore product details, organise favourites, and move through a checkout workflow.

The application uses Kotlin and Jetpack Compose to build its user interface. Its screen-based architecture separates the main shopping experience into reusable UI components, individual screens, navigation routes, and supporting data stores.

The project demonstrates Android UI development, state management, navigation, product catalogues, and shopping-cart workflows.

## ✨ Key Features

### 🔐 Authentication Interface
- Login screen with email and password fields.
- Registration screen with name, email, and password fields.
- Password input masking.
- Navigation between login and registration screens.
- Splash screen as the application entry point.

*The inspected screens use navigation callbacks; working server-backed authentication has not been verified.*

### 🥤 Beverage Catalogue
- Product catalogue containing fruit juices, dairy drinks, soft drinks, and energy drinks.
- Product names, descriptions, sizes, prices, and ratings.
- Category-based menu navigation.
- Product detail screens.
- Product images stored in Android drawable resources.

### 🛒 Shopping Cart
- Add products to the cart.
- Increase quantities of existing cart items.
- Update item quantities.
- Remove products from the cart.
- Calculate the cart total from item prices and quantities.

### ❤️ Favourites
- Add and remove favourite products.
- Track saved items within the application's current state.
- Access a dedicated favourites screen.

### 📦 Checkout Workflow
The application includes a multi-step checkout experience:

1. **Shipping details** — enter delivery information.
2. **Payment selection** — navigate through the payment-method screen.
3. **Order review** — review the checkout information.
4. **Order details** — display an order summary when available.

The source includes payment-method options for card, PayPal, and Google Pay. Actual payment processing has not been verified.

### 👤 Profile Management
- Profile screen.
- Edit-profile screen.
- Profile information represented through a local state store.
- Navigation for account and logout-related actions.

### 🎨 User Interface
- Jetpack Compose declarative UI.
- Material Design 3 components.
- Custom reusable UI elements.
- Theme and colour configuration.
- Screen navigation using Navigation Compose.
- Scrollable authentication forms for smaller screens.

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| Kotlin | Android application development |
| Android SDK | Native Android platform |
| Jetpack Compose | Declarative user interface |
| Material Design 3 | UI components and visual styling |
| Navigation Compose | Navigation between application screens |
| ViewModel / Compose state APIs | UI state and theme-related state management |
| Gradle Kotlin DSL | Build configuration |
| Android Studio | Recommended development environment |

## 🏗️ Technical Architecture

### Application Architecture

BubbleBlizz separates navigation, screens, shared components, theme resources, product models, and state stores.

```text
Android Application
        |
        v
MainActivity / App Entry
        |
        v
Navigation Compose
        |
        +---- Authentication Screens
        |
        +---- Home and Product Catalogue
        |
        +---- Product Details
        |
        +---- Cart and Favourites
        |
        +---- Checkout and Order Details
        |
        +---- Profile Management
        |
        v
Local Application State Stores
```

This diagram represents the structure visible in the source code. It does not imply that a remote backend, persistent database, or payment service is connected.

### Navigation

The navigation graph defines routes for:

- Splash
- Login and registration
- Home and category menus
- Product details
- Cart and favourites
- Profile and edit profile
- Shipping, payment, and checkout review
- Order details

Navigation Compose manages transitions between these destinations.

### State Management

The project contains dedicated stores for several application data areas:

- `CartStore` — shopping-cart items, quantities, and totals.
- `FavoritesStore` — saved favourite products.
- `CheckoutStore` — shipping details and selected payment method.
- `UserStore` — profile information.
- `Orders` — the most recent order summary.
- `Catalog` — predefined product data.

The inspected stores use in-memory Compose state. Persistent storage across application restarts has not been verified.

## 📁 Project Structure

```text
BubbleBlizz/
├── app/
│   ├── build.gradle.kts
│   ├── proguard-rules.pro
│   └── src/
│       └── main/
│           ├── AndroidManifest.xml
│           ├── java/
│           │   └── com/example/bubbleblizz/
│           │       ├── App.kt
│           │       ├── MainActivity.kt
│           │       ├── navigation/
│           │       │   └── Nav.kt
│           │       ├── ui/
│           │       │   ├── component/
│           │       │   ├── screen/
│           │       │   ├── assets/
│           │       │   └── theme/
│           │       └── util/
│           │           ├── Catalog.kt
│           │           ├── Product.kt
│           │           ├── Store.kt
│           │           ├── FavoritesStore.kt
│           │           ├── CheckoutStore.kt
│           │           └── UserStore.kt
│           └── res/
│               └── drawable/
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Android Studio.
- A compatible JDK, with Java 17 configured for compilation.
- Android SDK Platform 34.
- An Android emulator or compatible Android device.
- Gradle wrapper files, if included in the repository.

### 1. Clone the Repository

```bash
git clone https://github.com/sahan721/BubbleBlizzApp-flutter-.git
cd BubbleBlizzApp-flutter-
```

### 2. Open the Project

Open the project root directory in Android Studio and allow Gradle to synchronise the project dependencies.

### 3. Configure the Android SDK

The application configuration specifies:

- Compile SDK: 34
- Target SDK: 34
- Minimum SDK: 24
- Java compatibility: 17
- Kotlin JVM target: 17

Install the required Android SDK components if they are not already available.

### 4. Run the Application

Select an Android emulator or connected device in Android Studio and run the `app` configuration.

If the Gradle wrapper is included, the application can also be built from the terminal using the appropriate Gradle wrapper command for your operating system.

*These instructions are based on the uploaded Gradle configuration. A clean build and runtime test have not been independently performed.*

## 🧭 Application Workflow

### 1. Entry and Authentication
The application opens through a splash screen and navigates to the login interface. A registration screen is available from the login flow.

### 2. Browse Products
Users can navigate to the home screen, explore beverage categories, and open product details.

### 3. Manage Shopping Items
Products can be added to the cart, quantities can be changed, and items can be removed. A separate favourites area is also provided.

### 4. Complete the Checkout Flow
The checkout screens collect shipping details, provide payment-method options, and navigate to an order-review screen and order-details screen.

### 5. Manage Profile Information
Users can navigate to profile and edit-profile screens.

These steps describe the application's source-defined navigation and UI workflows, not a verified production ordering service.

## 🧪 Testing and Verification

The uploaded project source contains application screens, navigation definitions, product data, and local state stores.

The following areas should be verified through manual or automated testing:

- Login and registration validation.
- Product category navigation.
- Product detail rendering.
- Cart quantity and total calculations.
- Favourite-item management.
- Checkout field validation.
- Payment selection behaviour.
- Order-summary consistency.
- Profile updates.
- State behaviour after the application restarts.

No successful build or comprehensive test results are claimed in this documentation.

## 🔐 Security and Production Considerations

Before using BubbleBlizz as a production ordering application, consider:

- Integrating a secure authentication service.
- Connecting the catalogue and order workflows to a backend where required.
- Persisting cart and profile data appropriately.
- Using a trusted payment provider for real transactions.
- Validating orders and prices on the server.
- Protecting personal and delivery information.
- Testing navigation, input validation, and error states.

The current source inspection does not establish that these production services are implemented.

## 🗺️ Future Improvements

- [ ] Connect authentication to a real backend.
- [ ] Integrate a persistent product catalogue and order service.
- [ ] Add order history and persistent cart storage.
- [ ] Integrate a verified payment gateway.
- [ ] Add product search and sorting.
- [ ] Improve form validation and error handling.
- [ ] Add automated UI and unit tests.
- [ ] Add screenshots and a demonstration video.
- [ ] Document verified backend integration, if applicable.

These items are potential enhancements, not claims of existing functionality.

## 📜 License

No licence has been confirmed from the inspected project files. Review the repository's licence before redistributing or reusing the source code.

## 👨‍💻 Author

**Sahan Nimnaka**

GitHub: [@sahan721](https://github.com/sahan721)

Repository: [BubbleBlizz Android Application](https://github.com/sahan721/BubbleBlizzApp-flutter-)

---

<div align="center">

**BubbleBlizz — Beverage Ordering Android Application**

*Built with Kotlin, Jetpack Compose, and Material Design 3.*

</div>
