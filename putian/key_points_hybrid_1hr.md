# DSSA Graduate Key Points and In-Person Studio Plans for 1-Hour Hybrid Weekly Meetings

This file aggregates the final key-point summaries for both lecture folders:
- `lectures_data_warehousing`
- `lectures-python-programming`

Course description: Finding and gathering data from public and private databases. Database and web mining. Data storage alternatives. Required coursework will be demonstrated through Jupyter/Colab Python notebooks.

## General Design Principles

| Principle | Course decision |
|---|---|
| Lecture-extensive weekly rhythm | Weeks 1-13 use about 35 minutes of instructor explanation, prepared examples, prompt suggestions, and expected-result discussion before student demos. |
| No live instructor AI login | The instructor should not show a personal AI account or live AI conversation. Use prepared prompt cards, sample AI outputs, anonymized examples, and expected notebook results. |
| Jupyter/Colab only | Required work happens in Jupyter/Google Colab notebooks. Do not require Linux shells, servers, clusters, SSH, cloud platforms, or command-line system administration. |
| Colab free-tier safe | Required notebooks use CPU, small samples, row limits, lightweight APIs, pandas, SQLite, and standard Python. Required runs should finish in less than 10 minutes. |
| Prompt-based, not coding-recipe based | Students learn to frame tasks, write prompts, inspect generated code/query drafts, revise outputs, verify results, and explain limitations. |
| Evidence over polish | Weekly demos show a concrete artifact: notebook output, source preview, prompt trail, verification check, schema sketch, query result, or stewardship note. |
| Larger in-person demo assignments | Weeks 4, 7, and 10 use larger demonstration assignments that synthesize several small skills and support project development. |
| Individual before group | All weekly artifacts and larger in-person assignments are individual. The final semester project is the only group assignment. |
| Short demos before final project | Before Weeks 14-15, student demonstrations are assignment artifacts, larger in-person demo assignments, project-preparation artifacts, or checkpoints, not full project talks. |
| Final project once per group | Groups 1-2 demonstrate once in Week 14; Groups 3-4 demonstrate once in Week 15. Each final demo is 30-35 minutes and requires both slides and a Colab/program demonstration. |

## Concise Semester Schedule

| Week | Mode | Instructor focus | Student demo type | Assignment / project role |
|---|---|---|---|---|
| 1 | In person | Course launch, Colab setup, AI-use policy, project expectations | Orientation artifact | Weekly artifact or participation/setup check |
| 2 | Online | First notebook workflow, prompts, generated code review, file output | Assignment demo | Weekly artifact: cleaned mini CSV |
| 3 | Online | Data structures for data gathering | Assignment demo | Weekly artifact: two data representations |
| 4 | In person | Public dataset profiling, metadata, quality, provenance | Bigger in-person demo assignment | Larger assignment: dataset profile and source evaluation |
| 5 | Online | Text/web mining from short records | Assignment demo | Weekly artifact: extraction and tests |
| 6 | Online | Small API collection and responsible web access | Assignment demo | Weekly artifact: row-limited API collector |
| 7 | In person | Query design, joins, SQL/pandas validation | Bigger in-person demo assignment | Larger assignment: source pitch and validated query |
| 8 | Online | Storage alternatives and model choice | Assignment demo | Weekly artifact: two storage representations |
| 9 | Online | Storage/retrieval reasoning and tiny timing demos | Assignment demo | Weekly artifact: index/lookup explanation |
| 10 | In person | Warehouse design, grain, facts, dimensions, ETL | Bigger in-person demo assignment | Larger assignment: mini warehouse / ETL design checkpoint |
| 11 | Online | Batch-style notebook processing | Assignment demo | Weekly artifact: small batch processing output |
| 12 | No class | Thanksgiving break | None | No new assignment |
| 13 | Online | Reliability, retries, logging, idempotence, consistency concepts | Project-risk or makeup demo | Weekly artifact: final readiness/risk check |
| 14 | In person or online | Facilitate final demonstrations | Final project demo | Groups 1-2 present once; 30-35 minutes per group |
| 15 | In person or online | Facilitate final demonstrations and synthesis | Final project demo | Groups 3-4 present once; 30-35 minutes per group |

Recommended assignment count: 12 weekly artifacts before the final project if Week 1 is graded: 1 setup/orientation artifact, 8 smaller online-week individual artifacts, and 3 larger individual in-person demo assignments in Weeks 4, 7, and 10. The larger in-person assignment is the weekly artifact for that week expanded for demonstration; it is not an extra assignment on top of a small weekly task. If Week 1 is participation/setup only, count 11 graded weekly artifacts. Add 1 final group project demonstrated once in Week 14 or Week 15. The final group project requires slides, a runnable Colab/program demo, and visible participation from every group member. Week 7, Week 10, and Week 13 already function as project-preparation checkpoints and should not be counted again as separate project milestones unless the instructor wants more grading.

Recommended scoring model:

| Component | Count | Points each | Subtotal | Notes |
|---|---:|---:|---:|---|
| Week 1 setup/orientation artifact | 1 | 4 | 4 | Colab readiness, source idea, save/reload verification, and initial stewardship risk. |
| Smaller weekly individual assignments | 8 | 4 | 32 | Weeks 2, 3, 5, 6, 8, 9, 11, and 13. Week 13 includes the final readiness/risk check. |
| Larger individual in-person demo assignments | 3 | 8 | 24 | Weeks 4, 7, and 10. These are individual and replace the small weekly artifact for that week. |
| Final group project | 1 | 30 | 30 | One group demonstration in Week 14 or Week 15; 30-35 minutes, slides and Colab/program demo required, every member demonstrates a defined part. |
| Coursework/project subtotal |  |  | 90 | These are the graded deliverables and project components. |
| Engagement reserve | ongoing |  | 10 | Attendance/participation, preparedness, peer questions, in-person/online discussion, constructive critique, optional feedback, optional reflection, and professional engagement. |
| Course total |  |  | 100 | 90 points from artifacts/project plus 10 engagement points. |

Peer feedback and final reflection are not separate graded deliverables in this model. They may be used informally as part of the 10-point engagement reserve if the instructor wants lightweight participation evidence.

If Week 1 is participation/setup only rather than graded, move its 4 points into the final group project, making the final project 34 points and keeping the coursework/project subtotal at 90.

Larger in-person demonstration assignments:

| Week | Ownership | Larger assignment | What students demonstrate in person | Why it is bigger |
|---|---|---|---|---|
| Week 4 | Individual | Public Dataset Profile and Source Evaluation | A small public CSV/JSON sample, source URL, metadata notes, field/type summary, missingness or quality check, one profiling output, one limitation, and one responsible-use concern. | It combines data access, profiling, metadata/provenance, quality, and interpretation limits. |
| Week 7 | Individual, with optional project connection | Source Pitch and Validated Query | A possible project source, one data question, two AI-assisted query prompts, one SQLite or pandas query result, row-count/join verification, and one risk of misleading interpretation. | It connects source selection, query design, SQL/pandas practice, validation, and early project feasibility. |
| Week 10 | Individual, with optional project connection | Mini Warehouse / ETL Design Checkpoint | Draft fact/dimension or table design, grain statement, source-to-target ETL sketch, one query goal, one verification check for keys/grain, and one revision after critique. | It synthesizes storage choice, warehouse design, ETL reasoning, verification, and project architecture before students commit to group project implementation. |

## Detailed Weekly Schedule and Agenda

Use this as an instructor-facing scene script. It is not a word-for-word transcript; it is a practical action sequence for running each class. For Weeks 1-13, the rhythm is instructor lecture first, then a short student demonstration. For Weeks 14-15, the class is the student project demonstration.

AI privacy note for the scene scripts: the instructor should not need to log into a personal AI account or display a live AI conversation. When a scene says to show a prompt or AI result, use prepared slides, a handout, pasted text in the notebook, anonymized examples, or stored expected outputs.

### Week 1: Course Launch and AI-Assisted Data Gathering

Key points:
- The course is about finding, gathering, storing, verifying, and responsibly using data.
- AI coding is allowed as an assistant, but students must frame the task, inspect the output, and prove that it works.
- Google Colab/Jupyter is the required demonstration environment.
- A good project is small, reproducible, explainable, and grounded in a real data source.

Scene script:
1. 0-5 min: Open the course shell, show the syllabus, and name the central promise: students will demonstrate working data workflows in notebooks.
2. 5-15 min: Show the final project expectation: source, gathering method, storage choice, prompt trail, verification, and stewardship note.
3. 15-25 min: Open Colab and run a tiny notebook: create a five-row data-source table, save it as CSV, reload it, and print row count.
4. 25-35 min: Explain responsible AI coding using prepared prompt cards and sample outputs: prompt, generated code, student edits, verification evidence, and limitations.
5. 35-45 min: Students add one possible data interest/source to the starter table.
6. 45-55 min: One or two students briefly screen-share the saved/reloaded CSV and explain their data interest.
7. 55-60 min: Exit item: each student submits one possible project idea or one question about data gathering.

Student short demo:
- One or two students show that their starter notebook runs, saves a CSV, reloads it, and includes a possible data interest.

Assignment / online lecture artifact:
- Assignment type: Small setup/orientation artifact.
- Instructions: Create or complete a starter Colab notebook that proves the student can open a notebook, run cells, create a tiny table, save it as CSV, reload it, and explain one possible data interest.
- Key points: Colab readiness, reproducibility, simple file output, early project thinking, and responsible AI use.
- What to do: Add one possible data source or topic; record the source name or possible URL; describe how the data might be accessed; name one possible use case; identify one risk or limitation.
- What to submit: Colab link or `.ipynb` file, saved/reloaded CSV evidence, row-count output, and a short note with source/topic, access method, use case, and risk.

In-person details:
- Use this meeting to build comfort with speaking. The demonstration is an orientation artifact, not a project presentation.

### Week 2: First Data Workflow and Prompting for Python

Key points:
- A useful AI prompt states the task, input format, constraints, expected output, and verification checks.
- Generated code is a draft that must be run, read, and revised.
- File input/output should stay simple, visible, and reproducible.
- A cleaned output file is not enough; students must show evidence that it is correct.

Scene script:
1. 0-5 min: Start with a messy mini CSV/text block and ask what the desired clean output should look like.
2. 5-15 min: Show a prepared prompt card: "Read this text, parse rows, handle missing values, write CSV, and print checks."
3. 15-25 min: Show a prepared AI output or starter code in Colab, pause on an error or weak assumption, and revise the prompt wording on screen without logging into AI.
4. 25-35 min: Explain the verification cells: row count, missing-value count, column list, and a sample of cleaned rows.
5. 35-45 min: One rotating student demonstrates their revised prompt and one validation rule.
6. 45-55 min: Ask classmates to identify one hidden assumption in the code or data.
7. 55-60 min: Assignment checkpoint: submit notebook with prompt, code, cleaned CSV, and verification cell.

Student short demo:
- One rotating student shows the prompt, generated or starter code, one student revision, and one validation result.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact.
- Instructions: Use a messy mini text block or CSV sample and build a Colab workflow that converts it into a clean, simple CSV.
- Key points: Prompt framing, generated-code review, cleaning decisions, file input/output, and verification.
- What to do: Write or revise a prompt that states the input format, desired output fields, missing-value handling, and required checks; run the generated or starter code; revise at least one weak assumption; save the cleaned CSV; add verification cells for row count, column names, missing values, and sample records.
- What to submit: Colab notebook, prompt text, cleaned CSV or saved output cell, verification output, and a brief note naming one student revision to the AI/starter code.

In-person details:
- Online week. If demonstrated in person later, treat it as an assignment evidence check only.

### Week 3: Data Structures for Data Gathering

Key points:
- Lists, dictionaries, sets, JSON-like records, and DataFrames support different access patterns.
- The structure should match the question: lookup, grouping, duplicate detection, or update.
- Students should be encouraged to ask AI to explain structure choices before generating code.
- Students need to justify data organization decisions in plain language.

Scene script:
1. 0-5 min: Show the same tiny transaction dataset on screen as raw records.
2. 5-15 min: Lecture through four representations: list of rows, dictionary by ID, set of unique values, and DataFrame.
3. 15-25 min: Show a prepared AI-style comparison of which structure fits lookup, grouping, duplicate detection, and updates.
4. 25-35 min: Run tiny examples and show why one structure makes a task easier than another.
5. 35-45 min: One rotating student demonstrates two structures and explains a tradeoff.
6. 45-55 min: Peer question: "What task would make your chosen structure inconvenient?"
7. 55-60 min: Assignment checkpoint: submit two representations, one operation on each, and a short justification.

Student short demo:
- One student compares two data structures using the same tiny records and explains which task each structure supports.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact.
- Instructions: Represent the same tiny record set in two different Python data structures and explain why each structure helps or hurts a specific task.
- Key points: Lists, dictionaries, sets, JSON-like records, DataFrames, lookup, grouping, duplicate detection, and tradeoff explanation.
- What to do: Create a 5-20 row toy dataset; represent it in two forms; run one meaningful operation on each form; use a prompt or prompt card to ask for structure-choice reasoning; revise the answer in the student's own words.
- What to submit: Colab notebook with both representations, operation outputs, prompt trail or prompt note, and a short explanation of which representation is better for which task.

In-person details:
- Online week. This can feed later source/query decisions but is not a project milestone by itself.

### Week 4: Public Dataset Profiling

Key points:
- Before analysis, students must understand fields, types, missingness, update dates, metadata, and provenance.
- Datetime and encoding issues are common in public datasets.
- A dataset can support some questions and fail to support others.
- Responsible use begins before modeling or visualization.

Scene script:
1. 0-5 min: Open a small public CSV/JSON extract and ask, "What do we know before running any analysis?"
2. 5-15 min: Explain metadata, source steward, update frequency, license/terms, and field definitions.
3. 15-25 min: Show a prepared profiling prompt and expected plan, not code first: columns, data types, missingness, dates, categories, and sample records.
4. 25-35 min: Run the profiling notebook and point out one date issue, one missingness issue, and one limitation.
5. 35-45 min: Selected student demonstrates one profile artifact.
6. 45-55 min: Class asks one evidence question and one stewardship question.
7. 55-60 min: Assignment checkpoint: submit one-page profile with one quality issue and one responsible-use concern.

Student short demo:
- Selected individual students demonstrate the larger Public Dataset Profile and Source Evaluation: dataset preview, source URL, metadata notes, one profiling result, one quality issue, one limitation, and one responsible-use concern.

Assignment / online lecture artifact:
- Assignment type: Larger individual in-person demo assignment.
- Instructions: Select one small public CSV/JSON dataset or row-limited API result and prepare a source profile that explains whether the dataset is usable for a modest analysis.
- Key points: Metadata, provenance, source steward, update date, field definitions, data types, missingness, quality, limitations, and responsible use.
- What to do: Record the dataset source URL and publisher/steward; load a small sample in Colab; show columns and data types; run at least one missingness or quality check; inspect date or encoding issues if relevant; identify one question the data can support and one question it cannot support.
- What to submit: One-page profile or notebook section with source URL, metadata notes, preview, field/type summary, profiling output, one quality issue, one limitation, one responsible-use concern, and 3-5 demo talking points for in-person presentation.

In-person details:
- This is the first larger in-person demo assignment. Use face-to-face time for questioning source credibility, metadata quality, and what the data cannot support.

### Week 5: Text and Web Mining from Short Records

Key points:
- Text extraction should begin with examples and counterexamples.
- Regex and string logic are testable hypotheses, not magic.
- False positives and false negatives matter.
- Web mining must respect terms of use, privacy, and scope.

Scene script:
1. 0-5 min: Show 10-30 short records with dates, IDs, keywords, and messy wording.
2. 5-15 min: Explain extraction goals: what field is needed, what counts as a match, and what should not match.
3. 15-25 min: Show a prepared regex or string-cleaning prompt that includes examples and counterexamples, plus one plausible AI-generated pattern.
4. 25-35 min: Run extraction, show false positives/false negatives, and revise the pattern.
5. 35-45 min: One rotating student demonstrates a fixed extraction rule and the test evidence.
6. 45-55 min: Peer question: "What text variation would break this?"
7. 55-60 min: Assignment checkpoint: submit extracted table, test cases, and one limitation.

Student short demo:
- One student shows an extraction rule, one false positive or false negative, and how the rule was revised.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact.
- Instructions: Extract one or more structured fields from 10-30 short public or instructor-provided text records.
- Key points: String methods, regex, examples and counterexamples, false positives, false negatives, and responsible text mining.
- What to do: Define the target field; create or choose 10-30 short records; write a prompt that includes examples and counterexamples; run an extraction rule; test the rule against expected matches and non-matches; revise the rule after finding at least one weakness.
- What to submit: Colab notebook with raw text records, extraction rule, extracted table, test cases, false-positive/false-negative note, revised rule or explanation, and one limitation about text variability or responsible use.

In-person details:
- Online week. If revisited in person, use it for peer debugging rather than a project presentation.

### Week 6: Small API Collector

Key points:
- APIs require attention to URL structure, parameters, status codes, JSON shape, rate limits, and terms of use.
- Required work should use no-key or instructor-approved APIs with row limits.
- A polite collector includes timeouts, small limits, and minimal repeated calls.
- Students must save the raw or lightly processed response and verify it.

Scene script:
1. 0-5 min: Open a paste-ready API URL and show the JSON response in browser or notebook.
2. 5-15 min: Explain endpoint, parameters, row limit, response format, and source documentation.
3. 15-25 min: Show a prepared prompt and sample `requests` workflow with timeout, status check, JSON parsing, and saved output.
4. 25-35 min: Run the collector and verify row count, columns/keys, source URL, and timestamp.
5. 35-45 min: One rotating student shows a row-limited API result.
6. 45-55 min: Discuss rate-limit and terms-of-use risks.
7. 55-60 min: Assignment checkpoint: submit notebook, API URL, saved output, and verification cell.

Student short demo:
- One student screen-shares a row-limited API result, source URL, saved output, row count, and one access-risk note.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact.
- Instructions: Build a small API collector in Colab using a no-key or instructor-approved endpoint with a row limit.
- Key points: URL parameters, HTTP status, JSON/CSV shape, rate limits, terms of use, saved raw response, and verification.
- What to do: Choose or use a provided API URL; include row limits or filters; request the data with a timeout; check status code; parse JSON or CSV into a DataFrame; save the raw or lightly processed response; print row count, keys/columns, source URL, and collection timestamp.
- What to submit: Colab notebook, API URL, saved response or output file, row-count and key/column checks, timestamp, and one access-risk or terms-of-use note.

In-person details:
- Online week. Later in-person project checkpoints may reuse the same source if it remains small and reliable.

### Week 7: Question to Query

Key points:
- A data question must become a table design and query plan.
- SQL and pandas can both answer questions, but joins and filters must be validated.
- Misleading joins often appear correct until row counts and keys are checked.
- AI-generated SQL should be reviewed for intent, assumptions, and verification.

Scene script:
1. 0-5 min: Show two or three tiny related tables and a natural-language question.
2. 5-15 min: Explain keys, joins, filters, aggregation, and expected grain.
3. 15-25 min: Show a prepared SQL prompt plus a sample explanation of possible join mistakes and row-count checks.
4. 25-35 min: Run the query in SQLite, verify counts, and show one misleading query result.
5. 35-45 min: Selected student demonstrates one source choice and one validated query.
6. 45-55 min: Peer question: "What result would convince you the join is wrong?"
7. 55-60 min: Assignment checkpoint: submit source pitch, two query prompts, one query result, and one verification.

Student short demo:
- Selected individual students demonstrate the larger Source Pitch and Validated Query assignment: possible project source, data question, query prompt, SQL/pandas result, and row-count or join sanity check.

Assignment / online lecture artifact:
- Assignment type: Larger individual in-person demo assignment.
- Instructions: Turn one possible data source into a focused data question and a validated query result using SQLite or pandas.
- Key points: Source feasibility, natural-language question, table grain, keys, joins, filters, aggregation, AI-assisted query drafting, and validation.
- What to do: Pitch one possible project source; write one focused data question; draft two AI-assisted query prompts; run one SQLite or pandas query; verify the result with row counts, join checks, key uniqueness, or manual spot checks; explain one way the result could be misleading.
- What to submit: Notebook or short demo packet with source URL/name, data question, two query prompts, query code, query output, validation evidence, misleading-interpretation note, and 3-5 demo talking points for in-person presentation.

In-person details:
- This is the second larger in-person demo assignment and a project-preparation demo. Students may use it to test a possible final project source, but it is still exploratory and can change.

### Week 8: Storage Alternatives

Key points:
- Storage choices follow from data shape, query needs, update patterns, and governance concerns.
- Relational, document, graph, key-value, schema-on-read, and schema-on-write models solve different problems.
- Students should ask AI for comparisons under project constraints, not generic pros/cons.
- Required demonstrations use only lightweight local representations.

Scene script:
1. 0-5 min: Show one small dataset and three possible questions it could answer.
2. 5-15 min: Explain relational, JSON document, graph edge list, and key-value representations.
3. 15-25 min: Show a prepared model-comparison prompt and sample response for the dataset, question, privacy, and update pattern.
4. 25-35 min: Run two tiny representations and show how the same question changes.
5. 35-45 min: One rotating student recommends a model for a project-style question.
6. 45-55 min: Class challenges the recommendation with one future requirement.
7. 55-60 min: Assignment checkpoint: submit two storage representations and one justified recommendation.

Student short demo:
- One student compares two storage representations and recommends one for a specific question or project-style scenario.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact.
- Instructions: Compare two lightweight storage representations for the same small dataset and justify which one better fits a specific question.
- Key points: CSV, JSON, pandas DataFrame, SQLite, relational thinking, document-style records, schema-on-read, schema-on-write, and governance tradeoffs.
- What to do: Choose or use a small dataset; store or represent it in two ways; run or describe one operation supported by each representation; use a prompt to compare the choices under Colab/free-tier constraints; revise the recommendation to include data shape, query need, update pattern, and stewardship concern.
- What to submit: Notebook or short design note with two representations, one operation or query example, prompt/revision note, recommendation, and one tradeoff or governance concern.

In-person details:
- Online week. The recommendation can become evidence for the Week 10 warehouse/storage checkpoint.

### Week 9: Storage and Retrieval Reasoning

Key points:
- Indexes are designed for access patterns, not added because they sound advanced.
- Hash indexes, B-trees, LSM-trees, and file scans reflect read/write tradeoffs.
- Tiny timings are illustrations, not production benchmarks.
- Students must state what a performance demonstration can and cannot conclude.

Scene script:
1. 0-5 min: Start with a lookup task and ask students how the computer might find the record.
2. 5-15 min: Explain scan, dictionary lookup, sorted lookup, and database index intuitively.
3. 15-25 min: Show a prepared prompt and starter code for a tiny timing demo plus warnings about interpretation limits.
4. 25-35 min: Run the demo with modest rows and compare list/dictionary/SQLite behavior.
5. 35-45 min: One rotating student explains a timing result and its limits.
6. 45-55 min: Peer question: "What would change if writes were frequent?"
7. 55-60 min: Assignment checkpoint: submit tiny timing output, explanation, and limitation.

Student short demo:
- One student explains a tiny lookup/index timing result and clearly states why it is illustrative rather than definitive.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact.
- Instructions: Run a tiny lookup or retrieval comparison that illustrates how access patterns affect storage/index choices.
- Key points: File scan, dictionary lookup, sorted lookup, SQLite query, index intuition, read/write tradeoffs, and limits of tiny benchmarks.
- What to do: Create or load a modest dataset small enough for Colab; compare two lookup/retrieval methods; record the timing or operation count; explain the access pattern; state why the result is only illustrative; connect the finding to one possible storage or indexing decision.
- What to submit: Colab notebook with timing/output evidence, access-pattern explanation, storage/index implication, and one limitation about scale, hardware, data size, or write workload.

In-person details:
- Online week. Use this later as vocabulary for justifying storage/index choices in the project.

### Week 10: Mini Warehouse Design

Key points:
- Warehouse design depends on grain, facts, dimensions, keys, and intended analyses.
- ETL choices should be explainable and verified.
- AI can propose schemas, but students must reject, revise, or justify alternatives.
- This week is a project checkpoint, not the final presentation.

Scene script:
1. 0-5 min: Show a tiny operational dataset and ask what business/public question the warehouse should answer.
2. 5-15 min: Explain fact table, dimension tables, grain, keys, and common schema mistakes.
3. 15-25 min: Show two prepared AI-style star schema suggestions and critique each.
4. 25-35 min: Build a tiny fact/dimension example in pandas or SQLite and verify grain and keys.
5. 35-45 min: Selected individual students show draft schema checkpoints.
6. 45-55 min: Peer critique focuses on grain, missing dimensions, and verification checks.
7. 55-60 min: Assignment checkpoint: submit schema sketch, prompt trail, and one revision.

Student short demo:
- Selected individual students demonstrate the larger Mini Warehouse / ETL Design Checkpoint: draft fact/dimension or table design, grain statement, ETL sketch, one query goal, one verification check, and one revision they will make after critique.

Assignment / online lecture artifact:
- Assignment type: Larger individual in-person demo assignment.
- Instructions: Design a mini warehouse, star schema, or clear table model for a small operational-style dataset and explain how the data would move from source to analytical form.
- Key points: Fact tables, dimensions, grain, primary/foreign keys, ETL steps, source-to-target mapping, query goals, AI schema critique, and verification.
- What to do: Select or use a tiny operational dataset; state the analytical question; draft a schema or table model; define the grain; identify keys; sketch ETL steps from raw source to analytical table(s); ask AI for a schema suggestion or critique; revise one design decision; verify grain or keys with a row-count, uniqueness, or join check.
- What to submit: Schema sketch or notebook, source-to-target ETL sketch, prompt trail, grain statement, key/grain verification output, one revised design decision, and 3-5 demo talking points for in-person critique.

In-person details:
- This is the third larger individual in-person demo assignment and a formative project checkpoint. It is not the final project demo, and students may later decide whether to adapt an individual design into the group project.

### Week 11: Batch-Style Processing in Notebooks

Key points:
- Batch processing can be taught with tiny files and repeated transformations.
- Generators/chunking are useful when data could become larger, even if demos stay small.
- Project organization, reusable functions, and row-count logs improve reproducibility.
- Required work should not create thousands of files or depend on Drive-heavy operations.

Scene script:
1. 0-5 min: Show a small folder of short CSV/log files and the target summary output.
2. 5-15 min: Explain repeated processing, functions, generators/chunks, modules, and output checks.
3. 15-25 min: Show a prepared prompt and starter workflow for processing multiple small files with row-count logging and one summary file.
4. 25-35 min: Run the notebook and inspect input counts, transformed counts, and output file.
5. 35-45 min: One rotating student shows a small processed output and row-count verification.
6. 45-55 min: Discuss how the design would scale conceptually without running a large job.
7. 55-60 min: Assignment checkpoint: submit notebook, summary output, and processing log.

Student short demo:
- One student shows several tiny inputs, one summary output, and a processing log or row-count check.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact.
- Instructions: Build a batch-style notebook workflow that processes several tiny files or chunks and produces one checked summary output.
- Key points: Repeated processing, functions, chunks/generators, file organization, row-count logs, output checks, and reproducibility.
- What to do: Use several small CSV/text files or simulated chunks; write a reusable function for the transformation; process each input; combine or summarize results; save one summary output; log input counts, output counts, and any skipped/problem rows.
- What to submit: Colab notebook, tiny input files or generated sample cells, summary output, processing log, row-count checks, and one note on how the design could scale conceptually without running a large job.

In-person details:
- Online week. Keep any later in-person discussion focused on reproducibility and file organization, not large-scale infrastructure.

### Week 12: Thanksgiving Break

Key points:
- No new lecture.
- No required Colab activity.
- Students may use the break to stabilize project data sources and small sample files.

Scene script:
1. Before break: remind students to avoid selecting large or credential-heavy sources.
2. Optional: post a short project self-check list: source, sample, access method, storage idea, verification idea, and stewardship risk.
3. After break: resume with reliability and final project readiness.

Student short demo:
- None.

Assignment / online lecture artifact:
- Assignment type: No new required assignment.
- Instructions: Do not assign new technical work during the break unless the instructor wants an optional project self-check.
- Key points: Rest, source stabilization, avoiding oversized data sources, and reducing final-project risk.
- What to do: Optional only: groups or individuals review source, sample, access method, storage idea, verification idea, and stewardship risk.
- What to submit: Nothing required. Optional submission may be a short project self-check list or source-risk note.

In-person details:
- No class.

### Week 13: Reliability and Integration Concepts

Key points:
- Reliability can be taught through small simulations: retries, logging, idempotence, transaction anomalies, and consistency tradeoffs.
- Distributed systems concepts should remain conceptual or tiny local simulations in this course.
- Prompting should label what is simulated and what is production reality.
- Final projects need evidence that the workflow is reproducible and failure-aware.

Scene script:
1. 0-5 min: Ask, "What could fail in your data gathering workflow?"
2. 5-15 min: Explain logging/timing, retries, idempotence, transactions, replication, partitioning, and consistency at a conceptual level.
3. 15-25 min: Show a prepared simulation prompt and sample output for one reliability concept at tiny scale, clearly labeling assumptions.
4. 25-35 min: Run one simulation, such as retry logic or duplicate-safe output writing.
5. 35-45 min: One rotating student demonstrates a project risk check or reliability simulation.
6. 45-55 min: Class asks how the final project notebook will prove reproducibility.
7. 55-60 min: Assignment checkpoint: submit final project readiness note with source, sample, demo step, verification, and risk.

Student short demo:
- One student shows a small reliability simulation or final project risk check, such as retries, duplicate-safe output, logging, or idempotence.

Assignment / online lecture artifact:
- Assignment type: Small weekly artifact and final project readiness check.
- Instructions: Prepare a brief readiness note proving that the final project or demo idea is small, reproducible, and failure-aware.
- Key points: Reliability, retries, logging, idempotence, reproducibility, consistency concepts, demo risk, and honest limitation.
- What to do: Identify what could fail in the data gathering/storage workflow; show one small reliability practice such as status checks, retry logic, duplicate-safe output, logging, saved intermediate data, or row-count validation; connect the practice to the final project demo plan.
- What to submit: Readiness note or notebook section with source/sample, planned demo step, verification evidence, one reliability practice, one remaining risk, and one fallback plan if the live API or data source fails.

In-person details:
- Online week. If used as a makeup demo, keep the same 10-minute artifact format.

### Week 14: Final Project Demonstrations, Groups 1-2

Key points:
- This class is student-led demonstration, not a regular lecture.
- Each group presents once.
- Slides and a program/notebook demo are both required.
- Each group member must demonstrate or explain a specific part of the project.
- The demo must show a reproducible project slice that runs on Colab free tier.
- Evaluation focuses on data source, gathering method, storage choice, prompt trail, verification, and stewardship.

Scene script:
1. 0-5 min: Instructor opens with timing, expectations, and the evidence checklist.
2. 5-38 min: Group 1 presents slides and demonstrates the notebook/program: source, sample load/API call, cleaning or query/storage step, verification cell, stewardship note, and limitation. Each member demonstrates or explains one part.
3. 38-43 min: Peer and instructor questions for Group 1: evidence, feasibility, stewardship.
4. 43-76 min: Group 2 presents slides and demonstrates the same required project evidence. Each member demonstrates or explains one part.
5. 76-81 min: Peer and instructor questions for Group 2.
6. Final 2-3 min: Instructor gives transition notes and reminds non-presenting groups what to adjust before Week 15.

Student short demo:
- Groups 1-2 each give one final project demonstration of 30-35 minutes. This is no longer a short weekly assignment demo.

Assignment / online lecture artifact:
- Assignment type: Final group project demonstration.
- Instructions: Groups 1-2 deliver their only final project presentation. The presentation must include both slides and a runnable Colab/program demo, and each member must demonstrate or explain a defined part.
- Key points: Data source, gathering method, storage/model choice, query or analysis, verification evidence, AI prompt trail, stewardship, limitations, and shared member participation.
- What to do: Prepare a 30-35 minute group presentation; keep the live notebook/program run under 10 minutes; use saved intermediate outputs if needed; assign every member a visible segment and evidence item; answer peer/instructor questions about reliability, feasibility, and responsible use.
- What to submit: Slide deck, Colab notebook or `.ipynb`, required small sample data if not loaded from a stable public URL, prompt trail, stewardship/limitation note, and group contribution note naming each member's role and demonstrated part.

In-person details:
- If in person, enforce timing, visible notebook evidence, required slides, member-by-member participation, and peer questions. The instructor facilitates rather than lectures. If the class meeting is strictly 60 minutes, use two 30-minute demos with questions collected in writing; otherwise schedule an extended final-demo block.

### Week 15: Final Project Demonstrations, Groups 3-4

Key points:
- This class is student-led demonstration, with a short synthesis only if time remains.
- Each group presents once.
- Slides and a program/notebook demo are both required.
- Each group member must demonstrate or explain a specific part of the project.
- The project demo should be small, runnable, and honest about what would change at production scale.
- The course closes by connecting data gathering, storage alternatives, reliability, privacy, and responsible use.

Scene script:
1. 0-5 min: Instructor opens with timing, expectations, and a reminder that live notebook/program runtime must stay under 10 minutes.
2. 5-38 min: Group 3 presents slides and demonstrates the notebook/program: source, sample, gathering method, storage/query step, verification, stewardship note, and limitation. Each member demonstrates or explains one part.
3. 38-43 min: Peer and instructor questions for Group 3.
4. 43-76 min: Group 4 presents slides and demonstrates the same required project evidence. Each member demonstrates or explains one part.
5. 76-81 min: Peer and instructor questions for Group 4.
6. Final 2-3 min: Instructor closes with course synthesis: strongest design decisions, remaining risks, and responsible next steps.

Student short demo:
- Groups 3-4 each give one final project demonstration of 30-35 minutes. This is no longer a short weekly assignment demo.

Assignment / online lecture artifact:
- Assignment type: Final group project demonstration.
- Instructions: Groups 3-4 deliver their only final project presentation. The presentation must include both slides and a runnable Colab/program demo, and each member must demonstrate or explain a defined part.
- Key points: Data source, gathering method, storage/model choice, query or analysis, verification evidence, AI prompt trail, stewardship, limitations, production-scale thinking, and shared member participation.
- What to do: Prepare a 30-35 minute group presentation; keep the live notebook/program run under 10 minutes; use saved intermediate outputs if needed; assign every member a visible segment and evidence item; close by connecting the project to course themes of data gathering, storage alternatives, reliability, privacy, and responsible use.
- What to submit: Slide deck, Colab notebook or `.ipynb`, required small sample data if not loaded from a stable public URL, prompt trail, stewardship/limitation note, and group contribution note naming each member's role and demonstrated part.

In-person details:
- If in person, preserve time for synthesis only after both demos are complete. The instructor's role is facilitation, evidence checking, and course closure. If the class meeting is strictly 60 minutes, use two 30-minute demos with questions collected briefly in discussion or moved into the engagement reserve; otherwise schedule an extended final-demo block.

## Group Project Instructions

Student-facing introduction:

The semester project is the only required group assignment. Each group will design and demonstrate a small, reproducible data gathering and warehousing workflow using Jupyter/Google Colab. The goal is not to build a production data platform. The goal is to show that the group can find or select a usable data source, gather a small sample responsibly, organize or store it appropriately, run a meaningful query or summary, verify the result, and explain the limitations and stewardship risks.

Group size:
- Recommended: 4-6 students per group.
- Maximum: 6 students per group.
- For a class of about 10 students, two groups are likely. If only two groups form, use Week 14 for final demos and Week 15 for synthesis, reflection, or contingency. If three or four groups form, split presentations across Week 14 and Week 15.

Required project constraints:
- Must run in Google Colab free tier with CPU only.
- Must use Jupyter/Colab notebook work; no required Linux shell, Docker, server setup, database server, paid cloud service, Spark cluster, Kafka cluster, or long-running background job.
- Live demo runtime must stay under 10 minutes.
- Use a small sample, row-limited API result, or instructor-approved extract, usually 100-5,000 rows.
- Avoid private credentials, sensitive personal data, paid API keys, scraping at scale, or any source whose terms of use are unclear.
- The notebook must include visible verification: row counts, schema checks, sample records, missingness checks, SQL counts, join checks, or manual spot checks.

Project question:
- Start with one practical data question, not a broad topic.
- Good pattern: "Using [source], what can we learn about [specific issue] by gathering [small sample], storing it as [CSV/SQLite/JSON/table model], and running [query/summary]?"
- Examples: public service requests by complaint type, unemployment time series for a few regions, public health indicators by state/year, government spending summaries by agency/vendor, or dataset metadata comparison across sources.
- The strongest projects should have research value, not only application value. A research-value project measures, compares, audits, validates, or explains a data problem in a way that could support a small report, poster, or future study.

Research-oriented project options:

| Option | Possible research question | Suggested data path | Colab demo | Research value |
|---|---|---|---|---|
| Public-data quality audit | How complete, current, and internally consistent is one public dataset that people might use for decision-making? | Socrata open data, Data.gov agency dataset, NJ Open Data, NYC Open Data, CDC Open Data | Load 500-5,000 rows, profile fields, measure missingness, check dates/categories, and document anomalies. | Evaluates whether a dataset is trustworthy enough for analysis and identifies evidence-based limitations. |
| Cross-source measurement comparison | Do two public sources describe the same phenomenon differently, and what explains the difference? | World Bank vs. Data USA/Census sample, BLS vs. FRED CSV sample, city/state open data pair | Gather small samples from two sources, align fields/time/place, compare definitions and summary results. | Shows how measurement choices, definitions, and collection methods affect conclusions. |
| Metadata and provenance study | How well does a dataset document its origin, update process, license/terms, and field meanings? | Data.gov metadata pages, NJ Open Data metadata, UCI dataset pages, agency documentation | Build a metadata table, score documentation quality, link fields to source notes, and identify missing provenance details. | Produces a stewardship-focused evaluation of discoverability, reuse risk, and accountability. |
| Bias and coverage analysis | Which groups, places, time periods, or categories are underrepresented or overrepresented in a public dataset? | 311 requests, public health indicators, education data, inspections, transit/service data | Group by place/time/category, compare counts or rates, visualize coverage gaps, and discuss what is unobserved. | Investigates sampling, reporting, access, or administrative bias without claiming causality. |
| Responsible web/API access study | How do API limits, pagination, field selection, and terms of use shape what researchers can collect responsibly? | Socrata API endpoint, BLS API, World Bank API, Data USA API | Make row-limited calls, log URL parameters/status/time, compare two query designs, and save raw response. | Studies data access as a methodological constraint, not just a technical step. |
| Reproducibility and reliability audit | Can another student rerun the data workflow and obtain the same row counts, schema, and result? | Any approved small public dataset or API with stable sample file fallback | Run notebook from top to bottom, record versions/timestamps, validate row counts, and include fallback saved data. | Tests whether the data pipeline is reproducible, inspectable, and failure-aware. |
| Small warehouse design evaluation | Which table design best supports a specific analytical question while preserving provenance and verification? | UCI tabular dataset, NJ purchasing data, 311 data sample, instructor-provided operational sample | Create two candidate table models, implement one in SQLite, run a query, and verify keys/grain. | Compares design alternatives and justifies modeling choices using evidence, not preference. |
| Prompt reliability study | How much do AI-generated data-cleaning or SQL suggestions improve after adding constraints, examples, and verification requirements? | Any small course dataset; use saved prompts and generated/revised outputs | Compare first prompt vs. revised prompt, run both outputs if appropriate, and evaluate correctness with tests/checks. | Treats AI assistance as an object of study: prompt design, error detection, revision, and human oversight. |
| Ethical interpretation case study | What claims can responsibly be made from a small public dataset, and what claims would overreach the evidence? | Public health, crime/safety, education, labor, housing, or service-request data | Run a modest query/summary, then map result to limitations, missing variables, privacy concerns, and possible harms. | Connects technical evidence to responsible interpretation, bias, privacy, and policy caution. |
| Data lifecycle mini-study | What happens to data quality and meaning as data moves from raw source to cleaned file, SQLite table, and summary output? | Any small CSV/API dataset with several fields and at least one cleaning issue | Show raw sample, cleaned DataFrame, SQLite table, summary query, and verification checks at each stage. | Studies how transformation decisions affect provenance, meaning, and later analytical trust. |

Step-by-step action suggestions by project option:

| Option | Jupyter/Colab program demo steps | Slides based on results |
|---|---|---|
| Public-data quality audit | 1. Choose one public dataset and load 500-5,000 rows. 2. Display source URL, publisher, row count, column list, and data types. 3. Run missingness, duplicate, date-range, category-frequency, and impossible-value checks. 4. Save a small issue log table with issue, field, evidence, possible cause, and impact. 5. Show one cleaned or flagged sample and one verification cell. | Slide 1: research question and why the dataset matters. Slide 2: source/provenance summary. Slide 3: quality-check table or chart. Slide 4: two or three most important issues with evidence. Slide 5: what analysis is safe or unsafe given the audit. |
| Cross-source measurement comparison | 1. Select two sources that describe a similar concept. 2. Load small samples from each source. 3. Create a field-definition comparison table. 4. Standardize place, time, unit, and category labels where possible. 5. Join or align the samples and compare summary results. 6. Verify matched rows and document unmatched rows. | Slide 1: comparison question. Slide 2: source definitions and collection differences. Slide 3: alignment method and join/check evidence. Slide 4: result chart or table showing difference. Slide 5: interpretation: what difference may reflect data definition rather than real-world change. |
| Metadata and provenance study | 1. Select 3-6 related datasets or one dataset with rich documentation. 2. Build a metadata review table with publisher, steward, update date, field definitions, license/terms, access method, and contact. 3. Score each metadata element as present, partial, or missing. 4. Visualize documentation completeness. 5. Link one missing metadata element to a real reuse risk. | Slide 1: research question about reuse and trust. Slide 2: metadata scoring rubric. Slide 3: completeness table or bar chart. Slide 4: strongest and weakest documentation evidence. Slide 5: stewardship recommendations for improving reuse. |
| Bias and coverage analysis | 1. Choose a dataset with place, time, category, or demographic fields. 2. Load a small sample or filtered extract. 3. Group records by the chosen coverage dimension. 4. Compare counts, proportions, missingness, or rates across groups. 5. Check whether missing categories or sparse groups affect interpretation. 6. Write a limitation note about what the data does not observe. | Slide 1: coverage or representation question. Slide 2: dataset and variables used. Slide 3: coverage chart by place/time/category/group. Slide 4: missingness or sparse-data evidence. Slide 5: responsible interpretation and possible reporting/access bias. |
| Responsible web/API access study | 1. Choose one no-key or instructor-approved API. 2. Record documentation link, endpoint, parameters, row limit, and terms/rate-limit note. 3. Make one small API call with timeout and status-code check. 4. Compare two query designs, such as broad row limit vs. filtered request. 5. Save the raw response and parsed DataFrame. 6. Log request time, row count, fields, and any errors. | Slide 1: data-access research question. Slide 2: API design and responsible-use constraints. Slide 3: request log and parameter comparison. Slide 4: how query design changes what data is collected. Slide 5: recommended responsible collection practice. |
| Reproducibility and reliability audit | 1. Start from a small data workflow or group project notebook. 2. Run the notebook from top to bottom in a fresh runtime. 3. Record package versions if relevant, source URL, timestamp, row counts, schema checks, and key output values. 4. Add a fallback sample file for unstable sources. 5. Re-run with the fallback and compare expected outputs. 6. Create a reproducibility checklist. | Slide 1: reproducibility question. Slide 2: workflow diagram from source to result. Slide 3: run log with row counts/schema/output checks. Slide 4: failure or fallback test. Slide 5: recommendations for making the workflow easier to reproduce. |
| Small warehouse design evaluation | 1. Choose a small operational-style dataset. 2. State the analytical question and grain. 3. Draft two table models, such as one flat table and one fact/dimension model. 4. Implement one model in SQLite or pandas. 5. Run one analytical query. 6. Verify primary keys, foreign keys, row counts, and grain. 7. Explain why one model better supports the research question. | Slide 1: analytical question and grain. Slide 2: two candidate models. Slide 3: implemented SQLite/table design. Slide 4: query result and verification checks. Slide 5: design recommendation and tradeoffs. |
| Prompt reliability study | 1. Choose one small cleaning, extraction, or SQL task. 2. Save an initial broad prompt and its output. 3. Save a revised prompt with constraints, examples, expected output, and verification requirements. 4. Run both outputs if appropriate. 5. Compare errors, missing checks, assumptions, and correctness. 6. Summarize which prompt features improved reliability. | Slide 1: prompt-reliability research question. Slide 2: first prompt vs. revised prompt. Slide 3: output comparison table. Slide 4: verification/test results. Slide 5: practical prompting rules supported by evidence. |
| Ethical interpretation case study | 1. Choose a sensitive or policy-relevant public dataset, preferably aggregated. 2. Load a small sample and run one modest summary query. 3. Identify variables that are missing, proxy-like, biased, or difficult to interpret. 4. Separate supported claims from unsupported claims. 5. Create a risk table covering privacy, fairness, harm, missingness, and overclaiming. | Slide 1: research question and why interpretation matters. Slide 2: dataset and modest finding. Slide 3: supported vs. unsupported claims. Slide 4: ethical/stewardship risk table. Slide 5: responsible wording for reporting the result. |
| Data lifecycle mini-study | 1. Load a raw CSV/API sample and show the original rows. 2. Clean selected fields and record every transformation in a log. 3. Store the cleaned data as CSV and SQLite table. 4. Run one summary query from the final table. 5. Verify row counts and selected field values at raw, cleaned, stored, and summarized stages. 6. Identify one meaning change caused by cleaning or aggregation. | Slide 1: lifecycle research question. Slide 2: raw-to-cleaned-to-stored workflow. Slide 3: transformation log and verification checks. Slide 4: final query result. Slide 5: how transformations changed meaning, provenance, or trust. |

Suggested notebook-to-slide workflow:
- Program first: students should build the Colab notebook before designing the final slide story.
- Use notebook outputs as slide evidence: row-count tables, profiling summaries, charts, query results, verification checks, prompt revisions, and limitation tables.
- Avoid decorative slides that are not supported by notebook evidence.
- For every result slide, include one sentence that explains what the result means and one sentence that states what it does not prove.
- The final live demo should run the smallest reliable path; the slides can show saved results from earlier checks as long as the notebook explains how they were produced.

Projects should avoid claims such as "this proves the cause" or "this predicts the future." A stronger research posture is: "This small, reproducible demo measures one pattern, documents uncertainty, and explains what evidence would be needed for a stronger conclusion."

Minimum required project components:
- Data source: source name, URL/API endpoint or file source, publisher/steward, format, update date if available, and access method.
- Data gathering: small download, row-limited API call, instructor-provided extract, or uploaded sample.
- Data preparation: cleaning, type parsing, selected fields, missing-value handling, or text extraction.
- Storage choice: explain why the group used CSV, JSON, pandas DataFrame, SQLite tables, or a small warehouse/star-schema design.
- Query or analysis: at least one SQL or pandas query/summary that answers part of the project question.
- Verification evidence: row counts, field checks, query checks, join checks, sample inspection, or independent calculation.
- AI prompt trail: selected prompts or prompt cards, generated/revised code or query, and a brief note explaining what the group changed and why.
- Stewardship note: provenance, privacy, terms of use, bias, missingness, retention, reliability, or responsible interpretation.
- Limitation statement: what the demo cannot prove, what the sample excludes, and what would need to change for a larger or production version.

Recommended group roles:
- Source steward: documents source, metadata, access terms, update frequency, and provenance.
- Notebook lead: keeps the Colab notebook runnable, organized, and under 10 minutes.
- Data/model lead: handles cleaning, storage choice, SQLite/pandas tables, schema, or ETL sketch.
- Verification lead: designs row-count checks, schema checks, query checks, and sample inspections.
- Presentation lead: coordinates final demo flow, timing, and speaking transitions.

For groups of 4, combine presentation with source stewardship or verification. For groups of 6, add a second analyst or a responsible-use reviewer.

Project development path:

| Timing | Project activity | Relationship to individual assignments |
|---|---|---|
| Week 1 | Brainstorm possible topics and public/private data interests. | Individual setup artifact can become an idea pool. |
| Week 4 | Evaluate public datasets and identify quality/provenance issues. | Individual larger assignment helps students practice source evaluation before choosing a group source. |
| Week 7 | Test a possible source and validated query. | Individual larger assignment can become evidence for joining or forming a project group, but it is not yet the group project. |
| Week 10 | Design a mini warehouse, ETL sketch, or storage model. | Individual larger assignment gives students design options; groups may adopt, combine, or revise ideas afterward. |
| Week 13 | Submit final readiness/risk check. | Individual artifact confirms each student understands reproducibility and risk before group presentations. |
| Week 14 | Groups 1-2 present once. | Final group project demo: 30-35 minutes with slides, Colab/program demo, and every member demonstrating a defined part. |
| Week 15 | Groups 3-4 present once. | Final group project demo and course synthesis: 30-35 minutes with slides, Colab/program demo, and every member demonstrating a defined part. |

Final demo format:
- Total time per group: 30-35 minutes, including slides, program/notebook demo, and brief questions.
- Slides and program demo are both required. The slides explain the project purpose and design; the program demo proves the workflow runs.
- Every group member must demonstrate or explain a specific part of the project unless accommodations or group circumstances require a different arrangement.
- Recommended demo split: 5 minutes project question, source, and stewardship context; 7 minutes data gathering and preparation; 7 minutes storage/model choice and SQL or pandas query; 5 minutes verification evidence; 4 minutes AI prompt trail and student revisions; 4 minutes limitations, production-scale changes, and questions.
- The live program/notebook run should still stay under 10 minutes. Use saved intermediate outputs where needed so the total presentation can focus on explanation and evidence.
- The group should run only the small demo path live. Larger original data, future architecture, or production concerns may be described but should not be processed live.

Required member participation:
- Each member must own one visible presentation segment and one visible piece of evidence.
- Acceptable member segments include source/provenance, data gathering, cleaning/preparation, storage/schema/SQLite design, query or analysis result, verification checks, AI prompt trail, limitations, privacy/security/responsible-use risks, or demo coordination.
- For a 4-person group, each member should speak for roughly 5-7 minutes across slides and program evidence.
- For a 5-6 person group, each member should speak for roughly 4-6 minutes, with tighter transitions.
- A member's contribution is not satisfied by only advancing slides or saying an introduction; the student must explain a decision, show evidence, or demonstrate part of the notebook/program.

Final presentation scheduling note:
- Two groups at 30-35 minutes each require about 60-70 minutes before transition time. If two groups present in one meeting, plan an extended final-demo block or collect some peer questions in writing.
- If the meeting must remain exactly 60 minutes, set a hard 30-minute limit per group and move some questions or optional engagement notes to the online discussion/LMS.

Final submission:
- Colab notebook or `.ipynb` file.
- Any small sample data file needed to reproduce the demo, unless the notebook loads it from a stable public URL.
- Slide deck.
- Prompt trail appendix or notebook section.
- Stewardship and limitation note.
- Group contribution note naming each member's role and the part each member demonstrated.

Suggested grading emphasis:

| Criterion | What to look for |
|---|---|
| Data source, question, and research value | The source is appropriate, accessible, documented, and matched to a focused question that measures, compares, audits, validates, or explains a data problem. |
| Data gathering workflow | The notebook gathers or loads data reproducibly with row limits, clear paths, and no hidden credentials. |
| Storage/model choice | The group explains why the chosen representation fits the data and question. |
| Query/analysis result | The result is meaningful, modest, and supported by the data. |
| Verification | The group provides concrete evidence that the workflow and result are trustworthy. |
| AI prompt trail and revision | Prompts are specific, outputs are inspected, and student/group revisions are explained. |
| Stewardship and limitations | The group addresses provenance, privacy, bias, terms of use, missingness, reliability, and appropriate interpretation. |
| Demonstration quality | The demo is clear, timed, runnable, and shared across group members. |

## Dataset Sources and Project Inspiration

Students should choose datasets that support a clear data question, can be sampled small enough for a Colab demo, and include enough metadata to discuss provenance and responsible use. A good course dataset is not necessarily large; it is understandable, inspectable, and connected to a real decision or public question.

Dataset selection rules:
- Prefer CSV, JSON, SQLite, or simple API responses that can be limited to 100-5,000 rows.
- Prefer sources with visible metadata: publisher, update date, field descriptions, license or terms of use, and contact or steward.
- Avoid required use of accounts, paid keys, private credentials, large downloads, scraping at scale, or files that cannot run in less than 10 minutes.
- If the original source is large, use a sampled extract and explain what was sampled, filtered, or excluded.
- Choose topics where students can discuss limitations, bias, missingness, privacy, and responsible interpretation.

Recommended places to find datasets:

| Source | Good for | Colab-safe use |
|---|---|---|
| [Google Dataset Search](https://datasetsearch.research.google.com/) | Finding datasets across many repositories and disciplines. | Use it as a discovery tool; choose sources that provide small CSV/JSON downloads or clear metadata. |
| [Data.gov](https://data.gov/) | U.S. federal open data across health, climate, transportation, education, labor, agriculture, and more. | Use mainly for discovery and metadata review; then choose a small CSV/JSON resource from the publishing agency. Do not make catalog API keys required. |
| [New Jersey Open Data](https://data.nj.gov/) | State-level datasets relevant to New Jersey: education, health, transportation, labor, environment, treasury, and public safety. | Good default for locally relevant projects; use small tables or filtered extracts. |
| [NJ Geographic Information Network](https://www.nj.gov/njgin/) | New Jersey geospatial data, boundaries, roads, parcels, addresses, imagery, and GIS layers. | Use cautiously: many GIS files are large. Prefer metadata review, small tabular exports, or simplified boundary samples. |
| [OpenDataPhilly](https://opendataphilly.org/) | Philadelphia-region datasets across transportation, public safety, planning, real estate, health, parks, and city services. | Useful for regional case studies; choose small datasets or filtered API results. |
| [NYC Open Data](https://opendata.cityofnewyork.us/) | Large city datasets with many Socrata API endpoints, including 311, inspections, transportation, housing, and public services. | Always use row limits and filters; many datasets are too large for full download. |
| [Chicago Data Portal](https://chicago.socrata.com/) | City operations, 311, buildings, public safety, sanitation, transportation, parks, and community datasets. | Good for Socrata API examples; use small `$limit` values or exports. |
| [U.S. Census Bureau APIs](https://www.census.gov/data/developers.html) | Demographics, housing, economy, geography, ACS, and population data. | Strong source, but current Census API examples require a personal API key; use only as optional enrichment or provide an instructor-downloaded sample. |
| [CDC Open Data](https://data.cdc.gov/) | Public health datasets, indicators, surveys, and dashboards. | Choose aggregated public-health data; avoid sensitive interpretation and check metadata carefully. |
| [BLS Public Data API](https://www.bls.gov/developers/) | Labor, employment, unemployment, wages, CPI, prices, and economic time series. | Use unregistered/light API access for one or two series with a short year range; registered access is optional only. |
| [World Bank Indicators API](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392) | Country-level development indicators, population, GDP, education, health, poverty, energy, and environment. | Good no-key API source; use a few countries, one or two indicators, and a short date range. |
| [FRED API](https://fred.stlouisfed.org/docs/api/fred/) | Economic time series from the Federal Reserve Bank of St. Louis. | Useful for optional projects; some workflows require an API key, so provide a small downloaded CSV alternative. |
| [NOAA/NCEI Climate Data Online](https://www.ncdc.noaa.gov/cdo-web/webservices/v2) | Weather and climate data, stations, locations, and historical observations. | Good conceptually; the API requires a free token, so required demos should use instructor-provided samples unless tokens are arranged in advance. |
| [UCI Machine Learning Repository](https://archive.ics.uci.edu/) | Classic compact teaching datasets for classification, regression, and tabular analysis. | Strong choice for under-10-minute demos because many datasets are small and well documented. |
| [Kaggle Datasets](https://www.kaggle.com/datasets) | Inspiration, example notebooks, and many public datasets. | Use mainly for inspiration unless the dataset is small and accessible without complicated setup; avoid making Kaggle accounts required. |

Checked starter datasets and convenient access patterns:

| Starter dataset or API | Access pattern for students | Good demo use | Caution |
|---|---|---|---|
| NYC 311 Service Requests from 2020 to Present | JSON: `https://data.cityofnewyork.us/resource/erm2-nwe9.json?$limit=500`; CSV: `https://data.cityofnewyork.us/resource/erm2-nwe9.csv?$limit=500` | Public service requests, dates, agencies, complaint types, boroughs, status, data profiling, grouping, and filtering. | Very large source; never download full dataset for class. Use `$limit`, date filters, or borough filters. |
| Chicago 311 Service Requests | JSON: `https://data.cityofchicago.org/resource/v6vf-nfxy.json?$limit=500`; CSV: `https://data.cityofchicago.org/resource/v6vf-nfxy.csv?$limit=500` | Compare city-service categories, status fields, response patterns, and public-service metadata. | Use small limits. Portal terms and rate limits should be respected. |
| New Jersey Municipalities | JSON: `https://data.nj.gov/resource/k9xb-zgh4.json?$limit=600`; CSV: `https://data.nj.gov/resource/k9xb-zgh4.csv?$limit=600` | Clean local reference dataset for joins, codes, counties, municipality names, and storage-model examples. | Good safe starter because it is reference data rather than sensitive event data. |
| New Jersey Agency/Department Names | JSON: `https://data.nj.gov/resource/n3ie-tqf2.json?$limit=500`; CSV: `https://data.nj.gov/resource/n3ie-tqf2.csv?$limit=500` | Small lookup/reference table for joins, normalization, code/name mapping, and data documentation. | Limited analytical depth by itself; pair with another NJ table for richer projects. |
| New Jersey Purchasing by Vendor | JSON: `https://data.nj.gov/resource/piv7-rtxj.json?$limit=500`; CSV: `https://data.nj.gov/resource/piv7-rtxj.csv?$limit=500` | Government spending summaries, grouping by agency/vendor/year, data quality checks, and public finance questions. | Avoid overclaiming: spending data needs context and field definitions. |
| CDC U.S. Chronic Disease Indicators | JSON: `https://data.cdc.gov/resource/hksd-2xuw.json?$limit=500`; CSV: `https://data.cdc.gov/resource/hksd-2xuw.csv?$limit=500` | Aggregated health indicators, location/year filters, responsible interpretation, missing values, and public-health caveats. | Use only aggregated public data; avoid individual-level claims. |
| BLS public time-series API | `https://api.bls.gov/publicAPI/v1/timeseries/data/LNS14000000` | Unemployment or labor time-series demo, JSON parsing, date fields, trend summaries, and API response structure. | Unregistered access is limited; use one series and avoid repeated calls. |
| World Bank Indicators API | `https://api.worldbank.org/v2/country/usa;chn/indicator/SP.POP.TOTL?format=json&date=2015:2024` | Country-year indicators, JSON normalization, time-series comparison, missingness, metadata, and source notes. | Excellent no-key option, but students must choose meaningful indicators and avoid causal overclaims. |
| Data USA API | `https://api.datausa.io/tesseract/data.jsonrecords?cube=acs_yg_total_population_5&drilldowns=State,Year&measures=Population&include=Year:2023&limit=100,0` | No-key demographic/economic-style data, state/year summaries, JSON records, and comparison with Census concepts. | Use as a convenient teaching API; still discuss original data sources and metadata. |
| UCI Wine Quality | `https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-red.csv` | Direct small CSV download, data profiling, correlation, grouping by quality, and model/storage examples. | Semicolon-delimited CSV; students must set `sep=";"`. |
| UCI Wine | Use the UCI dataset page download or `ucimlrepo` import if already available. | Very small classification-style table for data structures, profiling, and storage demos. | Avoid long package installation; direct download or instructor sample is safer. |
| Data.gov catalog search | Web search through `https://data.gov/`; optional catalog examples may use `DEMO_KEY` or older read-only endpoints if available. | Dataset discovery, metadata inspection, publisher/source evaluation, and deciding whether a dataset is usable. | This is metadata, not usually the actual data. Do not make Data.gov catalog API access a required live demo. |

Preferred required-demo sources:
- Best no-key/API options: World Bank, Data USA, BLS unregistered light API, public Socrata JSON/CSV endpoints with row limits.
- Best local/regional options: New Jersey Municipalities, New Jersey Agency/Department Names, small filtered NJ Open Data tables.
- Best direct-download teaching data: UCI Wine Quality, small UCI tabular datasets, instructor-provided CSV/JSON extracts.
- Use with instructor support only: Census API, NOAA/NCEI API, FRED API, or any source requiring tokens, accounts, or private credentials.

Project inspiration by course theme:

| Theme | Possible question | Suggested sources |
|---|---|---|
| Public services | What kinds of service requests are most common, and how do they vary by neighborhood or time? | NYC Open Data, Chicago Data Portal, OpenDataPhilly, Data.gov |
| Transportation | Which transit, road, crash, parking, or bike-network patterns can be summarized responsibly? | NJ Open Data, OpenDataPhilly, NYC Open Data, Data.gov |
| Public health | How do aggregated health indicators vary across place, time, or demographic groups? | CDC Open Data, Data.gov, World Bank, Census |
| Economy and labor | How do unemployment, prices, wages, or industry indicators change over time? | BLS, FRED, Census, World Bank |
| Education | What enrollment, completion, access, or institutional patterns can be described without overclaiming causality? | Data.gov, Census, NJ Open Data, UCI sample datasets |
| Environment and climate | How do weather, air quality, or environmental indicators vary over time or place? | NOAA/NCEI, Data.gov, NJ Open Data, World Bank |
| Housing and neighborhoods | What can property, rent, permits, or demographic data show, and what privacy risks remain? | Census, NJ Open Data, OpenDataPhilly, NYC Open Data |
| Text and web mining | What patterns appear in short public text records such as complaints, descriptions, reviews, or job posts? | Open data portals with description fields, small instructor-provided text samples, Kaggle inspiration |
| Data warehousing | How can a small operational-style dataset be transformed into facts, dimensions, and analytical queries? | Instructor-created mini datasets, public CSV extracts, UCI tabular datasets |

Student dataset discovery prompts:

> I need a dataset for a graduate data gathering and warehousing project that can run in Google Colab free tier in less than 10 minutes. Suggest public datasets about [topic]. For each one, include the source, likely format, estimated size, metadata quality, privacy concerns, possible analytical questions, and whether it can be sampled to 100-5,000 rows.

> I found this dataset page: [link]. Evaluate whether it is suitable for a small Jupyter/Colab demo. Check access method, file format, size, metadata, license or terms, update date, fields, privacy risks, and three possible analyses. Also identify what the data cannot prove.

> Give me five project ideas using [Data.gov/NJ Open Data/Census/etc.] that involve data gathering, cleaning, storage choice, one query or summary, verification checks, and a stewardship note. Keep each idea small enough for an under-10-minute Colab demo.

> Turn this broad topic, [topic], into three specific data questions. For each question, recommend one likely dataset source, the minimum fields needed, one cleaning issue to expect, one storage/query choice, and one responsible-use concern.

## Source Folder Alignment

The redesigned material is intentionally built from the two existing lecture folders. The prompt-based layer changes how students practice and demonstrate learning, but the concepts remain anchored in the prior course materials.

Python workflow anchors from `lectures-python-programming`:
- `wk_02_Introduction_to_python.md`: notebook/runtime basics, variables, conditionals, loops, errors, and first exposure to objects.
- `wk_03_data_structures_and_algorithms_pt1.md`: arrays/lists/tuples, dictionaries, sets, maps, traversal, lookup, insertion, deletion, and structure choice.
- `wk_04_numbers_datetimes.md`: datetime parsing, formatting, arithmetic, timezones, UTC, and audit/log quality.
- `wk_04_strings_and_texts.md`: strings, regex, pattern matching, replacement, compiled patterns, bytes, and text cleaning.
- `wk_05_functions.md`: reusable functions, arguments, docstrings, lambda functions, type hints, and testable transformations.
- `wk_05_classes.md`: classes, objects, attributes, methods, constructors, abstract classes, and modeling choices.
- `wk_06_iterators_and_generators.md`: iteration, generators, large-file processing, memory efficiency, and stream-like traversal.
- `wk_07_modules_and_packages.md`: modules, packages, imports, aliases, introspection, and organizing reusable code.
- `wk_07_decorators_wrappers.md`: decorators, wrappers, logging, timing, validation, caching, and instrumentation.
- `wk_08_data_structures_and_algorithms_pt2.md`: linked lists, queues, stacks, graphs, trees, heaps, sorting/searching, recursion, and dependency modeling.
- `wk_09_data_encoding_and_processing.md`: CSV, JSON, pandas, SQLite, SQL execution, filtering, grouping, and summarization.
- `wk_10_files_and_io.md`: files, encodings, directories, metadata, globbing, temporary files, copying, deletion, and archives.
- `wk_11_network_and_web_programming.md`: HTTP, `urllib`, `requests`, headers, status codes, cookies, uploads, TCP/UDP, SSL/TLS, and event-driven I/O.
- `wk_13_concurrency.md`: threads, multiprocessing, executors, GIL, process pools, asyncio, and concurrency tradeoffs.

Data warehousing anchors from `lectures_data_warehousing`:
- `wk_02_reliable_scalable_maintainable_apps.md`: reliability, scalability, response time, percentiles, load, operability, simplicity, and evolvability.
- `wk_03_data_models_and_query_languages.md`: relational/document/graph models, schema flexibility, data locality, query languages, MapReduce, SPARQL, and Datalog.
- `wk_04_storage_and_retrieval.md`: hash indexes, SSTables, LSM-trees, B-trees, OLTP/OLAP, warehouses, star schemas, and column-oriented storage.
- `wk_05_encoding_and_evolution.md`: encoding formats, JSON/XML/CSV, binary encoding, Avro, compatibility, schema evolution, and modes of dataflow.
- `wk_06_replication_and_partitioning.md`: leaders/followers, sync/async replication, lag, failover, multi-leader and leaderless replication, quorums, partitioning, rebalancing, and routing.
- `wk_07_transactions.md`: transactions, ACID, read committed, snapshot isolation, lost updates, write skew, phantom reads, and serializability.
- `wk_08_distributed_systems.md`: partial failure, unreliable networks, timeouts, unreliable clocks, process pauses, quorums, fencing tokens, and Byzantine faults.
- `wk_09_consistency_and_concensus.md`: eventual consistency, linearizability, causal consistency, total order broadcast, two-phase commit, consensus, ZooKeeper, and etcd.
- `wk_10_batch_and_stream_processing.md`: Unix pipeline concepts, MapReduce, joins, hot keys, Spark/Tez/Flink, stream processing, Kafka-style logs, CDC, event sourcing, exactly-once/idempotence, and ethics. The Unix/Linux material should be translated into Python notebook examples or treated as conceptual background.

## In-Person Meeting Redesign

Design principle: both online and in-person weeks can use the same basic teaching arc: an instructor-led 35-minute concept and prompt lecture, a short student demonstration, questions, and an assignment checkpoint. In-person meetings should be necessary because they make explanation, critique, and accountability richer: students speak about their data choices, receive immediate questions, revise project artifacts together, and practice defending technical decisions in plain language.

Recommended 1-hour in-person rhythm:
- 35 minutes: Instructor lecture on the key concepts, prompt tricks, expected notebook artifact, and one prepared example.
- 10 minutes: One rotating student or team demonstration of the weekly assignment artifact.
- 10 minutes: Peer questions, instructor probing, or quick critique of the demonstrated prompt/output.
- 5 minutes: Exit item that records one revision, verification check, or stewardship risk.

In-person presentation expectations:
- Keep weekly student demonstrations short: about 10 minutes total for one student or one small team, except final project weeks.
- Require one concrete artifact: dataset preview, source evaluation, prompt trail, SQL query, schema sketch, ETL diagram, notebook output, verification check, or risk/provenance note.
- Ask presenters to answer three recurring questions: What data are you using? What decision did you make? What tradeoff or risk remains?
- Give listeners a role: ask one evidence question, one feasibility question, or one stewardship question.
- Use grading lightly for weekly demonstrations: completion, clarity, technical reasoning, verification evidence, and responsiveness to questions.

Type of student demonstration by in-person week:
- Week 1: orientation artifact. Students demonstrate a tiny Colab/Jupyter setup result and a possible data interest.
- Week 4: larger individual in-person demo assignment. Students demonstrate a dataset profile and source evaluation from a small public CSV/JSON extract.
- Week 7: larger individual in-person demo assignment and project-preparation demo. Students demonstrate a source pitch and one validated query/prompt idea that may become part of the project.
- Week 10: larger individual in-person demo assignment and project checkpoint demo. Students demonstrate a draft ETL/schema/storage design for critique; this is formative, not final.
- Week 14: final project demo for Groups 1-2.
- Week 15: final project demo for Groups 3-4.

| In-person week | Presentation/discussion purpose | Student artifact | Exit item |
|---|---|---|---|
| Week 1 | Instructor explains course structure, AI-assisted coding expectations, Colab workflow, and what counts as verification. Students briefly introduce data interests as setup for later project choices. | Tiny source-list notebook row plus saved/reloaded CSV check | One project idea or one question about data gathering |
| Week 4 | Larger individual in-person demo assignment: students explain a public dataset before analyzing it deeply. | Dataset profile and source evaluation: preview, source URL, metadata, field/type summary, quality check, limitation, and stewardship concern | One quality issue and one responsible-use concern |
| Week 7 | Larger individual in-person demo assignment: students connect source selection to query design and early project feasibility. | Source pitch and validated query: data question, two query prompts, one SQL/pandas result, and row-count/join verification | Revised project question and storage/query choice |
| Week 10 | Larger individual in-person demo assignment: students turn warehouse concepts into a formative project checkpoint. | Mini warehouse / ETL design checkpoint: star schema or table sketch, grain, ETL sketch, prompt trail, verification check, and revision | One schema or ETL revision based on peer feedback |
| Week 14 | Formal final presentations for Groups 1-2. Focus on evidence: data acquisition, AI prompt trail, student revisions, storage, cleaning/mining, verification, and provenance. Each member demonstrates a defined part. | Final project slide deck plus Colab/program demo | Engagement questions on technical clarity |
| Week 15 | Formal final presentations for Groups 3-4, followed by course synthesis. Focus on lessons learned, limits, reliability, privacy, and responsible use. Each member demonstrates a defined part. | Final project slide deck plus Colab/program demo | Course synthesis discussion on strongest design decisions and remaining risks |

Instructor facilitation notes:
- Treat Week 1 as orientation/setup, Weeks 4, 7, and 10 as larger individual in-person demo assignments, and Weeks 14 and 15 as final demo slots, with each group presenting once for 30-35 minutes.
- Use Weeks 1, 4, 7, and 10 for the full 35-minute instructor lecture plus a short individual student demonstration or checkpoint.
- Rotate who speaks so in-person time does not become dominated by the most confident students.
- When discussion slows, use prompts such as: "What would make this data source unreliable?", "What would you log for provenance?", "Who could be harmed by this data use?", and "What query or output would prove the pipeline works?"

Online lecture delivery:
- Keep the same 35/10/10/5 structure when synchronous online.
- Use the instructor lecture for concept explanation, prompt design, prepared AI output critique, and a prepared Colab example.
- Use the student slot for one screen-shared notebook demonstration: prompt, output, verification cell, and limitation.
- Require all students to submit the weekly artifact even when only one student demonstrates live.
- Record or post the instructor example notebook so students can compare their own AI-assisted work against a known small, runnable pattern.

## Part I: Data Gathering & Warehousing

This summary is based on the nine lecture markdown files in `lectures_data_warehousing`. The course appears to begin this lecture sequence at Week 2; no Week 1 file is present in this folder.

Suggested use in the hybrid course: keep core concept explanation, prepared AI-assisted examples, and reading checks in the regular lecture flow. When a data warehousing topic lands in an in-person week, keep the 35-minute instructor lecture and use the student slot for a short assignment artifact, project-preparation artifact, or project checkpoint where students explain prompts, outputs, tradeoffs, and verification evidence. Reserve full project presentations for Weeks 14-15.

## wk_02_reliable_scalable_maintainable_apps.md

Topic focus: Reliability, scalability, and maintainability as the foundation of data-intensive applications.

Key points:
- Data-intensive applications combine databases, caches, search indexes, stream processing, and batch processing.
- Reliability means functioning correctly despite hardware faults, software errors, human mistakes, abuse, and unexpected operating conditions.
- Fault tolerance is different from failure prevention; resilient systems assume components will fail and recover gracefully.
- Scalability requires defining load parameters before discussing performance or infrastructure growth.
- Response time should be understood through percentiles, especially p95/p99, rather than averages alone.
- Scaling up, scaling out, and elastic scaling are design choices tied to workload shape, not generic best practices.
- Maintainability depends on operability, simplicity, and evolvability.

Prompt-based emphasis:
- Ask AI to compare reliability, scalability, and maintainability risks for one familiar data product, then require students to correct or sharpen the answer.
- Have students prompt for likely load parameters, failure modes, and SLOs before deciding what evidence would validate those assumptions.
- Keep the technical takeaway centered on tradeoffs among reads, writes, latency, operational complexity, and what AI cannot know without workload evidence.

## wk_03_data_models_and_query_languages.md

Topic focus: Choosing data models and query languages for application and analytical needs.

Key points:
- Data models are layered abstractions that shape how developers, analysts, and systems reason about data.
- Relational databases remain strong for joins, constraints, many-to-many relationships, transaction processing, and analytics.
- Document databases reduce object-relational impedance mismatch and can improve locality for document-shaped data.
- Schema-on-read offers flexibility but shifts responsibility to readers; schema-on-write provides stronger guarantees earlier.
- Declarative query languages such as SQL describe desired results and allow the optimizer to choose execution strategies.
- MapReduce exposes distributed computation but is less ergonomic and less optimizable than declarative query pipelines.
- Graph models are appropriate when relationships and traversals are central, especially with many-to-many structures.

Prompt-based emphasis:
- Compare relational, document, and graph models by asking AI for alternatives for one shared scenario, such as student records, clinical visits, or social networks.
- Have students revise the prompt until the recommendation discusses joins, locality, schema evolution, query patterns, and data governance.
- Treat MapReduce as a bridge between query language design and distributed processing, with prompts focused on explanation and tradeoffs rather than implementation.

## wk_04_storage_and_retrieval.md

Topic focus: Storage engines, indexing, and the transition from OLTP systems to data warehousing.

Key points:
- Databases must store data durably and retrieve it efficiently; indexes speed reads but slow writes.
- Append-only logs simplify writes, crash recovery, and concurrency, but require compaction and segment management.
- Hash indexes work well for key-value lookups when keys fit in memory, but they do not support efficient range queries.
- SSTables and LSM-trees support high write throughput through sorted immutable files, memtables, compaction, and sparse indexing.
- B-trees are the dominant general-purpose index structure and support efficient lookups and range scans.
- OLTP workloads optimize for transactional reads/writes, while OLAP workloads optimize for large analytical scans and aggregation.
- Data warehouses use ETL and analytical schemas, often star schemas with fact and dimension tables.
- Column-oriented storage, compression, sorting, vectorized processing, and materialized views support warehouse analytics.

Prompt-based emphasis:
- Prompt AI to explain when an LSM-tree, B-tree, file export, or warehouse table would fit a given workload, then have students challenge vague claims.
- Spend substantial time on OLTP versus OLAP and why warehouses are separated from operational systems.
- Use a small star schema design activity where AI proposes fact/dimension tables and students verify grain, keys, and analytical questions.

## wk_05_encoding_and_evolution.md

Topic focus: Data encoding, schema evolution, compatibility, and dataflow between systems.

Key points:
- Application code and stored data evolve at different speeds; old and new code and data formats often coexist.
- Backward compatibility means newer code reads older data; forward compatibility means older code reads newer data.
- Encoding translates in-memory objects into byte sequences; decoding reconstructs objects from bytes.
- Language-native serialization can create portability, security, versioning, and efficiency problems.
- JSON, XML, and CSV are readable and common but have limitations around schemas, binary data, and numeric ambiguity.
- Binary schema-based formats such as Thrift, Protocol Buffers, and Avro are compact and better suited to controlled evolution.
- Avro handles reader and writer schema differences and is especially useful for dynamically generated database export schemas.
- Data flows through databases, service calls, and asynchronous message brokers; each mode has different compatibility and coupling concerns.
- Data outlives code, so stewardship requires careful migration, schema documentation, and long-term interpretability.

Prompt-based emphasis:
- Use compatibility as the anchor concept: students prompt AI to identify what could break during rolling upgrades and long-lived data storage.
- Compare JSON/CSV with Avro or protobuf from the perspective of governance, documentation, interoperability, and long-term interpretability.
- Include a short activity where students ask AI to classify schema changes, then independently verify forward/backward compatibility.

## wk_06_replication_and_partitioning.md

Topic focus: Replication, replication lag, conflict handling, partitioning, and request routing.

Key points:
- Replication improves latency, availability, and read throughput by keeping copies of data on multiple nodes.
- Single-leader replication centralizes writes, uses followers for reads, and requires failover planning.
- Synchronous replication improves durability and consistency but increases latency and availability risk.
- Asynchronous replication supports availability and read scaling but introduces replication lag and eventual consistency.
- Replication lag creates user-visible anomalies such as stale reads, non-monotonic reads, and inconsistent prefixes.
- Multi-leader replication can support multi-datacenter and offline use cases but requires conflict detection and resolution.
- Leaderless replication uses quorum reads/writes, read repair, anti-entropy, sloppy quorums, hinted handoff, and version vectors.
- Partitioning, or sharding, distributes data and workload; poor partitioning creates skew and hot spots.
- Key-range partitioning supports range scans but can skew; hash partitioning balances load but weakens range-query efficiency.
- Secondary indexes, rebalancing, service discovery, and parallel query execution complicate distributed database design.

Prompt-based emphasis:
- This file is dense; focus the meeting on three AI-assisted design decisions: replication strategy, consistency expectation, and partitioning strategy.
- Use one scenario, such as a national student information system or event-tracking platform, and ask students to prompt for leader/follower, multi-leader, or leaderless designs.
- Require students to name the tradeoff AI underexplained, such as replication lag, conflict handling, hot partitions, or routing complexity.

## wk_07_transactions.md

Topic focus: Transactions, ACID guarantees, weak isolation, concurrency anomalies, and serializability.

Key points:
- Transactions group reads and writes into a unit that commits or aborts together, simplifying fault and concurrency handling.
- ACID separates atomicity, consistency, isolation, and durability, but consistency is partly an application-level responsibility.
- Safe retries require careful handling of commits, side effects, network failures, overload, and idempotence.
- Read committed prevents dirty reads and dirty writes but does not prevent all race conditions.
- Snapshot isolation/MVCC gives each transaction a consistent view, helping with backups, analytics, and read skew.
- Lost updates occur when concurrent read-modify-write cycles overwrite one another.
- Atomic updates, explicit locks, compare-and-set, and automatic conflict detection help prevent lost updates.
- Write skew and phantom reads show why snapshot isolation is not the same as serializability.
- Serializable isolation can be implemented through serial execution, two-phase locking, or serializable snapshot isolation.
- Stronger isolation improves correctness but may reduce throughput or increase aborts and latency.

Prompt-based emphasis:
- Teach the anomalies through examples: dirty read, lost update, read skew, write skew.
- Ask students to prompt AI for diagnosis and mitigation, then require them to defend which isolation level or mechanism actually fits.
- Connect transaction isolation to data stewardship: auditability, correctness, and protection from subtle data corruption.

## wk_08_distributed_systems.md

Topic focus: Partial failure, unreliable networks, unreliable clocks, process pauses, and distributed truth.

Key points:
- Distributed systems differ from single-machine programs because partial failures are normal and nondeterministic.
- Network requests can be lost, delayed, queued, duplicated, or receive no response, making failure interpretation uncertain.
- Timeouts are necessary but always represent a tradeoff between slow failure detection and false failure detection.
- Queueing, congestion, virtualization, TCP flow control, and overloaded processes all contribute to unbounded delays.
- Physical clocks are risky for ordering events because clocks drift, jump, and carry uncertainty.
- Monotonic clocks are useful for elapsed time, while logical clocks are better for causal ordering.
- Process pauses from garbage collection, VM suspension, OS scheduling, paging, or signals can invalidate lease and leadership assumptions.
- Quorums help systems avoid trusting one node's local judgment.
- Fencing tokens protect shared resources when a paused or old leader resumes acting after losing authority.
- Byzantine faults introduce the harder case of nodes acting dishonestly or arbitrarily.

Prompt-based emphasis:
- Center the session on the idea that a timeout is a guess, not proof.
- Use a failure scenario where students ask AI to narrate a leader pause, lease expiration, stale write, and fencing-token protection.
- Connect technical uncertainty to operational practices: monitoring, fault injection, recovery drills, and skepticism toward clean AI explanations of messy failures.

## wk_09_consistency_and_concensus.md

Topic focus: Consistency guarantees, linearizability, causal ordering, total order broadcast, atomic commit, and consensus.

Key points:
- Eventual consistency means replicas converge if writes stop, but applications must tolerate temporary disagreement.
- Linearizability makes replicated data appear as a single up-to-date copy with atomic operations.
- Serializability concerns transaction ordering; linearizability concerns real-time recency of reads and writes.
- Locks, leader election, uniqueness constraints, and compare-and-set require strong coordination.
- CAP is useful historically but too narrow for practical design because it focuses on network partitions and linearizability only.
- Causal consistency preserves cause-before-effect relationships without requiring a global total order for every concurrent event.
- Lamport timestamps provide a causally consistent ordering mechanism based on counters and node IDs.
- Total order broadcast lets all nodes deliver the same messages in the same order and underpins state machine replication.
- Two-phase commit provides atomic commit across participants but can block if the coordinator fails.
- Consensus protocols such as Paxos, Raft, Zab, and Viewstamped Replication allow fault-tolerant agreement but require majorities and add operational cost.
- ZooKeeper and etcd provide coordination primitives such as locks, leader election, service discovery, fencing tokens, and change notifications.

Prompt-based emphasis:
- Focus on why different guarantees exist, not on proving consensus protocols.
- Use uniqueness of usernames or leader election as the recurring example for AI-assisted explanation and critique.
- Distinguish timeliness, availability, and correctness so students do not reduce the topic to "CAP says pick two."

## wk_10_batch_and_stream_processing.md

Topic focus: Batch processing, MapReduce, dataflow engines, stream processing, event logs, CDC, event sourcing, and ethical data systems.

Key points:
- Batch systems process bounded data offline; stream systems process unbounded event data continuously or near-real-time.
- Unix pipelines demonstrate durable composability: simple tools, byte-stream interfaces, stdin/stdout, and inspectable intermediate results; in this redesign, the idea should be demonstrated with Python notebook cells rather than required shell commands.
- MapReduce generalizes batch processing over distributed filesystems such as HDFS using map, shuffle, sort, and reduce stages.
- MapReduce favors immutable input and side-effect-free jobs, making recovery and reprocessing easier.
- Joins, hot keys, skew, batch output loading, and index building are major practical batch-processing concerns.
- Spark, Tez, and Flink reduce MapReduce materialization overhead with dataflow execution and lineage/checkpoint-based fault tolerance.
- Stream processing depends on producers, consumers, topics, brokers, acknowledgements, offsets, ordering, backpressure, and durability.
- Log-based brokers such as Kafka retain append-only event histories and allow replay, fan-out, consumer offsets, and partitioned throughput.
- Change data capture turns database write logs into streams for search indexes, caches, warehouses, and other derived data systems.
- Event sourcing stores application changes as immutable events and derives current state from the event log.
- Stream processing must handle event time versus processing time, windows, late events, joins, state, idempotence, and exactly-once/effectively-once semantics.
- Log-based data integration can avoid some distributed transaction costs through deterministic processing, idempotent writes, and replayable derived views.
- The closing ethical section emphasizes privacy, tracking, surveillance, bias, accountability, auditing, human dignity, consent, and responsible retention.

Prompt-based emphasis:
- Treat this as a capstone that ties architecture to stewardship.
- Prompt AI to compare batch versus stream, event logs, CDC/event sourcing, and exactly-once/idempotence for a project scenario.
- End with the ethics section: ask students how data collection, retention, derived views, tracking, and AI-generated assumptions affect privacy, accountability, and public trust.

## Part II: AI-Assisted Python and Data Workflow Lectures

This summary is based on the 14 lecture markdown files in `lectures-python-programming`. The folder starts at Week 2, has split topics for Weeks 4, 5, and 7, and has a file named `wk_13_concurrency.md` whose internal lecture header says Week 12.

Suggested use in the hybrid course: keep Python syntax as functional literacy, not the center of the course. Students should learn enough to read, run, modify, and verify AI-generated code. When a Python topic lands in an in-person week, keep the instructor-led lecture structure and use the student slot for prompt critique, output inspection, peer debugging, communication practice, or a project checkpoint. Reserve full project presentations for Weeks 14-15.

## wk_02_Introduction_to_python.md

Topic focus: Programming foundations, Python syntax, control flow, loops, and first exposure to OOP.

Key points:
- Programming means giving precise instructions to computers through a programming language.
- Python is presented as an interpreted or p-code language that executes source code through an interpreter/runtime process.
- Students need comfort with the interpreter, `print()`, errors, indentation, comments, and basic syntax.
- Variables are created by assignment and should follow readable naming conventions such as snake case.
- Core data types include numbers, strings, booleans, lists, dictionaries, and related structures.
- Numeric work includes integers, floats, complex numbers, arithmetic, conversion, and floating-point precision limits.
- Conditional logic uses Boolean expressions with `if`, `elif`, and `else`.
- Loops support repeated execution through `while`, `for`, `break`, and `continue`.
- OOP is introduced through inheritance, encapsulation, abstraction, and polymorphism.

Prompt-based emphasis:
- Use this as an AI coding orientation session, not a full OOP mastery session.
- Prioritize notebook execution, variables, conditionals, loops, reading errors, and asking AI to explain generated code line by line.
- Close with one small applied task, such as prompting for a data-record validator, running it, testing edge cases, and revising the prompt.

## wk_03_data_structures_and_algorithms_pt1.md

Topic focus: Built-in data structures, basic operations, and choosing structures based on use case.

Key points:
- Data structures organize storage and retrieval; algorithms define steps for processing data.
- Structure choice should follow access patterns, such as frequent lookup versus infrequent insertion.
- Arrays, lists, and tuples are ordered sequence-like structures with different mutability and type constraints.
- Lists are Python's flexible dynamic array; arrays enforce consistent element types; tuples are immutable.
- Students practice traversal, access, insertion, deletion, search, and update operations.
- Dictionaries represent hash tables with key-value associations, fast lookup, unique keys, and immutable key requirements.
- Dictionary comprehensions support compact construction, filtering, sorting, and transformation.
- Sets store distinct unordered values and support union, intersection, difference, subset, and superset operations.
- `ChainMap` combines multiple dictionaries into one logical view and can model stacked contexts.

Prompt-based emphasis:
- Anchor the session in data-work decisions: students prompt AI to choose a list, tuple, set, dictionary, JSON record, or table, and then critique the choice.
- Use a short restaurant, student, or transaction dataset and ask students to model it multiple ways.
- Include a quick complexity discussion without turning the session into a formal algorithms course.

## wk_04_numbers_datetimes.md

Topic focus: Datetime creation, formatting, arithmetic, and timezone awareness.

Key points:
- Python's `datetime` module represents dates and times for analysis and automation.
- Students create datetime objects manually and retrieve current timestamps with `datetime.now()`.
- Parsing and formatting convert between strings and datetime values using format codes.
- Date arithmetic supports computing differences between temporal values.
- Datetimes may be naive or aware depending on whether timezone information is attached.
- UTC is the preferred default for storage and arithmetic because it avoids daylight-saving ambiguity.
- `pytz` is introduced for localizing naive datetimes and converting among timezones.

Prompt-based emphasis:
- Make the session practical: prompt AI to parse messy date strings, convert to UTC, and calculate elapsed time.
- Connect time handling to data quality, audit trails, logs, and reproducible analytics.
- Require students to test daylight-saving, timezone, and invalid-date cases because these are common hidden sources of AI-generated bugs.

## wk_04_strings_and_texts.md

Topic focus: String processing and regular expressions in Python.

Key points:
- Regular expressions are a specialized language for matching, validating, extracting, and replacing text.
- Python's standard `re` module provides regex functions and pattern objects.
- `re.search()` checks whether a pattern appears and returns a match object or `None`.
- Regex match results can be used directly in conditional expressions.
- Flags such as `re.IGNORECASE` change matching behavior.
- `re.sub()` performs pattern-based replacement with optional count and flags.
- `re.compile()` is useful when a pattern will be reused many times.
- Regex patterns should generally be written as raw strings.
- Bytes require bytes patterns, such as `rb'...'`, rather than regular string patterns.

Prompt-based emphasis:
- Use realistic data cleaning examples: email checks, ID extraction, whitespace cleanup, and field normalization.
- Emphasize when regex is appropriate and when ordinary string methods are simpler; students should ask AI for both options when unsure.
- Let students test AI-generated patterns in their own notebook work and explain false positives and false negatives.

## wk_05_functions.md

Topic focus: Function design, arguments, scope, docstrings, lambdas, and type hints.

Key points:
- Functions organize related statements into reusable units and reduce repetition.
- User-defined functions use `def`, names, optional parameters, optional returns, and indented bodies.
- Local variables exist inside function scope and are discarded when execution ends unless returned or otherwise preserved.
- Default arguments, keyword arguments, `*args`, and `**kwargs` support flexible function interfaces.
- Docstrings document function purpose and can be inspected programmatically.
- Lambda functions support concise anonymous functions with one expression.
- Python is dynamically typed, but type hints support clearer contracts and optional static analysis.
- Type hints can describe arguments, return values, variables, unions, lists, dictionaries, sets, and `None` returns.

Prompt-based emphasis:
- Center on asking AI for small, testable functions for data transformations rather than large one-shot scripts.
- Have students prompt for docstrings, type hints, and example tests, then revise the generated function signature for clarity.
- Discuss how function signatures act as documentation for collaborative data projects and as constraints for AI-generated code.

## wk_05_classes.md

Topic focus: Python classes, objects, attributes, methods, constructors, abstract classes, and mixins.

Key points:
- A class is a blueprint for objects that combine state and behavior.
- Objects are instances with attributes and methods.
- The `class` keyword defines a new type; `pass` can hold a placeholder class body.
- Attributes store state, while methods operate on object state.
- `__init__()` initializes instances when objects are created.
- `self` refers to the current instance and gives methods access to instance attributes.
- Built-in class attributes such as `__dict__`, `__doc__`, `__name__`, `__module__`, and `__bases__` expose class metadata.
- Abstract base classes define required behavior and prevent incomplete subclasses from being instantiated.
- Concrete classes provide implementations for required methods.
- Mixins provide narrow reusable behavior through multiple inheritance.

Prompt-based emphasis:
- Focus on modeling: students ask whether a data record, validator, loader, or report should be represented as a class, dictionary, dataclass, or table.
- Use one small domain class with constructor, attributes, and methods before touching abstract classes.
- Treat abstract classes and mixins as advanced patterns for extensible codebases, not required patterns for every AI-generated solution.

## wk_06_iterators_and_generators.md

Topic focus: Iteration protocol, memory-efficient traversal, and generators.

Key points:
- Iterators return one value at a time and implement `__iter__()` and `__next__()`.
- Python `for` loops work by creating an iterator and repeatedly calling `next()` until `StopIteration`.
- Iterators reduce memory use by avoiding loading all values at once.
- Generators produce sequences using functions and `yield`.
- `yield` pauses a function and preserves its state so execution can resume later.
- Generators are useful for large files, data streams, and infinite sequences.
- A naive function that reads an entire large file can exhaust memory; a generator can process one row at a time.

Prompt-based emphasis:
- Make memory efficiency the core concept.
- Have students prompt AI for two versions of a file-processing task: one that reads all rows into memory and one that processes rows incrementally.
- Connect generators to data pipelines, log processing, and streaming analytics by requiring students to explain when memory or latency matters.

## wk_07_modules_and_packages.md

Topic focus: Organizing reusable Python code through modules, packages, imports, aliases, and introspection.

Key points:
- A module is a `.py` file containing related functions, classes, or variables.
- Modules reduce duplication, limit interdependency, and help organize functionality around small tasks.
- A package is a directory or collection of modules with a hierarchical namespace.
- Imports expose module contents to another script.
- Import aliases with `as` improve readability or reduce verbosity.
- `dir()` lists named objects available in a module.

Prompt-based emphasis:
- Use this as a software organization lab for AI-generated notebooks and scripts.
- Have students ask AI to split a small script into reusable functions/modules and a main workflow, then check whether the organization is actually clearer.
- Connect module organization to maintainable analytics, reproducibility, and collaboration in data engineering projects.

## wk_07_decorators_wrappers.md

Topic focus: Metaprogramming with decorators and wrappers.

Key points:
- Decorators modify or extend function or class behavior without permanently changing the original object.
- A decorator can take a function as input and return wrapped behavior.
- Inner wrapper functions allow code to run before and after the decorated function.
- The `@decorator` syntax applies a decorator directly above a function definition.
- Decorators can accept their own arguments by returning another decorator function.
- Decorators are a foundation for logging, timing, validation, authentication, caching, and instrumentation patterns.

Prompt-based emphasis:
- Teach decorators through one practical pattern, such as timing a data-cleaning function or logging function calls.
- Keep nested-function mechanics visible but do not over-formalize metaprogramming.
- Ask students where AI-suggested decorators could support reproducibility, auditing, or observability, and when they would add unnecessary complexity.

## wk_08_data_structures_and_algorithms_pt2.md

Topic focus: User-defined structures, linked lists, queues, stacks, graphs, trees, heaps, and algorithm patterns.

Key points:
- User-defined data structures reproduce behaviors not directly provided by Python's core built-ins.
- Linked lists consist of nodes with data and references to the next node.
- Linked-list operations include traversal, insertion, deletion, and search.
- `collections.deque` supports efficient queue and stack behavior.
- Queues follow first-in/first-out ordering; stacks follow last-in/first-out ordering.
- Graphs model nodes and edges and are suitable for relationship-centered problems.
- Binary trees organize hierarchical data and support traversal patterns such as inorder, preorder, and postorder.
- Heaps support priority-queue behavior through `heapq`.
- Algorithms should be clear, finite, feasible, input/output-aware, and independent of implementation language.
- Sorting and searching include linear search, interpolation search, bubble sort, merge sort, insertion sort, shell sort, and selection sort.
- Recursion, divide-and-conquer, and backtracking are core algorithm design patterns.

Prompt-based emphasis:
- Focus on queues, stacks, graphs, and heaps as practical structures used in data workflows.
- Have students prompt AI to map real data tasks to structures, such as task queues, dependency graphs, and priority processing.
- Treat manual linked-list/tree code as conceptual scaffolding; students should learn to recognize when AI is producing academic examples instead of practical Python.

## wk_09_data_encoding_and_processing.md

Topic focus: CSV, JSON, relational databases, pandas, and basic data summarization.

Key points:
- Data work often requires moving information into and out of programs through CSV, JSON, XML, and databases.
- Python's `csv` library reads rows as sequences or dictionaries and writes rows through writer objects.
- Pandas provides high-level data frames for reading, writing, filtering, grouping, and summarizing tabular data.
- JSON is a lightweight language-independent interchange format for arrays and objects.
- Python's `json` module uses `dumps()`/`loads()` for strings and `dump()`/`load()` for files.
- Hooks such as `object_pairs_hook` can customize JSON decoding behavior.
- Relational database interaction is introduced through `sqlite3`, connections, cursors, SQL execution, transactions, and commits.
- Rows returned from relational databases can be handled as tuples.
- Pandas supports exploratory data analysis through column inspection, filtering, value counts, grouping, and sorting.

Prompt-based emphasis:
- Build one AI-assisted mini-pipeline: read CSV or JSON, clean/select fields, store/query with SQLite or summarize in pandas.
- Emphasize encoding choices, data types, missing values, and reproducible transformations.
- Require students to submit the prompt, generated code or query, student edits, validation checks, and a short provenance note.

## wk_10_files_and_io.md

Topic focus: File handling, encodings, directories, metadata, pattern matching, temporary files, copying, deletion, and archives.

Key points:
- Files are durable named locations on disk and require open, operation, and close steps.
- `open()` supports modes for reading, writing, appending, exclusive creation, text, binary, and updating.
- File encodings matter; UTF-8 should be explicit when portable behavior is important.
- Context managers with `with` are the safest standard way to ensure files close properly.
- Reading can use `read()`, `readline()`, iteration, `seek()`, and `tell()`.
- The `os` module supports directory listing, path checks, metadata, and directory creation.
- `os.scandir()` can efficiently inspect directory contents and metadata.
- Filename selection can use `startswith()`, `endswith()`, `fnmatch`, or `glob`.
- `tempfile` supports short-lived file-like objects.
- `os.remove()`, `os.unlink()`, `os.rmdir()`, and `shutil.rmtree()` remove files and directories at different scopes.
- `shutil.copy()`, `copy2()`, `move()`, and `os.rename()` support file management.
- `zipfile`, `tarfile`, and `shutil` support creating, reading, extracting, packing, and unpacking archives.

Prompt-based emphasis:
- Use a directory-processing lab: students prompt AI to find matching files, read with explicit encoding, summarize metadata, and archive outputs.
- Emphasize responsible handling of deletion and overwrite operations; AI-generated destructive commands must be rewritten or removed unless explicitly justified.
- Connect file I/O to data ingestion, retention, backup, reproducibility, and platform portability.

## wk_11_network_and_web_programming.md

Topic focus: HTTP clients, requests, TCP/UDP servers, interpreter messaging, SSL/TLS, and event-driven I/O.

Key points:
- HTTP supports client-server communication and common methods such as GET, HEAD, POST, PUT, DELETE, PATCH, and OPTIONS.
- `urllib` can handle simple HTTP requests, query parameters, POST bodies, and headers.
- The third-party `requests` library is better suited to authentication, cookies, uploads, status codes, headers, text, bytes, and JSON responses.
- TCP provides connection-oriented bidirectional communication through sockets.
- `socketserver` supports simple TCP servers, stream handlers, and threaded/forked server variants.
- UDP sends datagrams without connection setup, ordering guarantees, or delivery confirmation.
- `multiprocessing.connection` allows Python interpreters to exchange serialized messages.
- SSL/TLS protects privacy, authentication, and integrity for network communication.
- SSL can wrap sockets directly or be mixed into existing socketserver-based services.
- Event-driven I/O converts read/write readiness into events handled by callbacks or event loops.
- Event loops can handle many simultaneous connections but block if handlers run long computations or blocking library calls.

Prompt-based emphasis:
- Prioritize HTTP APIs and `requests` for data gathering.
- Give TCP/UDP/SSL/event-loop material as conceptual extension for students building services or data collectors.
- Use a prepared example where the instructor shows the prompt, sample AI output, and verified notebook result for calling an API, checking status/headers, parsing JSON, handling failures, respecting rate limits, and documenting source terms.

## wk_13_concurrency.md

Topic focus: Concurrency, threading, multiprocessing, executors, the GIL, and asyncio.

Key points:
- Concurrency means tasks overlap in execution and can improve responsiveness or throughput.
- Correct concurrent systems must satisfy correctness, safety, and liveness properties.
- Threads are lightweight units of execution that share memory inside a process.
- Multithreading can improve responsiveness and I/O throughput but adds complexity, synchronization risk, deadlocks, and shared-state hazards.
- Python's `threading.Thread` runs a callable concurrently and supports `start()`, `is_alive()`, `join()`, and daemon threads.
- The Global Interpreter Lock limits parallel execution of Python bytecode, making threads poor for CPU-bound parallelism but useful for I/O-bound work.
- Multiprocessing uses separate processes and can bypass the GIL for CPU-bound tasks.
- `concurrent.futures` provides higher-level `ThreadPoolExecutor` and `ProcessPoolExecutor` abstractions.
- Use `ThreadPoolExecutor` for I/O-bound tasks and `ProcessPoolExecutor` for CPU-bound workloads.
- Algorithm choice and vectorized libraries such as NumPy may outperform naive parallelization.
- `asyncio` supports single-threaded cooperative concurrency through event loops, futures, coroutines, and protocols.
- Blocking operations can stall an async event loop, so async code requires careful library choices.

Prompt-based emphasis:
- Frame the session around choosing the right concurrency model: threads, processes, async, batch scheduling, or no concurrency at all.
- Use small AI-assisted examples: parallel web requests with threads, CPU work with process pools, and one coroutine demo.
- Connect concurrency to data gathering workloads, API rate limits, longer-running real-world tasks discussed conceptually, reproducibility, and reliability.

## Reusable Prompt Patterns

Use these prompt patterns as starting points. Students should customize them with the dataset, constraints, expected output, and verification method.

Data source evaluation:
> I am considering using [source name/link] for a graduate data gathering project about [topic]. Identify the likely fields, access method, licensing or terms-of-use concerns, privacy risks, provenance questions, update frequency, and three analyses this source can reasonably support. Also list three analyses it cannot support without additional data.

Data profiling:
> Given this CSV/JSON schema or sample rows: [paste sample]. Propose a data profile checklist with column types, missing-value checks, duplicate checks, range checks, categorical summaries, suspicious values, and join-key issues. Return the checks as a table and include the exact Python or SQL needed to verify each one.

Code generation with constraints:
> Write Python for Google Colab free tier that [task]. Constraints: standard CPU runtime only, less than 10 minutes of runtime, no paid GPU/TPU, no long-running jobs, no distributed workers, no persistent servers, readable beginner-friendly code, small sample or row-limited data, avoid destructive file operations, handle missing values, print row counts before and after cleaning, and include three small tests or spot checks. Explain any assumptions before the code.

Debugging:
> This code produced the following error: [error]. Explain the likely cause in plain language, ask what information is missing if needed, and suggest the smallest change that fixes it. Do not rewrite the whole program unless necessary.

SQL/query design:
> I have tables [table names and columns]. My analytical question is [question]. Propose two SQL queries: one simple version for validation and one final version for analysis. Explain joins, filters, grouping, expected row counts, and possible sources of misleading results.

Storage model selection:
> For a project with [data source], [data volume], [update frequency], [query patterns], and [privacy/security constraints], compare CSV/files, SQLite/relational tables, document storage, graph storage, and a warehouse/star schema. Recommend one option and explain the tradeoffs.

Warehouse design:
> Design a draft star schema for analyzing [business/research process]. Identify the grain of the fact table, candidate dimensions, measures, keys, slowly changing attributes, and two example analytical queries. Flag any assumptions that require confirmation from the data source.

Verification and audit:
> Review this AI-generated code/query/result for data gathering and warehousing. Identify assumptions, possible bugs, missing validation checks, privacy/provenance concerns, and at least five concrete checks I should run before trusting the output.

Colab feasibility check:
> Review this planned notebook for Google Colab free tier. Identify any step that may exceed standard CPU/runtime/memory limits, require paid hardware, run too long, create a service, use distributed workers, make too many API requests, write too many Drive files, or depend on credentials students may not have. Suggest a smaller free-tier-safe version.

Reflection:
> Based on my prompt, generated output, edits, and verification results below, help me write a concise reflection explaining what worked, what I changed, what remains uncertain, and how the workflow supports responsible data use. Do not overstate certainty.
