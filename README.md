# WalletTracker

A cross-platform personal finance management application built with .NET MAUI and Blazor. Track your credits, debits, and debts with an intuitive interface.

## Overview

WalletTracker is a desktop and mobile application that helps you manage your personal finances. It allows you to track income (credits), expenses (debits), and debts, while maintaining a complete transaction history.

## Features

### User Management
- User registration with secure password hashing
- User authentication and login
- Session management

### Financial Tracking
- Credit Management: Add and track income
- Debit Management: Record expenses with balance validation
- Debt Management: Track debts and clear them when credit is available
- Transaction History: View all transactions with filtering and sorting capabilities

### Transaction Features
- Filter transactions by type (Credit, Debit, Debt)
- Filter transactions by tags (Salary, Groceries, Rent, etc.)
- Search transactions by description
- Sort transactions by date
- Export transactions to PDF
- Export transactions to Excel
- View highest transactions (above 10,000)
- View lowest transactions (below 500)
- Clear transaction history

### User Interface
- Responsive design with Bootstrap
- Modern card-based dashboard
- Real-time balance updates
- Search and filter functionality

## Technology Stack

- .NET 9.0
- .NET MAUI (Multi-platform App UI)
- Blazor WebView
- C# 12
- Bootstrap 5
- JavaScript (for PDF and Excel export)

## Supported Platforms

- Windows 10/11
- Android
- iOS
- macOS (Mac Catalyst)

## Prerequisites

- .NET 9.0 SDK or later
- Visual Studio 2022 (17.8 or later) with MAUI workload, or
- Visual Studio Code with C# extension and .NET MAUI extension
- For Android development: Android SDK
- For iOS development: macOS with Xcode
- For Windows development: Windows 10 SDK

## Installation

1. Clone the repository or download the source code
2. Open the solution file (wallettracker.sln) in Visual Studio
3. Restore NuGet packages
4. Select your target platform (Windows, Android, iOS, or Mac Catalyst)
5. Build and run the application

## Building the Project

### Using Visual Studio
1. Open wallettracker.sln
2. Select your target platform from the dropdown
3. Press F5 to build and run

### Using Command Line
```bash
dotnet restore
dotnet build
dotnet run
```

## Project Structure

```
walletTracker/
├── Components/
│   ├── Layout/
│   │   ├── FirstLayout.razor
│   │   ├── MainLayout.razor
│   │   └── NavMenu.razor
│   └── Pages/
│       ├── Dashboard.razor
│       ├── Login.razor
│       ├── Register.razor
│       └── Transaction.razor
├── Models/
│   ├── Transaction.cs
│   └── User.cs
├── Services/
│   └── UserService.cs
├── Platforms/
│   ├── Android/
│   ├── iOS/
│   ├── MacCatalyst/
│   └── Windows/
├── Resources/
│   ├── AppIcon/
│   ├── Fonts/
│   └── Images/
├── wwwroot/
│   ├── css/
│   └── index.html
├── App.xaml
├── App.xaml.cs
├── MainPage.xaml
├── MainPage.xaml.cs
├── MauiProgram.cs
└── practice.csproj
```

## Data Storage

The application stores user data locally in JSON format. The data file is located at:
- Windows: Desktop\LocalDB\users.json
- Other platforms: Platform-specific local storage

All passwords are hashed using SHA256 before storage.

## Usage

### Registration
1. Launch the application
2. Click on "Don't have an account? Signup"
3. Enter username, email (optional), and password
4. Click "Signup"
5. You will be redirected to the login page

### Login
1. Enter your username and password
2. Click "Signin"
3. You will be redirected to the dashboard

### Adding Credit
1. On the dashboard, click "Add Credit" on the Credit card
2. Enter the credit amount
3. Select a tag (Salary, Others)
4. Add optional remarks
5. Click "Submit"

### Adding Debit
1. On the dashboard, click "Add Debit" on the Debit card
2. Enter the debit amount (must not exceed credit balance)
3. Select a tag (Groceries, Rent, Others)
4. Add optional remarks
5. Click "Submit"

### Adding Debt
1. On the dashboard, click "Add Debt" on the Debt card
2. Enter the debt amount
3. Select a tag (Loan, Credit Card, Others)
4. Add optional remarks
5. Click "Submit"

### Clearing Debt
1. On the dashboard, click "Clear Debt" on the Debt card
2. The debt will be cleared if you have sufficient credit balance

### Viewing Transactions
1. Navigate to "Transaction Table" from the menu
2. Use the search box to filter by description
3. Use the type filter dropdown to filter by transaction type
4. Use the tag filter dropdown to filter by tag
5. Click on "Transaction Date" header to sort by date
6. Click "Download Table in pdf" to export as PDF
7. Click "Download Table in excel" to export as Excel

### Logging Out
1. Click "Signout" from the navigation menu
2. You will be redirected to the login page

## Security Features

- Password hashing using SHA256
- Input validation on all forms
- Balance validation before debits
- Secure file-based storage

## Known Limitations

- Data is stored locally only (no cloud sync)
- No multi-device synchronization
- No data backup/restore feature
- No password recovery mechanism

## Development Notes

### Code Organization
- Models: Data structures for User and Transaction
- Services: Business logic in UserService
- Components: Blazor components for UI
- Platforms: Platform-specific configurations

### Key Components
- UserService: Handles all user and transaction operations
- Dashboard: Main financial overview page
- Transaction: Transaction history and filtering page
- Login/Register: Authentication pages

## Troubleshooting

### Build Errors
- Ensure .NET 9.0 SDK is installed
- Verify MAUI workload is installed: `dotnet workload install maui`
- Clean and rebuild the solution

### Runtime Errors
- Check that the LocalDB folder has write permissions
- Verify all NuGet packages are restored
- Check platform-specific requirements

### Data Issues
- User data is stored in Desktop\LocalDB\users.json
- If data is corrupted, delete the users.json file (all data will be lost)
- Ensure the application has file system permissions

## Future Enhancements

Potential improvements for future versions:
- Cloud synchronization
- Data backup and restore
- Password recovery
- Budget planning
- Financial reports and analytics
- Recurring transactions
- Categories and subcategories
- Multi-currency support
- Dark mode theme

## License

This project is provided as-is for educational and personal use.

## Version

Current Version: 1.0

## Support

For issues or questions, please refer to the project repository or create an issue in the issue tracker.

