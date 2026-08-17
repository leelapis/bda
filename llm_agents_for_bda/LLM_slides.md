---
marp: true
math: mathjax
html: true
theme: default
size: 16:9
paginate: true
header: "Harnessing LLM Agents for Business Data Analytics · Python"
footer: "Business Data Analytics · Lecture Series"
style: |
  section {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
    font-size: 21px;
    padding: 34px 44px;
    background-color: #f8fafc;
    color: #1e293b;
  }
  h1 {
    color: #0f172a;
    font-weight: 800;
  }
  h2 {
    color: #1e3a8a;
    font-size: 28px;
    margin-top: 0;
    margin-bottom: 14px;
    font-weight: 700;
    border-bottom: 2px solid #3b82f6;
    padding-bottom: 5px;
  }
  h3 {
    color: #1e40af;
    font-size: 21px;
    margin-bottom: 6px;
  }
  p, li {
    line-height: 1.4;
  }
  a {
    color: #2563eb;
    text-decoration: underline;
    font-weight: 600;
  }
  .highlight {
    background-color: #dbeafe;
    color: #1e40af;
    padding: 2px 6px;
    border-radius: 4px;
    font-weight: 600;
  }
  .badge {
    display: inline-block;
    padding: 2px 8px;
    border-radius: 6px;
    font-size: 13px;
    font-weight: 700;
    text-transform: uppercase;
  }
  .badge-blue { background: #dbeafe; color: #1e40af; }
  .badge-green { background: #dcfce7; color: #166534; }
  .badge-purple { background: #f3e8ff; color: #6b21a8; }
  .badge-amber { background: #fef3c7; color: #92400e; }
  .badge-red { background: #fee2e2; color: #991b1b; }
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
  }
  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
  }
  .card {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    padding: 14px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
  }
  .card-header {
    font-weight: 700;
    color: #1e3a8a;
    margin-bottom: 6px;
    font-size: 19px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .alert-box {
    background: #eff6ff;
    border-left: 5px solid #3b82f6;
    padding: 8px 12px;
    border-radius: 0 6px 6px 0;
    margin: 8px 0;
    font-size: 18px;
  }
  .code-sm {
    font-size: 14px;
    line-height: 1.25;
    background: #0f172a;
    color: #e2e8f0;
    padding: 8px 10px;
    border-radius: 6px;
    font-family: 'Fira Code', monospace;
  }
  table {
    font-size: 16px;
    width: 100%;
    border-collapse: collapse;
  }
  th {
    background-color: #1e3a8a;
    color: white;
    padding: 6px 8px;
    text-align: left;
  }
  td {
    border: 1px solid #cbd5e1;
    padding: 5px 8px;
    background: white;
  }
  .img-card {
    display: flex;
    justify-content: center;
    align-items: center;
    background: white;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    padding: 6px;
  }
  /* Marp wraps markdown-in-HTML as <p>; keep card layout tight */
  .card > p, .alert-box > p {
    margin: 0.15em 0;
  }
  mjx-container, .katex, .katex-display {
    color: inherit;
  }
  mjx-container[jax="CHTML"] {
    font-size: 1.05em;
  }
---

<!-- _class: lead -->
<!-- _header: "" -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

<div style="text-align: center; margin-top: 30px;">
  <span class="badge badge-blue" style="font-size: 15px; margin-bottom: 12px;">Executive Technical Masterclass</span>
  <h1 style="font-size: 40px; margin-bottom: 10px; color: #1e3a8a;">Harnessing LLM Agents for<br>Business Data Analytics with Python</h1>
  <p style="font-size: 22px; color: #475569; margin-bottom: 24px;">
    From Passive Prompting to Autonomous Multi-Agent Analytical Pipelines
  </p>
  <div style="font-size: 17px; color: #64748b; border-top: 1px solid #cbd5e1; padding-top: 14px; display: inline-block;">
    <strong>Applied Business Analytics Course</strong> · Turning Real Datasets into Audited Commercial Value
  </div>
</div>

---

## 1. Executive Roadmap: The Agentic BDA Paradigm

<div class="grid-2">
  <div class="card">
    <div class="card-header"><span class="badge badge-blue">Foundation</span> Ecosystem & Prompting</div>
    <ul style="margin-bottom: 0;">
      <li><strong>IDE vs. CLI:</strong> Interactive exploration vs. headless execution pipelines.</li>
      <li><strong>Anatomy of a Prompt:</strong> The 4-pillar blueprint for rigorous analytical queries.</li>
      <li><strong>Iterative Prompting:</strong> Leading agents sequentially across milestones.</li>
    </ul>
  </div>

  <div class="card">
    <div class="card-header"><span class="badge badge-green">Execution</span> Strategy & Synthesis</div>
    <ul style="margin-bottom: 0;">
      <li><strong>Plan Before Coding:</strong> Spec-driven design in Plan Mode to stop errors.</li>
      <li><strong>Model Tournaments:</strong> Forcing baseline benchmarks & test calibration.</li>
      <li><strong>Executive Synthesis:</strong> Bridging statistical models to managerial action.</li>
    </ul>
  </div>
</div>

<div class="alert-box" style="margin-top: 12px;">
  💡 <strong>Core Principle:</strong> You are not a code typist; you are the <strong>Lead Analytics Director</strong> orchestrating intelligent agents to deliver audited business decisions.
</div>

---

## 2. Paradigm Shift: From Chatbots to Autonomous Agents

<div class="grid-2">
  <div class="card">
    <div class="card-header" style="color: #64748b;">Traditional LLM Chatbot</div>
    <div style="text-align: center; padding: 6px; font-weight: bold; color: #ef4444; background: #fee2e2; border-radius: 6px; margin-bottom: 8px;">
      Text In → Text Out (Passive)
    </div>
    <ul style="font-size: 17px; margin-bottom: 0;">
      <li>Only generates code snippets in isolation.</li>
      <li>Cannot read local CSVs or inspect errors.</li>
      <li>Relies on user to copy-paste, debug, and execute.</li>
      <li>Prone to hallucinating columns and library APIs.</li>
    </ul>
  </div>

  <div class="img-card">
    <img src="figures/agent_react_cycle.png" alt="Agent ReAct Cycle" style="width: 100%; max-height: 340px; object-fit: contain; border-radius: 6px;">
  </div>
</div>

<div style="margin-top: 8px; text-align: center; font-size: 16px; color: #475569;">
  <code>[User Query]</code> → <strong>Reason & Plan</strong> → <strong>Act (Tool Execution)</strong> → <strong>Observe (Metrics/Errors)</strong> → <strong>Refine & Deliver</strong>
</div>

---

## 3. Agentic Ecosystem: IDE vs. CLI Environments

<div class="grid-2">
  <div class="card">
    <div class="card-header"><span class="badge badge-purple">Agentic IDE</span> Interactive & Visual</div>
    <p style="font-size: 16px; margin-bottom: 6px;"><strong>Core Tools:</strong> <a href="https://www.cursor.com/" target="_blank">Cursor</a> · <a href="https://codeium.com/windsurf" target="_blank">Windsurf</a> · <a href="https://code.visualstudio.com/docs/copilot/overview" target="_blank">VS Code Copilot Agent</a> · <a href="https://kiro.dev/ide/" target="_blank">Kiro</a></p>
    <ul style="font-size: 16px; margin-bottom: 0;">
      <li><strong>Inline Diffs & Review:</strong> Inspect every code modification visually.</li>
      <li><strong>Immediate Plot Rendering:</strong> Direct display of Matplotlib/Seaborn.</li>
      <li><strong>Notebook First:</strong> In-place editing of <code>.ipynb</code> cells and markdown.</li>
      <li><em>Best for:</em> Exploratory Data Analysis, debugging, slide decks.</li>
    </ul>
  </div>

  <div class="card">
    <div class="card-header"><span class="badge badge-blue">Agentic CLI</span> Headless & Terminal</div>
    <p style="font-size: 16px; margin-bottom: 6px;"><strong>Core Tools:</strong> <a href="https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview" target="_blank">Claude Code</a> · <a href="https://aider.chat/" target="_blank">Aider</a> · <a href="https://github.com/features/copilot/cli" target="_blank">GitHub Copilot CLI</a> · <a href="https://opencode.ai/docs/cli/" target="_blank">opencode</a></p>
    <ul style="font-size: 16px; margin-bottom: 0;">
      <li><strong>Deep Workspace Search:</strong> Blazing-fast ripgrep indexing across repos.</li>
      <li><strong>Batch Pipeline Execution:</strong> Run automated scripts, tests, and sweeps.</li>
      <li><strong>Git & CI Automation:</strong> Autonomous branching, committing, and scoring.</li>
      <li><em>Best for:</em> Data pipeline construction, grid searches, scoring.</li>
    </ul>
  </div>
</div>

<div class="alert-box" style="margin-top: 10px;">
  🎯 <strong>Workflow Synergy:</strong> Use <strong>Agentic CLI</strong> for batch data processing and model sweeps; switch to <strong>Agentic IDE</strong> to inspect charts, iterate notebooks, and craft executive decks.
</div>

---

## 4. When to Use Which Tool: Comparison Matrix

| Analytical Stage | Agentic IDE (<a href="https://www.cursor.com/">Cursor</a> / <a href="https://codeium.com/windsurf">Windsurf</a>) | Agentic CLI (<a href="https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview">Claude Code</a> / <a href="https://aider.chat/">Aider</a>) | Recommended Workflow |
| :--- | :--- | :--- | :--- |
| **1. Data Audit & Cleaning** | Inspect sample tables, visualize missingness | Batch execution of outlier scripts & schema checks | <strong>CLI</strong> for batch runs, <strong>IDE</strong> for sanity checks |
| **2. Feature Engineering** | Interactive <code>.ipynb</code> transform experimentation | High-speed script generation & unit testing | <strong>IDE</strong> for visual verification of distributions |
| **3. Model Tournaments** | View confusion matrices & ROC curves | Run long-running grid searches & cross-validation | <strong>CLI</strong> (background runs with progress monitoring) |
| **4. Diagnostic Refinement** | Side-by-side code diffs & manual tweaking | Rapid refactoring across multiple <code>.py</code> modules | <strong>IDE</strong> for precise visual code review |
| **5. Executive Deliverable** | Formatting Marp slides, Jupyter RISE decks | Automated report generation & data bundling | <strong>IDE</strong> for aesthetic slide and table polish |

<div style="margin-top: 10px; font-size: 16px; color: #64748b; text-align: center;">
  <em>Professional data teams combine both: CLI provides computational torque; IDE provides human oversight.</em>
</div>

---

## 5. Anatomy of a High-Impact BDA Prompt

<div class="card" style="margin-bottom: 10px;">
  <div class="card-header" style="font-size: 18px;">The 4-Pillar Analytics Prompt Blueprint</div>
  <div class="grid-2" style="gap: 10px; font-size: 17px;">
    <div>
      <strong>1. Persona & Context</strong><br>
      <span style="color: #64748b;">"Senior Hospitality Revenue Economist working on hotel booking cancellations."</span>
    </div>
    <div>
      <strong>2. Concrete Business Objective</strong><br>
      <span style="color: #64748b;">"Segment booking types to recommend differentiated deposit and reminder policies."</span>
    </div>
    <div>
      <strong>3. Technical Boundaries & Schema</strong><br>
      <span style="color: #64748b;">"Use pandas/sklearn. Features: <code>lead_time</code>, <code>adr</code>, <code>market_segment</code>. No target leakage!"</span>
    </div>
    <div>
      <strong>4. Verification & Output Schema</strong><br>
      <span style="color: #64748b;">"Evaluate via 5-fold TimeSeriesSplit ROC-AUC. Produce a summary comparison table."</span>
    </div>
  </div>
</div>

<div class="grid-2">
  <div style="background: #fee2e2; border: 1px solid #f87171; border-radius: 6px; padding: 8px; font-size: 16px;">
    ❌ <strong>Vague Prompt:</strong> "Analyze this hotel dataset and build a model to predict cancellations with Python."
  </div>
  <div style="background: #dcfce7; border: 1px solid #4ade80; border-radius: 6px; padding: 8px; font-size: 16px;">
    ✅ <strong>Engineered Prompt:</strong> Defines persona, business stakes, exact column roles, CV scheme, and table format.
  </div>
</div>

---

## 6. Practical Prompt Comparison 1: Data Cleaning & Hygiene

<div class="grid-2">
  <div class="card" style="border-top: 4px solid #ef4444;">
    <div class="card-header" style="color: #b91c1c;"><span class="badge badge-red">Bad Prompt</span> Lazy & Ambiguous</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Clean the dataset in inn_hotels_train.csv and remove bad rows."
    </div>
    <p style="font-size: 15px; color: #7f1d1d; margin-bottom: 0;">
      <strong>Catastrophic Consequence:</strong> The agent uses <code>df.dropna()</code> or silently removes 60% of valid rows with zero prices, destroying promotional stay segments with zero logging.
    </p>
  </div>

  <div class="card" style="border-top: 4px solid #10b981;">
    <div class="card-header" style="color: #15803d;"><span class="badge badge-green">Good Prompt</span> Audited & Constrained</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Audit inn_hotels_train.csv. Log dropped counts for:
1. Invalid calendar dates (e.g. Feb 29 non-leap).
2. Zero total nights (weekend+weekday == 0).
3. avg_price_per_room == 0 ONLY IF market_segment != 'Complementary'.
4. Exact feature duplicates (ignoring row_id).
Print a pandas Series summarizing rows dropped per rule and total kept."
    </div>
    <p style="font-size: 15px; color: #14532d; margin-bottom: 0;">
      <strong>Result:</strong> Produces a verifiable audit trail showing 28,445 → 20,153 records with explicit commercial justification.
    </p>
  </div>
</div>

---

## 7. Practical Prompt Comparison 2: Feature Engineering & Leakage

<div class="grid-2">
  <div class="card" style="border-top: 4px solid #ef4444;">
    <div class="card-header" style="color: #b91c1c;"><span class="badge badge-red">Bad Prompt</span> Unchecked & Leaky</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Create new features from all columns in the hotel table to predict booking_status."
    </div>
    <p style="font-size: 15px; color: #7f1d1d; margin-bottom: 0;">
      <strong>Catastrophic Consequence:</strong> Agent includes post-arrival fields (e.g. <code>reservation_status_date</code> or checkout status), achieving 99.9% fake accuracy that collapses in production.
    </p>
  </div>

  <div class="card" style="border-top: 4px solid #10b981;">
    <div class="card-header" style="color: #15803d;"><span class="badge badge-green">Good Prompt</span> Temporal & Leak-Proof</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Engineer features strictly available at booking creation:
- lead_time_log = np.log1p(lead_time)
- total_party_size = no_of_adults + no_of_children
- is_family = (no_of_children > 0).astype(int)
Strict Rule: Do NOT include booking_status or any post-booking signals. Wrap numeric transforms in sklearn Pipeline to avoid scaling leakage."
    </div>
    <p style="font-size: 15px; color: #14532d; margin-bottom: 0;">
      <strong>Result:</strong> Clean, leak-free feature matrix mathematically sound for out-of-time inference.
    </p>
  </div>
</div>

---

## 8. Practical Prompt Comparison 3: ML Model Tournaments

<div class="grid-2">
  <div class="card" style="border-top: 4px solid #ef4444;">
    <div class="card-header" style="color: #b91c1c;"><span class="badge badge-red">Bad Prompt</span> The Single Fit Fallacy</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Train a machine learning classifier on the data and print the accuracy score."
    </div>
    <p style="font-size: 15px; color: #7f1d1d; margin-bottom: 0;">
      <strong>Consequence:</strong> Agent fits an unregularized Decision Tree on the full dataset without a holdout split. Accuracy = 98%, but it cannot generalize to next season.
    </p>
  </div>

  <div class="card" style="border-top: 4px solid #10b981;">
    <div class="card-header" style="color: #15803d;"><span class="badge badge-green">Good Prompt</span> The Model Tournament</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Conduct a 3-contender model tournament on train:
1. Baseline: DummyClassifier(strategy='prior')
2. Interpretable: DecisionTreeClassifier(max_depth=5)
3. Ensemble: RandomForestClassifier(n_estimators=200, max_depth=12)
Split: Use Aug-Sep 2018 as mini-holdout.
Metrics: Output Markdown table with ROC-AUC, Avg Precision, Recall@10%, and Brier Score."
    </div>
    <p style="font-size: 15px; color: #14532d; margin-bottom: 0;">
      <strong>Result:</strong> Clear empirical proof of generalization (Dummy AUC 0.50 → Tree 0.89 → Forest 0.90).
    </p>
  </div>
</div>

---

## 9. How to Develop & Evolve Great Prompts

<div class="grid-3">
  <div class="card">
    <div class="card-header" style="font-size: 17px;"><span class="badge badge-blue">Step 1</span> Ground in Reality</div>
    <ul style="font-size: 15px; margin-bottom: 0;">
      <li>Feed exact table schemas, data types, and head rows to the agent.</li>
      <li>Never let the agent guess column names or categorical levels.</li>
      <li>Quote business pain points and operational constraints directly.</li>
    </ul>
  </div>

  <div class="card">
    <div class="card-header" style="font-size: 17px;"><span class="badge badge-amber">Step 2</span> Restrict Toolspace</div>
    <ul style="font-size: 15px; margin-bottom: 0;">
      <li>Specify allowed libraries (e.g. <code>scikit-learn</code>, <code>statsmodels</code>).</li>
      <li>Forbid unrequested heavy dependencies (e.g., PyTorch for tabular).</li>
      <li>Enforce random seeds for strict reproducibility (<code>random_state=42</code>).</li>
    </ul>
  </div>

  <div class="card">
    <div class="card-header" style="font-size: 17px;"><span class="badge badge-green">Step 3</span> System Rules File</div>
    <ul style="font-size: 15px; margin-bottom: 0;">
      <li>Store project rules in <code>.cursor/rules/</code> or <code>CLAUDE.md</code>.</li>
      <li>Set coding standards: <em>"English only"</em>, <em>"Short diffs"</em>, <em>"No emojis"</em>.</li>
      <li>Loaded automatically on every agent invocation without re-typing.</li>
    </ul>
  </div>
</div>

<div class="alert-box" style="margin-top: 10px; font-size: 17px;">
  ⚙️ <strong>Prompt Engineering as Code:</strong> Version control your prompts and rules alongside your Python codebase.
</div>

---

## 10. Interactive Pipeline Leadership (4-Stage Pipeline)

<div class="grid-2">
  <div class="img-card">
    <img src="figures/iterative_prompt_pipeline.png" alt="4-Stage Iterative Pipeline" style="width: 100%; max-height: 340px; object-fit: contain; border-radius: 6px;">
  </div>

  <div class="card">
    <div class="card-header" style="font-size: 18px;"><span class="badge badge-purple">Pipeline Discipline</span> Stop Waterfalling!</div>
    <ul style="font-size: 16px;">
      <li><strong>Gate 1 (Audit):</strong> Inspect cleaning log. Never train on unverified data.</li>
      <li><strong>Gate 2 (EDA):</strong> Review segment profiles (lead time, ADR, special requests).</li>
      <li><strong>Gate 3 (Model):</strong> Verify out-of-time test AUC and Brier calibration score.</li>
      <li><strong>Gate 4 (Action):</strong> Require segment-specific Monday morning decisions.</li>
    </ul>
    <div style="background: #eff6ff; padding: 6px 10px; border-radius: 6px; font-size: 15px; color: #1e40af;">
      🛡️ <em>If an error occurs at Gate 1, halt and correct before touching Gate 2.</em>
    </div>
  </div>
</div>

---

## 11. Designing a Plan Before Implementation (Plan Mode)

<div class="grid-2">
  <div class="card">
    <div class="card-header"><span class="badge badge-amber">The Hazard</span> The Blind Coding Trap</div>
    <p style="font-size: 16px; color: #475569;">When prompted to code immediately, LLMs jump into syntax, write 200 lines of brittle pandas transformations, hallucinate columns, and introduce fatal target leakage.</p>
    <div style="background: #fee2e2; padding: 6px 10px; border-radius: 6px; font-size: 15px; color: #991b1b;">
      ⚠️ <em>A small error in the wrong place is a silent business catastrophe.</em>
    </div>
  </div>

  <div class="card">
    <div class="card-header"><span class="badge badge-green">The Protocol</span> The 3-Step Spec Protocol</div>
    <ol style="font-size: 16px; margin-bottom: 0;">
      <li><strong>Read-Only Exploration:</strong> Inspect dataset shapes, datatypes, and missingness without writing code.</li>
      <li><strong>Structured Plan Creation:</strong> Detail the pipeline DAG, data split logic, feature definitions, and metrics.</li>
      <li><strong>Human Gate & Approval:</strong> You review the blueprint, adjust assumptions, and authorize execution.</li>
    </ol>
  </div>
</div>

<div class="alert-box" style="margin-top: 10px; font-size: 17px;">
  🛡️ <strong>Plan Mode in Practice:</strong> Switch the agent into <code>Plan Mode</code> in Cursor / Claude Code to lock the design before generating a single line of production code.
</div>

---

## 12. Requiring Agents to Summarize Key Business Insights

<div class="grid-2">
  <div class="card">
    <div class="card-header" style="color: #1e3a8a;"><span class="badge badge-blue">The "So What?" Principle</span></div>

Executives do not purchase model coefficients, ROC curves, or $R^{2}$ scores. They purchase **risk mitigation and profit growth**.

    <div style="background: #f1f5f9; padding: 8px; border-radius: 6px; font-size: 15px;">
      <em>"Our model has an AUC of 0.88 with lead_time importance at 0.35."</em><br>
      → <strong>So what?</strong><br>
      <em>"Guests booking >90 days out cancel at 58%, representing €420k in dark rooms. We must enforce 30-day non-refundable deposits on OTA channels."</em>
    </div>
  </div>

  <div class="card">
    <div class="card-header" style="color: #15803d;"><span class="badge badge-green">The 4-Part Insight Prompting Schema</span></div>
    <ul style="font-size: 15px; margin-bottom: 0;">
      <li><strong>1. Finding:</strong> Concrete statistical fact with numbers.</li>
      <li><strong>2. Mechanism:</strong> Operational root cause behind the data.</li>
      <li><strong>3. Commercial Impact:</strong> Quantified revenue or cost risk.</li>
      <li><strong>4. Monday Action:</strong> Specific operational change with a named owner (Front Desk / Revenue Management).</li>
    </ul>
  </div>
</div>

---

## 13. Translating Statistical Metrics into Commercial Impact

| Statistical Metric | What the LLM Sees | How to Prompt for Executive Translation | Resulting Business Insight |
| :--- | :--- | :--- | :--- |
| **Feature Importance (lead_time = 0.38)** | Gini impurity split frequency | *"Translate lead_time importance into booking window risk tiers with cancellation percentages."* | "Bookings made $\ge 90$ days out have a 58% cancellation rate vs. 19% for $\lt 20$ days." |
| **Interaction (special_requests $\times$ lead_time)** | Tree split depth interaction | *"Cross-tabulate cancellation rate by lead_time quartiles across special request counts."* | "Guests requesting $\ge 2$ special services cancel at $\lt 3\%$ even at 200 days lead time." |
| **Top-Decile Recall (Recall@10% = 25%)** | Ranked precision metric | *"Calculate the financial recovery if front desk calls the top 10% highest-risk bookings."* | "Focusing confirmation calls on the top 10% risky bookings protects 25% of all cancellations." |
| **Brier Score Loss (0.139)** | Mean squared probability error | *"Explain why well-calibrated probabilities prevent guest walk compensation costs."* | "Accurate probabilities allow precise overbooking limits without walking loyal corporate guests." |

<div style="margin-top: 8px; font-size: 15px; color: #64748b; text-align: center;">
  <em>Never accept raw scikit-learn output without mandating commercial translation.</em>
</div>

---

## 14. Practical Prompt Comparison 4: Summarizing Insights

<div class="grid-2">
  <div class="card" style="border-top: 4px solid #ef4444;">
    <div class="card-header" style="color: #b91c1c;"><span class="badge badge-red">Bad Prompt</span> Passive Summary</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Summarize the results of the model for management."
    </div>
    <p style="font-size: 15px; color: #7f1d1d; margin-bottom: 0;">
      <strong>Generic LLM Output:</strong> <em>"The Random Forest model performed well with an accuracy of 88%. Lead time, ADR, and special requests were important features. Management should use this model to predict cancellations."</em> (Zero business value!).
    </p>
  </div>

  <div class="card" style="border-top: 4px solid #10b981;">
    <div class="card-header" style="color: #15803d;"><span class="badge badge-green">Good Prompt</span> Executive Action Memo</div>
    <div class="code-sm" style="margin-bottom: 6px;">
"Act as Lead Revenue Consultant. Write a 1-page General Manager Memo:
1. Core Commercial Finding: Quantify cancel rate across Q1 segments.
2. Exploratory Surprise: Highlight the special requests vs lead time effect.
3. Monday Morning Action Matrix:
   - High-risk Online Leisure: Deposit & overbooking policy.
   - Low-risk Corporate: Frictionless VIP treatment.
4. Strategic Limitations: Note why autumn test drift requires quarterly re-calibration."
    </div>
    <p style="font-size: 15px; color: #14532d; margin-bottom: 0;">
      <strong>Result:</strong> Actionable boardroom memo with quantified operational rules.
    </p>
  </div>
</div>

---

## 15. Multi-Agent Architecture: Collaborative Specialization

<div class="grid-2">
  <div class="img-card">
    <img src="figures/multi_agent_architecture.png" alt="Multi-Agent Architecture" style="width: 100%; max-height: 340px; object-fit: contain; border-radius: 6px;">
  </div>

  <div class="card">
    <div class="card-header" style="font-size: 18px;"><span class="badge badge-blue">Specialized Roles</span> Isolation = Quality</div>
    <ul style="font-size: 15px;">
      <li><strong>Orchestrator:</strong> Deconstructs RFP and manages the DAG.</li>
      <li><strong>Data Engineer:</strong> Cleans raw table & outputs immutable Parquet.</li>
      <li><strong>ML Specialist:</strong> Conducts benchmark tournaments on training set.</li>
      <li><strong>Quality Auditor:</strong> Adversarial check on data leakage & Brier score.</li>
      <li><strong>Executive Synthesizer:</strong> Prepares boardroom slide deck & memo.</li>
    </ul>
    <div style="background: #f8fafc; padding: 6px; border-radius: 4px; font-size: 14px; color: #334155;">
      💡 <em>Specialization prevents context window poisoning and ensures independent auditing.</em>
    </div>
  </div>
</div>

---

## 16. Case Study: End-to-End Hotel Cancellation Analytics

<div class="grid-2">
  <div class="card">
    <div class="card-header" style="font-size: 18px;"><span class="badge badge-blue">Phase 1</span> Segmentation (Q1)</div>
    <p style="font-size: 15px;"><strong>Prompt:</strong> <em>"Perform PCA and K-Means on scaled behavioral features (lead time, ADR, special requests). Profile each segment's cancellation rate without using the target label in clustering."</em></p>
    <div style="font-size: 14px; background: #f1f5f9; padding: 6px; border-radius: 4px;">
      <strong>Result:</strong> Discovers 4 distinct archetypes (e.g., <em>Long-lead OTA leisure</em> vs. <em>Short-lead Corporate</em>).
    </div>
  </div>

  <div class="card">
    <div class="card-header" style="font-size: 18px;"><span class="badge badge-green">Phase 2</span> Predictive Policy (Q2)</div>
    <p style="font-size: 15px;"><strong>Prompt:</strong> <em>"Train Random Forest on pre-October arrivals. Evaluate on post-October test arrivals using ROC-AUC. Connect Q1 clusters to specific deposit policies."</em></p>
    <div style="font-size: 14px; background: #f1f5f9; padding: 6px; border-radius: 4px;">
      <strong>Result:</strong> ROC-AUC 0.88; prescribes strict 30-day deposits for OTA leisure while keeping corporate bookings friction-free.
    </div>
  </div>
</div>

<div class="alert-box" style="margin-top: 10px; font-size: 16px;">

🏆 **Real-World Impact:** The agent uncovers that guests with $\ge 2$ special requests cancel at $\lt 3\%$ even at 200+ days lead time, preventing unnecessary reminder spam.

</div>

---

## 17. Critical Pitfalls & How to Neutralize Them

<div class="grid-2">
  <div class="card">
    <div class="card-header" style="color: #b91c1c;">1. Target & Temporal Leakage</div>
    <ul style="font-size: 15px;">
      <li><strong>Trap:</strong> Scaling before splitting, or using post-event signals (e.g. <code>reservation_status_date</code>).</li>
      <li><strong>Fix:</strong> Enforce <code>sklearn.pipeline.Pipeline</code> and temporal train/test cuts.</li>
    </ul>
  </div>

  <div class="card">
    <div class="card-header" style="color: #b91c1c;">2. Blind Acceptance of AI Code</div>
    <ul style="font-size: 15px;">
      <li><strong>Trap:</strong> Agent outputs plausible-looking code that silently drops 80% of rows.</li>
      <li><strong>Fix:</strong> Always demand before/after row count assertions and distribution prints.</li>
    </ul>
  </div>

  <div class="card">
    <div class="card-header" style="color: #b91c1c;">3. Context Window Poisoning</div>
    <ul style="font-size: 15px;">
      <li><strong>Trap:</strong> Dumping huge raw CSV texts into chat, exceeding token limits.</li>
      <li><strong>Fix:</strong> Force agent to use file-inspection tools (e.g. <code>head -n 5</code>, <code>df.info()</code>).</li>
    </ul>
  </div>

  <div class="card">
    <div class="card-header" style="color: #b91c1c;">4. Metric Hallucination</div>
    <ul style="font-size: 15px;">
      <li><strong>Trap:</strong> Agent claims "Model achieved 94% accuracy" on imbalanced 90/10 data.</li>
      <li><strong>Fix:</strong> Require baseline dummy score, Precision-Recall AUC, and confusion matrix.</li>
    </ul>
  </div>
</div>

---

## 18. The 5 Golden Rules for the AI-Augmented Analyst

<div style="display: flex; flex-direction: column; gap: 8px; margin-top: 4px;">
  <div class="card" style="padding: 8px 14px; border-left: 5px solid #3b82f6;">
    <strong>1. Ground in Real Data:</strong> Never let an agent operate on hypothetical schema; provide audited schemas and head rows.
  </div>
  <div class="card" style="padding: 8px 14px; border-left: 5px solid #10b981;">
    <strong>2. Plan Before Code:</strong> Enforce a written specification in Plan Mode and human approval before code execution.
  </div>
  <div class="card" style="padding: 8px 14px; border-left: 5px solid #f59e0b;">
    <strong>3. Stage Milestone Gates:</strong> Lead sequentially: Audit → EDA/Segmentation → Modeling → Executive Story.
  </div>
  <div class="card" style="padding: 8px 14px; border-left: 5px solid #ef4444;">
    <strong>4. Test Every Claim:</strong> Require automated baseline comparisons, cross-validation, and out-of-time test scores.
  </div>
  <div class="card" style="padding: 8px 14px; border-left: 5px solid #8b5cf6;">
    <strong>5. Demand the "So What?":</strong> Translate statistical outputs into dollar impact and specific Monday morning actions.
  </div>
</div>

---

<!-- _class: lead -->
<!-- _header: "" -->
<!-- _footer: "" -->
<!-- _paginate: "" -->

<div style="text-align: center; margin-top: 40px;">
  <h1 style="font-size: 38px; color: #1e3a8a; margin-bottom: 12px;">Summary & Classroom Hands-On Lab</h1>
  <p style="font-size: 21px; color: #475569; margin-bottom: 22px;">
    "The best data analysts do not write every line of code by hand.<br>They design the strategy, steer the agents, and audit the results."
  </p>
  <div style="background: #ffffff; border: 1px solid #cbd5e1; border-radius: 8px; padding: 16px 22px; display: inline-block; text-align: left; max-width: 720px;">
    <strong style="color: #1e3a8a;">Today's Classroom Mission:</strong>
    <ol style="margin-top: 6px; margin-bottom: 0; font-size: 17px;">
      <li>Open your Agentic IDE (<a href="https://www.cursor.com/">Cursor</a>) or CLI (<a href="https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview">Claude Code</a>) on the Hotel dataset.</li>
      <li>Draft a 4-pillar specification prompt in Plan Mode.</li>
      <li>Execute the 4-stage pipeline: Clean → Segment → Model → Action Memo.</li>
      <li>Submit your audited <code>submission.csv</code> and 1-page Executive Memo.</li>
    </ol>
  </div>
</div>
