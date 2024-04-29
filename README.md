# Distributions-demo
Smart contract for closed-end fund distributions on Canton blockchain network.

# Overview
This repository contains the DAML codebase for a closed-end fund distribution system designed to run on the Canton blockchain network. The system allows for the automated distribution of dividends from tokenized alternative assets managed within a closed-end fund structure.

# Components
The repository consists of the following primary components:
1. ClosedEndFund Template: Manages the fund's operations including investor registration, asset tracking, and dividend distributions.
2. DividendPayment Template: Handles individual dividend payments to investors, allowing for acknowledgment and archival of payment records.

# Explanation of Code
1. ClosedEndFund Template: This template models the closed-end fund itself. It includes:
  - issuer: The party who issues and manages the fund.
  - investors: A list of parties who have invested in the fund.
  - assetValuation: The current valuation of the fund's assets.
  - dividendAmount: The amount of money each investor receives as a dividend.

2. DistributeDividends Choice: This choice allows the fund's issuer to distribute dividends to all investors. It iterates over the list of investors and creates a new DividendPayment contract for each investor.

3. DividendPayment Template: Represents an individual payment of dividends to an investor.
  - payee: The investor receiving the dividend.
  - amount: The amount of dividend being paid.
  - AcknowledgeReceipt: A choice that allows the payee to acknowledge the receipt of the dividend. This action archives the DividendPayment contract to keep the ledger clean.

# Use Cases
1. The issuer of the fund can execute the DistributeDividends choice to send dividends to all registered investors.
2. Each investor receives a DividendPayment contract which they can acknowledge, thus confirming receipt of their dividend.
