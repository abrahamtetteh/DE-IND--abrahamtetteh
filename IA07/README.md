IA07: Test Evidence, PR Review and CI Walkthrough
1. Test Cases Suite
TC-01 (Normal Checkout): Verify successful order submission and distance delivery fee calculation. Status: Passed.

TC-02 (Stock Validation): Verify error response when ordering items exceeding available inventory. Status: Passed.

TC-03 (POS State Transition): Verify kitchen staff transition order state from PENDING to PREPARING. Status: Passed.
. Continuous Integration (CI)
GitHub Actions workflow automatically runs ESLint linting and Jest test suites on every pull request to prevent regression bugs (Risk R-08).
