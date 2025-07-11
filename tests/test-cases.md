# ✅ CleanCity - Draft Test Cases (Manual Testing)

## 📋 Legend
| TC | Test Case | Priority | Status | Module |
|----|-----------|----------|--------|--------|
| TC01 | Pickup form validation & filtering | High | Executed | Waste Request |
| TC02 | Feedback form error handling | Medium | Executed | Feedback |
| TC03 | Dashboard counts not updating | High | Executed | Dashboard |
| TC04 | Admin: Status update (Blocked) | High | Blocked | Admin Panel |

---

### TC01: Pickup Form – Validate Required Fields & Filter Logic
- **Precondition:** User is logged in and on the Home page
- **Steps:**
  1. Leave all fields blank and click "Submit"
  2. Try submitting a past date (e.g., yesterday)
  3. Choose different locations from the "Location" dropdown
- **Expected:**
  - Required fields should show validation errors
  - Past dates should be rejected
  - Location dropdown should update as selected
- **Actual:**
  - Required field errors are shown ✅
  - Past dates like yesterday are accepted ❌
  - Location dropdown works ✅
- **Status:** Partially Failed

### TC02: Feedback form accepts any ID
- **Precondition:** Open the Feedback Page
- **Steps:**
  1. Enter a random or non-existing Request ID (e.g., `REQ999`)
  2. Submit feedback
- **Expected:** Error: "Request ID not found"
- **Actual:** Feedback submitted even with non-existing ID ❌
- **Status:** Failed

### TC03: Dashboard Request and Blog Count Validation
- **Precondition:** A pickup request is submitted
- **Steps:**
  1. Submit a pickup request
  2. Go to `/dashboard`
- **Expected:**
  - “Total Requests” shows submitted request
  - Blog and Missed Pickup counts reflect activity
- **Actual:**
  - Total Requests = 0 ❌
  - Blog Posts = 0 ❌
  - Missed Pickups = 0 ❌
  - Community Posts = 3 ✅
- **Status:** Failed

### TC04: Admin Panel - Status Update Blocked
- **Precondition:** Pickup requests must be available for admin
- **Steps:**
  1. Visit `/admin`
  2. Try changing request status to "Scheduled"
- **Expected:** Admin can change status and see UI refresh
- **Actual:** No pickup data appears in admin panel
- **Status:** Blocked