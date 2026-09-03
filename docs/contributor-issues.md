# Contributor Issues

These are ready-to-publish issues for the Escrowly MVP. Each issue is intentionally scoped so a contributor can work independently.

## 1. Add a New Deal Form

**Labels:** `feature`, `good first issue`

Build the form opened by the **New deal** button. Capture project name, client name, total amount, asset, and milestone names and amounts.

**Acceptance criteria**
- Form opens without leaving the dashboard.
- Required fields show accessible validation messages.
- A valid submission adds the new deal to the active deals list.
- Cancel and close actions discard unsaved values.

## 2. Connect Freighter Wallet

**Labels:** `feature`, `stellar`, `help wanted`

Add wallet connection using Freighter or the current recommended Stellar wallet interface.

**Acceptance criteria**
- User can connect and disconnect a wallet.
- The truncated public key is visible after connection.
- The UI handles a rejected request and an unavailable wallet gracefully.
- No secret keys are requested or stored.

## 3. Create the Soroban Escrow Contract

**Labels:** `feature`, `soroban`, `smart contract`

Create a Soroban contract that stores client, freelancer, asset, amount, milestones, and escrow status.

**Acceptance criteria**
- Contract supports initialization with two parties and milestone amounts.
- Funds can only be deposited into an active escrow.
- Contract state is covered by unit tests.
- Unauthorized callers cannot mutate escrow state.

## 4. Fund an Escrow on Testnet

**Labels:** `feature`, `stellar`, `good first issue`

Replace the seeded funding state with a wallet transaction that deposits the selected asset into the escrow contract.

**Acceptance criteria**
- User sees the transaction review state before signing.
- Pending, successful, rejected, and failed states are represented.
- Successful funding updates the deal status and explorer link.
- Testnet network information is clearly displayed.

## 5. Release Milestone Payments

**Labels:** `feature`, `soroban`, `smart contract`

Connect the release action to the contract and pay the freelancer only when the release rules are satisfied.

**Acceptance criteria**
- Only the authorized party can release a milestone.
- A milestone cannot be released twice.
- UI shows pending and confirmed transaction states.
- Contract and integration tests cover unauthorized and duplicate release attempts.

## 6. Build the Dispute Workflow

**Labels:** `feature`, `soroban`, `help wanted`

Implement the dispute center flow for pausing an escrow and recording a dispute reason.

**Acceptance criteria**
- Either party can open a dispute while the escrow is active.
- New releases are blocked while a dispute is open.
- Both parties can see dispute status and submitted reason.
- A clear resolution path is documented, even if arbitration remains manual for the MVP.

## 7. Add Activity and Transaction History

**Labels:** `feature`, `data`, `good first issue`

Populate the Activity navigation view with escrow events and Stellar transaction links.

**Acceptance criteria**
- History includes deal creation, funding, milestone release, and dispute events.
- Events are sorted newest first.
- Loading, empty, and error states are implemented.
- Transaction hashes link to the correct network explorer.

## 8. Add Automated Component Tests

**Labels:** `testing`, `good first issue`

Set up a component test runner and cover the dashboard’s highest-value interactions.

**Acceptance criteria**
- Test command is documented and runs in CI.
- Tests cover deal selection and milestone release state.
- Tests cover responsive navigation labels or accessible roles.
- Tests do not depend on a live wallet or network.

## 9. Add End-to-End Wallet Mock Tests

**Labels:** `testing`, `stellar`, `help wanted`

Add browser tests that mock wallet responses and exercise connect, fund, release, rejection, and dispute flows.

**Acceptance criteria**
- Tests run headlessly in CI.
- Wallet approval and rejection paths are covered.
- Test fixtures never contain private keys.
- Failures include screenshots or useful diagnostic output.

## 10. Improve Accessibility and Keyboard Navigation

**Labels:** `accessibility`, `good first issue`

Audit the dashboard with keyboard navigation and an automated accessibility checker.

**Acceptance criteria**
- All controls have accessible names and visible focus states.
- Navigation and deal selection work without a mouse.
- Status changes are announced appropriately.
- Automated accessibility checks run as part of the test command or CI.
