

# Exploratory Testing Report on Monefy

Tester: Kunle Oduwobi  
Session Duration: 2 hours  
Testing Type: Exploratory Testing  
Platform: Android Mobile App  
App Under Test: Monefy

## 1\. Testing Scope & Approach

The goal of this exploratory testing session was to evaluate the core money management functionality, usability, data integrity, and risk areas relevant to a personal finance application such as the Monefy app.

Testing was conducted using time-boxed exploratory charters, focusing on high-risk user journeys such as expense tracking, balance calculations, and data persistence.

## 2\. Exploratory Testing Charters

### Charter 1: Core Expense & Income Tracking

#### Mission:

Verify that users can reliably add, edit, and delete income and expense entries and that balances update correctly.

#### Areas Covered:)

* Adding income entries  
* Adding expense entries  
* Viewing records: amount, dates, title, description, balance  
* Editing existing entries: amount, title, data  
* Deleting entries  
* Balance recalculation  
* Searching records: by text, by voice  
* Switching between all, cash, and payment accounts

### Charter 2: Categories, UI & Usability

#### Mission:

Evaluate how intuitive and user-friendly the category system and UI interactions are.

#### Areas Covered:

* Current date  
* Verify default categories  
* Create custom categories  
* Category icons & colors  
* Navigation between screens  
* Navigation between accounts  
* Switching currencies  
* Tool tips  
* Language translations  
* Colour theme  
* Verify features locked under a premium account

### Charter 3: Data Accuracy & Calculations

#### Mission:

Ensure financial calculations are accurate and consistent across views.

#### Areas Covered:

* Category summaries  
* Charts and line indicators  
* Percentage calculations  
* Negative balances  
* Move money between accounts  
* Currency changes, and verify conversion  
* Day, month, week, year, all totals  
* Intervals  
* Verify over budget  
* Export data  
* Create a backup  
* Delete data  
* Restore from backup

### Charter 4: Persistence, Offline & App Lifecycle

#### Mission:

Verify that user data is safely stored and behaves correctly across app lifecycle events.

#### Areas Covered:

* App restart should not lose data  
* Background → foreground  
* Offline usage  
* Split screen  
* Device rotation  
* Interrupts by phone calls, alerts

### Charter 5: Edge Cases & Error Handling

#### Mission:

Identify how the app behaves under unusual or incorrect inputs.

#### Areas Covered:

* Very large amounts and verify limits  
* Very small amounts to verify figures are not rounded  
* Descriptions with the following inputs   
  * empty,   
  * special character,   
  * emoji  
  * very long  
  * Copy and paste  
* Zero-value transactions  
* Display of large and small amounts  
* Rapid multiple entries  
* Double taps  
* Verify empty states  
* Undo or recovery behavior: delete, create record  
* Invalid Date range filter  
* Search with gibberish text  
* Restore the same backup again

## 3\. Findings & Observations

### General Result

Core functionality works as expected  
The app performs well for standard money tracking scenarios and feels stable during normal usage. There were no crashes or interruptions, even during offline modes.

### Notable Findings

#### Finding 1: Minor UI Feedback Gap

Charter: Core Expense & Income Tracking  
Observation:  
When deleting a transaction, the confirmation toast with the undo option displays for a very short duration.

Severity: Low  
Impact: Usability

#### Finding 2: Poor Navigation Experience on First Launch

Charter: Categories, UI & Usability  
Observation:  
There is no easy way to swipe between the welcome slides. It was also not possible to return to a previous slide

Severity: Low  
Impact: User education

#### Finding 3: UI Visibility Challenging

Charter: Categories, UI & Usability  
Observation:  
The colour of a device button is the same as the app background (white). For example, while making a transfer between accounts, it’s hard to know that one can dismiss the numeric keypad to enter the notes.

Severity: Low  
Impact: User experience

#### Finding 4: Offline Mode Lacks Immediate Visibility

Charter: Persistence & Offline  
Observation:  
The app works offline, but there is no immediate indication that the user is currently offline until a premium function is requested.

Severity: Low  
Impact: User awareness

## 4\. Charter Prioritization

| Priority | Charter | Reason |
| ----- | ----- | ----- |
| **High** | Core Expense & Income Tracking | Core business functionality; failure breaks app value |
| **High** | Data Accuracy & Calculations | Financial correctness is critical for trust |
| **Medium** | Persistence & Offline | Data loss would be severe, but less frequent |
| **Medium** | Edge Cases & Error Handling | Prevents rare but damaging scenarios |
| **Low** | Categories & Usability | UX improvements, not functional blockers |

## 5\. Key Risks to be mitigated

### 1\. Data Integrity Risk

* Incorrect balances or rounding errors  
* Negative value not represented  
* Loss of transactions  
* Inconsistent summaries

Mitigation:  
Automated maintenance tests, regression testing, applying the boundary value analysis technique.

### 2\. User Trust & Transparency

* Silent failures: failed back ups  
* No feedback on destructive actions  
* Confusing UI states, wrong colour representation of incomes and expenses

Mitigation:  
Clear confirmations, undo actions, and user feedback indicators

### 3\. Security & Privacy Risk

* Financial data exposure  
* Insecure synchronization

Mitigation:  
Encryption, secure storage, penetration testing

### 4\. Offline & Device Risks

* App crashes during backgrounding  
* Data loss on low memory  
* OS interruptions

Mitigation:  
Lifecycle testing, stress testing, recovery testing

### 5\. Scalability of User Data

* Many transactions over time  
* Performance degradation  
* UI clutter

Mitigation:  
Performance profiling, pagination, UX scaling strategies

## Conclusion

The exploratory testing session showed that Monefy is stable, intuitive, and functional for core money management use cases. Findings were of low severity, which do not negatively impact the functionality of the app.