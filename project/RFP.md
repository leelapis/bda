# Request for Proposals (RFP) — INN Hotels Group

**Document Reference:** RFP-2018-REV-042 \
**Issuing Authority:** Executive Operating Committee & Revenue Management Directorate, INN Hotels Group \
**Subject:** Competitive Tender for Revenue Protection, Guest Segmentation, and Cancellation Risk Strategy \
**Procurement Type:** Invited Competitive Advisory Tender \
**Working Language:** English

---

## 1. Executive Summary & Corporate Profile

INN Hotels Group operates a high-volume portfolio of premium city-center business hotels and destination leisure properties. Across 2017 and 2018, our properties handled tens of thousands of reservations flowing through diverse distribution channels: online travel agencies (OTAs), corporate negotiated accounts, direct digital bookings, offline travel agencies, and contracted aviation partner crews.

Our inventory is 100% perishable: once the night passes, an unsold room's revenue is lost forever. Today, revenue management and front-desk operations face an escalating commercial crisis that threatens our operating margins and brand reputation.

The Executive Operating Committee has initiated this formal solicitation to select an external analytics advisory partner. We are inviting shortlisted analytics firms (student consulting teams) to submit competitive bids. The winning firm will be awarded the advisory engagement based on the rigor of their data analysis, the predictive power of their empirical models, and the commercial viability of their operational recommendations.

---

## 2. The Burning Platform: Operational Crisis & Revenue Hemorrhage

Our historical booking data reveals an alarming reality: **nearly one in three bookings (over 32%) is subsequently canceled.**

In a volatile hospitality market, this is not an acceptable cost of doing business. It is a severe operational hemorrhage.

### Why This Crisis Cannot Wait:
1. **The Perishable Inventory Trap:** When a long-lead online booking cancels 48 hours prior to arrival, that room often sits dark. Last-minute fire-sale discounting erodes our average daily rate (ADR) and damages brand prestige.
2. **The "Walked Guest" Disaster:** To compensate for cancellations, front-office managers rely on crude, historical overbooking rules of thumb. On high-demand dates when cancellations fail to materialize as expected, hotels overfill. Walking a confirmed guest to a competitor property results in direct relocation costs, taxi vouchers, partner penalties, and catastrophic customer lifetime value destruction.
3. **The Failure of Blanket Policies:** Currently, the hotel applies uniform cancellation, deposit, and reminder policies across all guests. Treating a short-lead repeat corporate guest identically to an ultra-long-lead speculative leisure reservation causes friction with our most loyal clients while failing to deter high-risk cancellations.
4. **Impending High-Season Contracting Deadline:** With next season's major corporate renewals and OTA allocation windows opening immediately, the General Manager and Operating Board require an evidence-backed decision framework before locking in our commercial terms.

We are not soliciting theoretical statistical exercises. We are purchasing an **actionable revenue-management decision system** that a General Manager can deploy at the front desk on Monday morning.

---

## 3. Scope of Work & Core Bidding Mandate

Different consulting firms may propose different analytical architectures. Your firm must address two tightly interconnected core strategic questions, along with an open exploratory investigation.

### Mandate Q1: Strategic Booking Typology & Risk Profiles
A blanket customer policy assumes all bookings are interchangeable. Your firm must uncover the true structural booking archetypes within our portfolio.
- Segment reservations based on behavioral and commercial characteristics (e.g., lead time, distribution channel, party composition, room rate, loyalty status, previous stay history, and special service requests).
- Profile each identified archetype in vivid business language that hotel general managers and desk agents can immediately understand and operationalize.
- Quantify how cancellation exposure and booking volume vary across these distinct groups.

### Mandate Q2: Predictive Cancellation Risk & Segmented Operational Policy
To eliminate guesswork at the reservation desk, the hotel needs a reliable mechanism to evaluate cancellation likelihood for incoming bookings.
- Develop and validate a robust decision framework that estimates the probability of cancellation for newly created reservations.
- **Connect Q1 directly to Q2:** Use your behavioral archetypes from Q1 to prescribe **differentiated operational levers** (e.g., targeted non-refundable deposit requirements, dynamic pre-arrival confirmation workflows, differentiated overbooking thresholds, or white-glove protection for zero-risk accounts).
- If your firm concludes that a uniform hotel-wide policy remains superior to differentiated rules, you must rigorously defend why segmentation should be discarded.

*Note on Analytical Integrity:* Directly leaking the target outcome (`booking_status`) into feature engineering or clustering constitutes invalid data mining practice and will result in bid disqualification.

### Special Directive: Exploratory Operational Discovery
Beyond the two core mandates, our Executive Committee challenges each consulting firm to discover **at least one non-obvious, surprising commercial pattern** hidden in the operational booking data that a traditional manager would overlook when looking at simple top-line averages. High scores in this category require clear visual/tabular proof and a direct business implication.

---

## 4. Data Package & Governance

The hotel group provides an extract of 36,275 real historical reservations spanning arrivals across 2017 and 2018. Original identifying booking references have been masked and replaced with unique bidding identifiers (`row_id`).

### Data Files Provided:
| File Name | Description | Target Availability |
|---|---|---|
| `inn_hotels_train.csv` | Historical reservations (arrivals prior to October 2018) | Complete with audited `booking_status` |
| `inn_hotels_test.csv` | Prospective reservations (arrivals October–December 2018) | Features only (**unlabeled** `booking_status`) |
| `sample_submission.csv` | Standard submission format template | `row_id` and reference baseline probability |
| `CONTRIBUTIONS.md` | Formal consulting team contribution register | Ownership breakdown per team member |

### Data Dictionary:
| Field Name | Variable Description |
|---|---|
| `row_id` | Unique anonymized reservation identifier for competitive scoring |
| `no_of_adults` | Number of adult guests in the reservation party |
| `no_of_children` | Number of child guests in the reservation party |
| `no_of_weekend_nights` | Number of weekend nights (Saturday and/or Sunday) in the stay |
| `no_of_week_nights` | Number of weekday nights (Monday through Friday) in the stay |
| `type_of_meal_plan` | Meal plan package selected by the customer |
| `required_car_parking_space` | Binary indicator for on-site vehicle parking reservation (0 = No, 1 = Yes) |
| `room_type_reserved` | Room category accommodation code requested at booking |
| `lead_time` | Elapsed days between initial booking creation date and scheduled arrival date |
| `arrival_year` | Calendar year of scheduled check-in (2017 or 2018) |
| `arrival_month` | Calendar month of scheduled check-in (1 to 12) |
| `arrival_date` | Day of the month of scheduled check-in (1 to 31) |
| `market_segment_type` | Customer acquisition channel (Online, Offline, Corporate, Complementary, Aviation) |
| `repeated_guest` | Flag indicating whether the booking belongs to a recognized repeat guest (0 = No, 1 = Yes) |
| `no_of_previous_cancellations` | Historical cancellations recorded under this guest profile prior to current booking |
| `no_of_previous_bookings_not_canceled` | Historical completed room nights under this guest profile prior to current booking |
| `avg_price_per_room` | Average daily room rate (ADR) in Euros/currency units per room night |
| `no_of_special_requests` | Total count of recorded special guest preferences (e.g., high floor, crib, twin beds) |
| `booking_status` | Audited reservation outcome (`Canceled` vs. `Not_Canceled`) — *training extract only* |

### Data Quality & Hygiene Notice:
As an operational transaction dump, this extract reflects real-world operational quirks (e.g., record duplicates, zero-rate promotional stays, impossible calendar configurations, zero-night records). Bidders are expected to audit and clean the raw data systematically, logging the exact count of dropped records and providing explicit commercial justifications.

---

## 5. Hidden-Test Empirical Benchmark (The Competitive Arena)

To ensure fair procurement evaluation, all consulting firms will be benchmarked on an out-of-time, held-out test cohort (`inn_hotels_test.csv`) representing subsequent fourth-quarter 2018 arrivals.

Each bidding firm must generate and submit one certified `submission.csv` containing estimated cancellation probabilities:

```text
row_id,p_cancel
HTL28446,0.412500
HTL28447,0.038100
...
```
*Note:* `p_cancel` must be a **continuous probability score** bounded in the interval \([0.0, 1.0]\).

### Benchmark Ranking Metric:
- **Primary Standard:** **ROC-AUC (Area Under the Receiver Operating Characteristic Curve)** evaluated against hidden ground truth labels.
- **Tie-Breaking Standards:**
  1. Top-Decile Capture Rate (Recall on the 10% highest-risk predicted reservations).
  2. Probability Calibration Accuracy (Lowest Brier Score Loss). For $n$ test bookings, true cancel label $y_i\in\{0,1\}$ (Canceled = 1) and submitted
  probability $p_i$ = p_cancel $\in [0,1]$:

  $$
  BS = \frac{1}{n}\sum_{i=1}^n(p_i-y_i)^2
  $$

### Competitive Award Tiers:
- **1st Prize Firm:** Highest empirical test AUC.
- **2nd Prize Firm:** Runner-up empirical test AUC.
- **3rd Prize Firm:** Third-place empirical test AUC.

*Procurement Warning:* A brilliant predictive model with ungrounded operational recommendations will not win the contract. Conversely, a polished presentation backed by broken predictions will forfeit all benchmark points. Matching test rows to outside public copies of the dataset constitutes gross academic malpractice and immediate disqualification.

---

## 6. Bid Submission Requirements & Boardroom Pitch

Every consulting firm must submit a complete, unified advisory tender package:

1. **Advisory Master Notebook (`.ipynb`):** An end-to-end reproducible computational notebook written in English. This document serves as your technical due diligence report, detailing data auditing, segmentation, predictive validation, and policy derivation. You're required to include the prompt if your group uses the LLM.
2. **Executive Boardroom Deck (`.pptx` or `.pdf`):** A professional slide presentation (prepared via PowerPoint or Google Slides).
   - **Format:** Limit of **10 to 15 slides**.
   - **Presentation Time:** **15 minutes** pitch followed by **5 minutes** of intense Executive Committee Q&A.
   - **Recommended Narrative Arc:**
     - The operational pain points and financial risks from the GM's viewpoint.
     - Key behavioral booking archetypes and structural findings.
     - The predictive risk architecture and validation integrity.
     - Segmented "Monday Morning Action Plan" (differentiated policies by guest type).
     - One high-impact GM-ready dashboard chart.
     - Strategic limitations, operational risks, and implementation caveats.
3. **Contest Prediction File (`groupname_submission.csv`):** Valid CSV formatted strictly according to Section 5.
4. **Team Contribution Register (`CONTRIBUTIONS.md`):** Complete breakdown of individual partner responsibilities. ***This part can be copied into a dedicated markdown cell in the submitted `.ipynb` notebook***.
5. Group memebers' individual experiment `.ipynb` files and the file name should follow this format: "Yourname_bda_expt.ipynb" (**This is the one you did on class**).
6. The submission link is [https://calcures.com:9001/itrade](https://calcures.com:9001/itrade). The deadline is by **midnight on Aug. 18, 2026**.

---

## 7. Bid Evaluation Framework (100 Points Total)

Proposals will be judged on **commercial acumen, analytical rigor, and executive communication quality**, rather than adherence to a single uniform technical recipe.

| Category | Evaluation Focus | Maximum Points |
|---|---|:---:|
| **A. Data Trust & Quality Engineering** | Systematic cleaning log, explicit handling of duplicates/outliers/anomalies, before-and-after record reconciliation, defensible retention rules. | **10** |
| **B. Strategic Analysis & Methodological Rigor** | Methodological soundness, strict avoidance of target leakage, proper temporal validation, coherent bridge where Q1 segmentation meaningfully powers Q2 predictive policy. | **25** |
| **C. Empirical Benchmark Performance** | Competitive performance on the hidden test set. Scaled linearly: 0 points at baseline AUC (0.50), scaling to the full 15 points for top-tier benchmark performance. | **15** |
| **D. Exploratory Operational Discovery** | Identification of a non-obvious, statistically grounded behavioral insight that delivers tangible business value beyond standard cancellation metrics. | **15** |
| **E. Executive Boardroom Presentation** | Boardroom presence, executive storytelling, visual clarity, persuasive defense during Q&A, and feasibility of Monday morning recommendations. | **25** |
| **F. Technical Hygiene & Governance** | Clean, self-contained, reproducible notebook, compliant contest submission, and signed partner contribution sheet. | **10** |

### Detailed Presentation Scoring Breakdown (25 Points):
- **Executive Problem Framing & Commercial Stakes:** 8 points
- **Clarity of Evidence & Visual Communication:** 7 points
- **Actionability & Logic of Monday Morning Policy:** 7 points
- **Pitch Delivery, Timing & Defense during Q&A:** 3 points

### Performance Rating Bands:
- **Grade Band A (Distinction / Approved for Contracting):** 85 – 100 points
- **Grade Band B (Competitive / Qualified Bidder):** 70 – 84 points
- **Grade Band C (Conditional / Substantial Revisions Needed):** 60 – 69 points
- **Below 60 Points:** Non-compliant tender.
