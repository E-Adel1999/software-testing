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

They happen **both before and after release**, but they serve slightly different purposes at each stage:

### Before Release (In the Test Environment)

- **Sanity Test:** A quick, focused test performed on a new build to verify that a specific bug fix or minor feature works, and that the build is stable enough for deeper testing.
- **Regression Test:** A comprehensive test suite executed after the sanity check passes to guarantee that the fixes didn't break surrounding features before the build is approved for production.

### After Release (In the Production Environment)

- **Post-Release Sanity Test:** Conducted immediately after deploying to live servers. Testers run a quick check on the critical paths to ensure the environment configured correctly and the app didn't break during deployment.
- **Production Regression Test:** If the deployment was massive or a hotfix patch was applied directly to production, a targeted regression run is executed live to ensure no live user workflows are broken.

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
