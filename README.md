# Tally Khata - Accounting & Ledger App

A modern Android application for maintaining business ledger and transaction records. Tally Khata helps small businesses and traders track their daily transactions, manage party accounts, and generate financial reports.

## Features

- 📊 **Transaction Management**: Record debit and credit transactions easily
- 👥 **Party Management**: Manage customers and vendors with opening balances
- 💰 **Balance Tracking**: Real-time display of total credits and debits
- 📈 **Reports**: Generate financial reports and analytics
- ⚙️ **Settings**: Customize app settings and preferences
- 🔒 **Data Security**: Local database storage with backup options
- 📱 **User-Friendly Interface**: Material Design UI with bottom navigation

## Tech Stack

- **Language**: Kotlin
- **Architecture**: MVVM with Repository Pattern
- **Database**: Room Database (SQLite)
- **UI Framework**: AndroidX, Material Design Components
- **Dependency Injection**: Hilt
- **Navigation**: Navigation Component
- **Async Programming**: Kotlin Coroutines
- **Reactive**: Flow and StateFlow

## Project Structure

```
app/src/main/
├── java/com/smarttech/tallykhata/
│   ├── ui/
│   │   ├── MainActivity.kt
│   │   ├── fragment/
│   │   │   ├── HomeFragment.kt
│   │   │   ├── TransactionsFragment.kt
│   │   │   ├── ReportsFragment.kt
│   │   │   └── SettingsFragment.kt
│   │   ├── viewmodel/
│   │   │   ├── TransactionViewModel.kt
│   │   │   └── PartyViewModel.kt
│   │   └── adapter/
│   │       └── TransactionAdapter.kt
│   ├── data/
│   │   ├── model/
│   │   │   ├── Transaction.kt
│   │   │   └── Party.kt
│   │   ├── database/
│   │   │   └── TallyDatabase.kt
│   │   ├── dao/
│   │   │   ├── TransactionDao.kt
│   │   │   └── PartyDao.kt
│   │   └── repository/
│   │       ├── TransactionRepository.kt
│   │       └── PartyRepository.kt
│   ├── di/
│   │   └── RepositoryModule.kt
│   └── TallyApp.kt
└── res/
    ├── layout/
    ├── values/
    ├── xml/
    ├── navigation/
    └── drawable/
```

## Getting Started

### Prerequisites

- Android Studio (Giraffe or later)
- Android SDK 21 or higher
- Gradle 8.1 or higher
- Java 11 or higher

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Smart-technology-bd/Tally-Khata.git
   cd Tally-Khata
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Click "Open" and select the project directory
   - Wait for Gradle sync to complete

3. **Build the Project**
   - Click Build → Make Project
   - Or use the keyboard shortcut Ctrl+F9 (Windows) / Cmd+F9 (Mac)

4. **Run the App**
   - Connect an Android device or start an emulator
   - Click Run → Run 'app'
   - Or use the keyboard shortcut Shift+F10

## Dependencies

Key dependencies included in the project:

- **AndroidX Core**: Core functionality
- **Material Design**: UI components
- **Room Database**: Local data persistence
- **Hilt**: Dependency injection
- **Navigation Component**: Fragment navigation
- **Kotlin Coroutines**: Async operations
- **LiveData & ViewModel**: MVVM architecture

## App Structure

### Home Screen
Displays:
- Total Credits
- Total Debits
- Quick action button to add transactions

### Transactions Screen
- List of all transactions
- Sortable by date, party, or type
- Tap to view/edit transaction details
- Swipe to delete

### Reports Screen
- Financial analytics
- Charts and graphs
- Period-wise analysis

### Settings Screen
- Business information
- App preferences
- Backup and restore functionality

## Database Schema

### Transactions Table
```sql
CREATE TABLE transactions (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    partyName TEXT NOT NULL,
    amount REAL NOT NULL,
    transactionType TEXT NOT NULL,
    description TEXT,
    date INTEGER NOT NULL,
    category TEXT,
    paymentMethod TEXT,
    referenceNumber TEXT,
    isReconciled INTEGER,
    tags TEXT
)
```

### Parties Table
```sql
CREATE TABLE parties (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL UNIQUE,
    phone TEXT,
    email TEXT,
    address TEXT,
    partyType TEXT,
    openingBalance REAL,
    createdAt INTEGER,
    isActive INTEGER
)
```

## Future Enhancements

- [ ] Export to Excel/PDF
- [ ] Cloud backup and sync
- [ ] Multi-user support
- [ ] Advanced filtering and search
- [ ] SMS/Email notifications
- [ ] Payment reminders
- [ ] Invoice generation
- [ ] Multi-language support
- [ ] Dark mode

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, email support@smarttech-bd.com or open an issue in the repository.

## Changelog

### Version 1.0.0
- Initial release
- Basic transaction management
- Party management
- Dashboard with totals
- Settings and preferences

## Author

**Smart Technology Bangladesh**
- Email: info@smarttech-bd.com
- GitHub: [Smart-technology-bd](https://github.com/Smart-technology-bd)

---

Made with ❤️ in Bangladesh
