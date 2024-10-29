# Lottery Pool Smart Contract

# About
This smart contract implements a decentralized lottery system on the Stacks blockchain. It allows for creating and managing lotteries, selling tickets, selecting winners, and distributing prizes.

## Features

- Create new lotteries with customizable parameters
- Purchase lottery tickets
- Withdraw tickets during a specified period
- Automatically end lotteries and select winners
- Claim prizes for winners
- Read-only functions for querying lottery state

## Contract Functions

### Administrative Functions

- `start-new-lottery`: Initializes a new lottery with specified parameters.
- `end-current-lottery`: Ends the current lottery and calculates prizes.
- `select-winners`: Selects winners for the ended lottery.

### User Functions

- `purchase-lottery-ticket`: Allows users to buy lottery tickets.
- `withdraw-tickets`: Enables users to withdraw their tickets during the withdrawal period.
- `claim-prize`: Allows winners to claim their prizes.

### Read-Only Functions

- `get-current-ticket-price`: Returns the current ticket price.
- `get-current-lottery-pot`: Returns the total amount in the lottery pot.
- `get-user-ticket-count`: Returns the number of tickets owned by a user.
- `get-total-tickets-sold`: Returns the total number of tickets sold.
- `check-if-lottery-is-active`: Checks if a lottery is currently active.
- `get-lottery-end-block-height`: Returns the block height when the lottery ends.
- `get-withdrawal-end-block-height`: Returns the block height when ticket withdrawals end.
- `get-organizer-fee-percentage`: Returns the organizer's fee percentage.
- `get-winner-info`: Returns information about a specific winner.
- `are-winners-selected`: Checks if winners have been selected for the current lottery.

## Usage

1. Deploy the contract to the Stacks blockchain.
2. Use the `start-new-lottery` function to initialize a new lottery.
3. Users can purchase tickets using the `purchase-lottery-ticket` function.
4. Users can withdraw tickets during the withdrawal period using `withdraw-tickets`.
5. After the lottery end time, the contract owner can end the lottery using `end-current-lottery`.
6. The contract owner then selects winners using `select-winners`.
7. Winners can claim their prizes using the `claim-prize` function.

## Error Handling

The contract includes various error codes for different scenarios:

- `ERR_NOT_AUTHORIZED`: User is not authorized to perform the action.
- `ERR_LOTTERY_INACTIVE`: The lottery is not active.
- `ERR_INSUFFICIENT_BALANCE`: User has insufficient balance.
- `ERR_INVALID_TICKET_PRICE`: The ticket price is invalid.
- `ERR_NO_WINNERS`: No winners could be selected.
- `ERR_NO_TICKETS`: User has no tickets to withdraw.
- `ERR_WITHDRAWAL_PERIOD_ENDED`: The withdrawal period has ended.
- `ERR_LOTTERY_NOT_ENDED`: The lottery has not ended yet.
- `ERR_WINNERS_ALREADY_SELECTED`: Winners have already been selected.

## Security Considerations

- The contract uses various checks to ensure only authorized actions are performed.
- Random winner selection is based on a provided seed and the block height.
- There's a maximum fee percentage (20%) to prevent excessive fees.

## Development and Testing

To develop and test this contract:

1. Set up a Stacks development environment.
2. Use Clarinet for local testing and deployment.
3. Write unit tests to cover all contract functions and edge cases.
4. Deploy to testnet before mainnet for thorough testing.