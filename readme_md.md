# 🧪 Swag Labs (SauceDemo) — Comprehensive Test Strategy & QA Execution Report

![QA Strategy](https://img.shields.io/badge/QA-Test%20Execution%20%26%20Strategy-blue.svg)
![Test Automation/Manual](https://img.shields.io/badge/Testing-Functional%20%7C%20UI%20%7C%20Performance-green.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

## 📌 Executive Summary

This repository contains the complete Software Quality Assurance (SQA) documentation, test execution reports, test scenario coverage, and defect identification for the **[Swag Labs (SauceDemo)](https://www.saucedemo.com/)** web application. 

The objective of this project was to establish a rigorous quality validation process covering user authentication, cart persistence, session management, dynamic component rendering, visual UI layout verification, and checkout workflows across multiple browsers and device platforms.

---

## 🛠️ Scope of Testing

The testing scope encompassed end-to-end user workflows and non-functional aspects of the platform:

* **User Authentication & Session Management:** Validating login mechanics, credential security, case-sensitivity rules, role-based behavioral personas, and session persistence across logouts.
* **Product Catalog & Management:** Verifying product filtering, dynamic catalogs (lazy-loading, sliders, spinners), image mapping, and stateful cart interactions (adding/removing items).
* **Checkout & Document Generation:** Validating multi-step user data input fields, order summaries, price calculations, and PDF receipt generation.
* **Cross-Browser & Platform Compatibility:** Executing functional and responsive checks on desktop (**Brave on PC**) and mobile (**Samsung Internet on Android**).
* **UI/UX & Visual Regression:** Identifying element layout shifts, component overlaps, visual misalignment, and image rendering inconsistencies.

---

## 📊 Test Execution Summary

Out of **19 executed test cases**, **14 passed** and **5 failed**, uncovering critical cross-user session leaks, visual regressions, and catalog rendering flaws.

| Total Test Cases | Passed | Failed | Not Executed | Out of Scope | Pass Rate |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **19** | **14** | **5** | **0** | **0** | **73.68%** |

### Test Scope Breakdown
* **Functional Testing:** Verified output against expected business logic for login, cart operations, and checkout.
* **UI & Visual Testing:** Verified component placement, responsiveness, and image accurate matching.
* **Negative & Edge-Case Testing:** Conducted tests using invalid data, case-variant inputs, and state boundary checks.
* **Performance Testing:** Analyzed application latency and handling under simulated performance-glitch user profiles.
* **Session Isolation Testing:** Tested multi-user cart state leaks and authentication boundaries.

---

## 📋 Test Scenarios & Traceability Matrix

| Test Scenario ID | Module / Feature | Priority | Test Scenario Description | Test Case Count |
| :--- | :--- | :---: | :--- | :---: |
| **TS_001** | Compatibility / Login | `P0` | Validate application loading and login performance on desktop and mobile browsers. | 12 |
| **TS_002** | Authentication | `P1` | Validate user authentication, error handling, case sensitivity, and credential security. | 5 |
| **TS_003** | Performance | `P2` | Evaluate latency metrics under simulated performance-glitch user conditions. | 2 |
| **TS_004** | Inventory / Cart | `P1` | Validate real-time cart add/remove capabilities across all user roles. | 6 |
| **TS_005** | Inventory Limits | `P2` | Test bulk product additions and cart capacity limits. | 2 |
| **TS_006** | Session Management | `P1` | Validate cart isolation and session persistence between user session switches. | 1 |
| **TS_007** | UI / Media | `P3` | Verify accurate product image mapping and asset loading. | 2 |
| **TS_008** | UI / Layout | `P3` | Validate DOM element alignment, responsive placement, and layout integrity. | 2 |
| **TS_009** | Checkout | `P1` | Verify end-to-end checkout flow, form validation, and PDF order generation. | 2 |
| **TS_010** | Navigation / Static | `P4` | Validate static content rendering and links in the "About" section. | 1 |
| **TS_011** | Dynamic Catalog | `P4` | Validate interactive dynamic components (spinners and sliders). | 1 |
| **TS_012** | Dynamic Catalog | `P2` | Test lazy-loading dynamic pagination, item uniqueness, and scroll loops. | 1 |

---

## 🚨 Critical Defect Highlights & Risk Assessment

During testing, several high-severity defects and risks were discovered and documented:

1. **Cross-User Session Data Bleed (High Severity - Security/Logic):**
   * *Issue:* The shopping cart state persists across session switches, allowing a newly logged-in user to view products added by a previous user session.
2. **Dynamic Catalog Lazy-Loading Infinite Loop (Medium Severity - UX):**
   * *Issue:* Lazy-loading trigger in the dynamic catalog enters an infinite loop resulting in duplicate product listings.
3. **Role-Specific Functional Blockers (Medium Severity - Functional):**
   * *Issue:* `problem_user` and `error_user` accounts fail to complete item removal from the cart and cannot execute PDF receipt generation.
4. **Visual Layout Misalignment (Low/Medium Severity - UI):**
   * *Issue:* Cart icon shifts position out of the navigation boundary under the `visual_user` profile; static asset placeholder images render uniformly for `problem_user`.

---

## 💻 Test Environment

* **Desktop Environment:** Brave Browser on Windows / PC
* **Mobile Environment:** Samsung Internet Browser on Android
* **Target Application Under Test:** [SauceDemo (Swag Labs)](https://www.saucedemo.com/)

---

## 👨‍💻 Author

**Muhammed Jabed Iqbal Sami**  
*Software Quality Assurance Engineer*