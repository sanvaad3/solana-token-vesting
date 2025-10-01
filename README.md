# Solana Token Vesting

A secure, decentralized token vesting platform built on Solana that enables companies to create time-locked token distributions for employees with cliff periods and linear vesting schedules.

## Features

- **Company Vesting Programs**: Create custom vesting accounts for organizations
- **Employee Token Allocation**: Distribute tokens to employees with customizable vesting schedules
- **Cliff Periods**: Enforce minimum vesting periods before tokens become claimable
- **Linear Vesting**: Gradual token release over specified time periods
- **Secure Claims**: Employees can safely claim vested tokens through the web interface
- **Treasury Management**: Automated treasury token account management

## Architecture

This project uses an Nx monorepo structure with:

- **Smart Contract** (`anchor/`): Rust-based Anchor program handling vesting logic
- **Frontend** (`web/`): Next.js web application for interacting with the vesting program
- **Shared Types**: TypeScript definitions generated from the Anchor program

## Smart Contract Features

### Instructions

1. **Create Vesting Account**: Initialize a company's vesting program
2. **Create Employee Vesting**: Set up individual employee vesting schedules
3. **Claim Tokens**: Allow employees to withdraw vested tokens

### Account Structure

- **VestingAccount**: Stores company information and treasury details
- **EmployeeAccount**: Tracks individual employee vesting schedules and claim history

## Quick Start

### Prerequisites

- Node.js 18+
- Rust and Cargo
- Solana CLI tools
- Anchor CLI

### Installation

```bash
# Install dependencies
npm install

# Build the Anchor program
npm run anchor-build

# Start local Solana validator (in a separate terminal)
npm run anchor-localnet

# Deploy to localnet
npm run anchor

# Start the web development server
npm run dev
```

### Testing

```bash
# Run Anchor program tests
npm run anchor-test

# Build the web application
npm run build
```

## Usage

### For Companies

1. Connect your Solana wallet to the web interface
2. Create a vesting account with your company name
3. Fund the treasury with the tokens you want to vest
4. Create employee vesting schedules with:
   - Start and end dates
   - Total token allocation
   - Cliff period

### For Employees

1. Connect your Solana wallet
2. View your vesting schedule and available tokens
3. Claim vested tokens that have passed the cliff period

## Security Features

- **Cliff Protection**: Tokens cannot be claimed before the cliff period expires
- **Proportional Vesting**: Only vested portions can be claimed based on elapsed time
- **Owner Verification**: Only account owners can create employee vesting schedules
- **Beneficiary Verification**: Only designated beneficiaries can claim their tokens

## Program ID

```
GFdLg11UBR8ZeePW43ZyD1gY4z4UQ96LPa22YBgnn4z8
```

## Development

### Project Structure

```
├── anchor/               # Anchor workspace
│   ├── programs/vesting/ # Smart contract source
│   └── tests/           # Program tests
├── web/                 # Next.js frontend
└── package.json         # Root package with scripts
```

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build production application
- `npm run anchor-build` - Build Anchor program
- `npm run anchor-test` - Run program tests
- `npm run anchor-localnet` - Start local Solana cluster

## License

MIT License - see [LICENSE](LICENSE) for details.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## Support

For questions and support, please open an issue in the GitHub repository.
