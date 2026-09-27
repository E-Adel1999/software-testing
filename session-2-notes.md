# Session 2: SDLC & STLC Notes & Mindset

During the SDLC & STLC session, the SDLC Software Development Life Cycle was explained in details, explained in 7 bullet points and each bullet point we had a detailed discussion to make sure every point is understood in a style from my prespective i can call a brain storming style.

## SDLC & STLC session discussion points:

1. Requirements gathering & Analysis (SRS, BRD, Use Case Diagrams, RTM)
2. Planning (by Project Manager, Product Owner, QA Manager, Dev. Lead/ Architect)
3. Design (translate requirements into a blueprint)
4. Implementation (converting design documents and requirements into working code)
5. Testing (o verify and validate that the software meets the requirements)
6. Deployment (To release the product to production using Jenkins / GitLab CI or Docker / Kubernetes)
7. Maintenance (To keep the software functional, up-to-date, and aligned with user needs post-deployment)

## SDLC & STLC session notes:

1. Jira is a project management tool, supports tickets assigned by testers
2. HLD design (ex. Use Case Diagram) and LLD design (ex. Class Diagram and Sequence Diagram)
3. maven tool will be used when developing in Java (ex. mvn compile, mvn test)
4. maintenence happens after deployment.
5. unit testing is done by the developer not the tester.
6. what is system testing? and what is integration testing?
7. test as soon as possible test early.
8. tools used by testers in automation testing: selenium, Cypress, junit, testNG.
9. what is the difference between functional and non functional features??
   - functional feature is what user can use non functional one are like security and reponse time.
10. what is the shift-left testing (test early and often) (this is what agile brought better than the wataer fall model)?
11. what is the RTM (ex: ensure tracebility with RTM)?
12. is regression test related to sanity check??
13. what is the difference between release, update and patches?
14. what is the reponse time per request?

note: next session is STLC will finsih it all and will contain interviews questions and there will be activity and will prepare test case and will from slide STLC silde 52 till slide 80

## Questions to answer next session:

1. what is the difference between verification and validation?

2. what is the regression test? and what is the UAT?

3. regression and sanity check happens (before release) or (after release) or (both after and before release)?

4. what is the difference between severity and priority?

### 1. What is the difference between Verification and Validation?

In short, **verification** checks if you are building the **product right**, while **validation** checks if you are building the **right product**.

| Metric              | Verification (Static Testing)                                                | Validation (Dynamic Testing)                                                |
| :------------------ | :--------------------------------------------------------------------------- | :-------------------------------------------------------------------------- |
| **Core Question**   | "Are we building the product **correctly** according to specifications?"     | "Are we building the **right product** that actually satisfies user needs?" |
| **Execution**       | Done **without** running the code.                                           | Done by **executing** the software.                                         |
| **Activities**      | Reviews, walkthroughs, inspections, and checking design documents (HLD/LLD). | Functional testing, integration testing, system testing, and UAT.           |
| **When it happens** | Early in the SDLC (aligned with **Shift-Left** testing).                     | Later in the SDLC, once code is ready to execute.                           |

---

### 2. What is Regression Testing? And what is UAT?

- **Regression Testing:** Testing existing, unchanged parts of the application after a code change (like a bug fix, new feature, or update) to **ensure that new changes haven't broken existing functionality**. It prevents old defects from crawling back into stable builds.
- **UAT (User Acceptance Testing):** The final phase of testing done **by the end-users or clients** in a production-like environment. Its sole purpose is to validate that the software fits real-world business workflows and is ready for market release.

---

### 3. Do Regression and Sanity checks happen before release, after release, or both?

They happen **exclusively before release**. They are critical gates in the testing cycle designed to validate a build prior to shipping it to production or end users, never after.

#### Before Release (In the Test Environment)

- **Sanity Test:** A quick, focused test performed right after a new build arrives (usually containing a minor fix or small change). It acts as a gatekeeper step to quickly answer: _"Is this build even worth investing more testing effort into?"_
- **Regression Test:** A comprehensive test suite executed throughout the development cycle after any code change (bug fix, new feature, or minor tweak) to guarantee that recent fixes didn't break surrounding, existing functionalities before QA sign-off.

#### Key Exceptions

- **Production Hotfixes:** If a critical bug is discovered in production, you will run sanity and regression checks again on the fix. However, this testing still happens entirely **before** that hotfix itself is released live to users.
- **Staging Environments:** Regression tests can sometimes run post-deployment in a staging environment that mirrors production right before the final push. Conceptually, this is still considered **before release** because it occurs before the code reaches the end users.

---

### The General Pipeline Order

1. **Development:** Developer makes a change or bug fix.
2. **Deployment (QA):** New build is deployed to the QA environment.
3. **Smoke Test:** Verifies if the build is stable enough to test at all.
4. **Sanity Test:** Verifies if the specific fixed area works.
5. **Regression Test:** Verifies that nothing else in the system broke.
6. **Release:** Build is approved and officially released to production/customers.

---

### 4. What is the difference between Severity and Priority?

- **Severity:** Measures the **technical impact** of a defect on the system architecture or functionality. It is typically determined by the QA tester based on how badly the system breaks (e.g., crashes, data corruption).
- **Priority:** Measures the **business urgency** or commercial timing of fixing the defect. It is typically determined by the Product Owner or Project Manager based on business timelines, marketing impact, and user experience.

### High Severity / Low Priority Example

- **Scenario:** The application completely crashes, but only when a user inputs a 50-character string into an obscure, legacy settings field that 99% of users never visit.
- **Why:** High severity because it's a hard crash; low priority because it rarely impacts business operations or real users.

### Low Severity / High Priority Example

- **Scenario:** The company logo on the homepage is misspelled as "Googleg" instead of "Google" right before a massive televised marketing campaign launch.
- **Why:** Low severity because the website functions perfectly fine technically; high priority because it severely damages brand reputation and needs an immediate fix.
