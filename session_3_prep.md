# Session 3 Preparation: QA Testing Concepts

This document outlines the core concepts required for the Session-3 preparation, covering software testing types, bug side effects, and unresolved bugs.

---

## 1. Smoke vs. Sanity vs. Regression Testing

These three testing methodologies represent different validation gates within the software development lifecycle, differing by depth, scope, and execution triggers.

| Testing Type | Scope & Depth | Execution Trigger | Primary Objective |
| :--- | :--- | :--- | :--- |
| **Smoke Testing** | **Wide but shallow**. Tests only critical, end-to-end functionalities. | Executed on an **initial/fresh build**. | Verifies if the build is stable enough to undergo further detailed testing. |
| **Sanity Testing** | **Narrow and deep**. Focuses strictly on the modified module. | Executed immediately after a **minor bug fix** or code change. | Quickly proves that the specific fix works as intended before deeper testing. |
| **Regression Testing** | **Broad and thorough**. Explores impacted areas across the app. | Executed on a **stable build** prior to a release cycle. | Ensures that new changes or bug fixes have **not broken** existing, unchanged features. |

### Test Suite Origin
**No, they are typically not generated from the same output/test suite.** 
* **Smoke Tests:** Consist of a small, automated subset of scripts designed to run in minutes during early CI/CD pipeline stages.
* **Sanity Tests:** Often performed manually or compiled on-the-fly to validate specific, localized code fixes.
* **Regression Tests:** Comprise a comprehensive, dedicated suite of hundreds or thousands of test cases (heavily automated) that expand over the software's lifespan.

---

## 2. How Bugs Create Side Effects (The Ripple Effect)

A software bug or its fix can cause a **side effect** (commonly known as a **regression bug** or **ripple effect**) when a code modification in one area unintentionally disrupts an entirely separate component. This occurs due to:

* **Shared Dependencies:** When multiple modules (e.g., Module A and Module B) rely on the same database table, API, or shared utility function, a change targeted at Module A can instantly break Module B.
* **Tight Coupling:** Components that are highly interdependent rather than decoupled will trigger a chain reaction of failures across the application when a single module encounters an error.
* **Shared State & Global Variables:** If an error causes a component to write incorrect data into a global variable or shared memory space, every other feature reading from that space will inherit corrupt data.

---

## 3. Can Some Bugs Remain Unresolved?

**Yes, certain bugs are never resolved.** In product management systems, these are often closed with statuses like `WONTFIX`, `Deferred`, or `As Designed`. They generally fall into the following categories:

* **Heisenbugs:** These are non-deterministic bugs whose behavior changes or disappears when an attempt is made to isolate or debug them (frequently tied to race conditions or memory allocation). Because they cannot be reliably reproduced, they cannot be fixed.
* **Hardware & External Environment Limitations:** Software cannot remediate inherent physical or external faults. For example, device overheating causing data loss or fundamental browser engine rendering flaws cannot be patched by the application developer.
* **Flawed Core Architecture:** A bug might be a symptom of a systemic structural defect established early in development. Rewriting the core foundation would require an impractical expenditure of time and capital, making a workaround preferable.
* **Business ROI Decisions:** If a bug is strictly cosmetic or impacts a negligible fraction of the user base (e.g., < 0.01%), the cost of engineering resources to resolve it outweighs the value it delivers to the business.
