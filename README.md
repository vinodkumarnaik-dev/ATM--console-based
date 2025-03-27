# ATM Operations - Console Based Application

## Overview
This is a simple console-based ATM operations application implemented using only control and conditional statements along with the dictionary data type to store user details. The project supports essential ATM functions, including deposit, withdrawal, PIN generation, and mini statement retrieval.

## Features
- **Deposit Money**: Allows users to deposit money into their account.
- **Withdraw Money**: Enables users to withdraw money if sufficient balance is available.
- **PIN Generation**: Users can generate or change their ATM PIN securely.
- **Mini Statement**: Displays the last few transactions made by the user.
- **Console-Based Interface**: Simple text-based interface for easy interaction.

## Technologies Used
- Python (without external libraries, using only built-in control structures and dictionaries)

## How to Run
1. Clone the repository:
   ```sh
   git clone <repository_url>
   ```
2. Navigate to the project directory:
   ```sh
   cd <project_folder>
   ```
3. Run the script:
   ```sh
   python atm.py
   ```
4. Follow the on-screen instructions to perform ATM operations.

## Project Structure
```
├── atm.py               # Main script with ATM operations
├── README.md            # Project documentation
└── transactions.json    # (If applicable) Stores user transaction data
```

## Future Enhancements
- Implementing file/database storage for persistence.
- Adding user authentication for security.
- Enhancing the UI with a graphical interface.

## Contributing
Contributions are welcome! If you want to improve this project, feel free to fork the repository and submit a pull request.

## License
This project is open-source and available under the [MIT License](LICENSE).

