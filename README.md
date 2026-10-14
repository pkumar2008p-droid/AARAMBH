Aarambh Follow-up Navigator
 Care That Fits Real Life

Aarambh Follow-up Navigator is an AI-assisted healthcare coordination system proposed to improve continuity of care in high-volume hospital environments. It helps patients understand clinician-approved follow-up instructions, identify practical barriers, plan their next visit, and receive appropriate assistance. It also helps hospital staff identify unresolved follow-up cases, reconcile records, coordinate administrative actions, and verify outcomes.

The project is developed as a solution concept for the AI Synergy Hackathon 2026 Round 1 Case Investigation Challenge, The Follow-Up Blind Spot.

Problem

Hospitals may issue follow-up instructions without knowing whether patients understand them, can be contacted safely, can travel to the facility, or complete the recommended next step.

Common challenges include unclear medical instructions, shared or unreachable phone numbers, long travel distances, uncertain waiting times, incomplete attendance records, and limited staff capacity.

These challenges can cause genuine follow-up gaps and incorrectly classified missed appointments.

Aarambh Follow-up Navigator aims to connect patient understanding, access support, visit planning, staff coordination, and outcome verification through one structured workflow.

## Project Objectives

1. Improve patient understanding of clinician-approved follow-up instructions.
2. Identify missing or conflicting appointment and follow-up information.
3. Capture patient-reported barriers related to communication, travel, accessibility, and contact preferences.
4. Support safe and consent-aware patient communication.
5. Provide visit planning assistance using reliable appointment, travel, and queue information.
6. Help hospital staff manage unresolved follow-up cases through a structured task queue.
7. Reconcile attendance records before classifying a patient as having missed an appointment.
8. Maintain traceable records of staff actions, corrections, and verified outcomes.
9. Support multilingual communication and non-digital access pathways.
10. Evaluate whether the proposed workflow improves coordination and follow-up completion.

## Proposed Solution

Aarambh Follow-up Navigator introduces an AI-assisted coordination layer between patients, clinicians, and hospital administrative teams.

The system begins with a clinician-approved follow-up plan. It validates the required information, prepares an accessible explanation, checks whether the patient understands the next step, and captures relevant contact preferences and access barriers.

When dependable data are available, the system provides visit planning guidance. Cases requiring clarification, contact verification, barrier support, or outcome review are assigned to the appropriate staff workflow.

The final status is established using an authoritative record or authorised staff confirmation rather than assuming that a message or call proves successful follow-up.

## Core Workflow

Clinician-approved follow-up plan

Input validation and record reconciliation

Patient-friendly explanation

Patient understanding confirmation

Contact preference and consent verification

Barrier identification and visit planning

Staff coordination and administrative action

Follow-up status reconciliation

Verified outcome and audit record

## Core Modules

### 1. Follow-up Plan Capture

Receives or records clinician-approved instructions, appointment windows, hospital location, and responsible clinical service.

Missing, outdated, malformed, or contradictory information is flagged for clarification. The system must not invent missing medical instructions or appointment details.

### 2. Accessible Explanation

Uses AI-assisted language rewriting to convert approved instructions into clear and patient-friendly language.

The generated explanation remains linked to its original source. Supported languages, terminology, and templates require appropriate validation. The original clinician-approved instructions remain unchanged.

### 3. Patient Understanding Check

Allows patients to confirm their understanding, indicate uncertainty, or request assistance.

The system records understanding as confirmed, unclear, assistance requested, or unknown. Message delivery alone is not treated as evidence that the patient understands the instructions.

### 4. Contact and Barrier Management

Records relevant contact preferences, consent status, language preferences, contact failures, and patient-reported practical barriers.

The system distinguishes between an unreachable contact, a patient who has requested assistance, and a patient who has not attended.

Shared household phone numbers require appropriate consent and recipient verification before sensitive information is disclosed.

### 5. Visit Planning

Provides appointment information, required check-in guidance, estimated travel duration, and predicted waiting time when reliable data are available.

Suggested departure time for a scheduled appointment is calculated using the appointment time, estimated travel duration, and required check-in buffer.

Waiting-time estimates are displayed separately from the required arrival time. Estimates include their source, update time, and uncertainty where applicable.

When the required data are missing or unreliable, the system displays that an estimate is unavailable and preserves the hospital's official instructions.

### 6. Staff Coordination Dashboard

Organises unresolved cases into actionable categories.

Needs Clarification

Contact or Access Barrier

Follow-up Due or Unverified

Visit Plan

Completed or Verified

Each case should display its current status, reason for the flag, relevant source information, responsible staff member, last update, and next administrative action.

### 7. Outcome Verification

Records attendance checks, follow-up status, staff actions, corrections, and verified outcomes.

Completion must be supported by an authoritative record or authorised staff confirmation. Sending a reminder or attempting a call does not count as completed care.

## Intended Users and Access Control

### Patients and Authorised Caregivers

Can access the relevant patient-facing explanation, confirm understanding, request assistance, and provide optional information about practical barriers according to their permissions.

They cannot view unrelated patient records or modify clinician-approved instructions.

### Clinicians and Authorised Clinical Staff

Can create or approve clinical instructions, clarify ambiguity, and make medical decisions.

Clinical judgement remains with authorised healthcare professionals.

### Registration and Follow-up Staff

Can reconcile attendance and contact information, assign administrative tasks, record outreach attempts, and verify follow-up status using approved sources.

They cannot treat an AI-generated score as proof of non-attendance or clinical urgency.

### Hospital Administrators

Can manage user permissions, workflow templates, retention policies, queue definitions, and operational reporting.

Access to identifiable patient information must be limited to authorised roles and legitimate purposes.

## Proposed Technical Architecture

The proposed architecture consists of the following logical components.

1. Data input layer for appointment records, clinician-approved instructions, patient preferences, and follow-up status.
2. Validation and reconciliation layer for detecting missing fields, conflicting information, duplicate records, and uncertain attendance status.
3. Rules and template layer for applying approved workflow conditions and generating administrative tasks.
4. AI assistance layer for plain-language rewriting, information summarisation, and selected administrative support.
5. Patient interaction layer for understanding checks, consent-aware communication, and barrier reporting.
6. Visit planning layer for appointment guidance and qualified travel and waiting-time estimates.
7. Staff dashboard layer for unresolved case management and administrative coordination.
8. Outcome and audit layer for status verification, timestamps, correction history, and traceable actions.

The system is intended to integrate with existing hospital workflows where feasible rather than requiring immediate replacement of existing registration or record systems.

For the initial prototype, synthetic or properly de-identified records should be used when direct hospital integration and required approvals are unavailable.

## Role of Artificial Intelligence

AI is intended to support healthcare coordination rather than replace clinical judgement.

Potential AI-assisted capabilities include:

1. Rewriting approved follow-up instructions into plain language.
2. Identifying missing or contradictory information.
3. Summarising patient-reported barriers.
4. Suggesting administrative follow-up tasks.
5. Supporting waiting-time estimation when validated data are available.
6. Evaluating follow-up patterns using suitable data and a human-reviewed process.

A transparent rules-based baseline should be established before introducing predictive prioritisation. Any predictive model requires a clear outcome definition, appropriate data quality, independent evaluation, and a defined human response workflow.

## Safety and Privacy Principles

The system follows a human-supervised approach to healthcare coordination.

1. It does not diagnose medical conditions.
2. It does not prescribe medicines or modify treatment.
3. It does not make autonomous emergency-triage decisions.
4. It does not override clinician-approved instructions.
5. It does not assume that an unreachable patient has missed an appointment.
6. It does not disclose sensitive information to unverified recipients.
7. It flags missing, contradictory, outdated, and unverified information.
8. It maintains role-based access and minimum necessary data collection.
9. It records important actions, corrections, timestamps, and responsible roles.
10. It supports staff-assisted and non-digital pathways for patients who cannot use a digital application.

Any real-patient deployment requires appropriate institutional approval, privacy and security review, clinical oversight, and an approved consent process.

## Implementation Roadmap

### Phase 1. Case Validation

Map the local hospital workflow, identify relevant data fields, define follow-up statuses, and determine authoritative sources for appointments and attendance.

Validate the requirements with patients and staff where permitted.

### Phase 2. Functional Prototype

Build a prototype using synthetic records to demonstrate follow-up plan capture, patient-friendly explanations, understanding status, barrier reporting, staff coordination, and audit history.

Simulated waiting-time information must be clearly identified as simulated.

### Phase 3. Offline Validation

Test the system using missing and conflicting records, shared-phone scenarios, unreachable contacts, language fidelity checks, unreliable queue data, and contradictory attendance information.

Evaluate usability and compare any proposed predictive component with a simple baseline.

### Phase 4. Supervised Pilot Proposal

Prepare a proposal for controlled evaluation after obtaining the necessary institutional approvals, privacy and security reviews, clinical oversight, and outcome monitoring arrangements.

## Evaluation Metrics

The proposed system should be evaluated using clearly defined metrics.

### Patient Understanding Rate

The proportion of assessed patients who correctly identify their next required care step.

### Follow-up Completion Rate

The proportion of due follow-ups verified as completed within the approved window after record reconciliation.

### Barrier Detection Usefulness

The agreement between recorded barriers and patient or staff confirmed barriers, including missed barriers and false positives.

### False Alert Rate

The proportion of reviewed flags that are closed as unnecessary after staff review.

### Record Reconciliation Rate

The proportion of suspected attendance or status mismatches that are corrected or resolved.

### Waiting-time Prediction Error

The difference between predicted and actual waiting times on suitable evaluation data, including mean absolute error and variation across clinics and time periods.

### Staff Response Time

The time between identification of an unresolved case and the first meaningful staff action.

### Accessibility and Completion by Channel

Task completion and understanding across digital, telephone or voice-based, and staff-assisted pathways.

### Privacy and Safety Events

The number and nature of unauthorised disclosures, incorrect instruction changes, and actions outside the approved scope.

Evaluation targets should be agreed with the relevant hospital team rather than invented from simulated case statistics.

## Prototype Acceptance Tests

The prototype should demonstrate the following behaviours.

1. Missing or conflicting follow-up information triggers clarification instead of generating assumed instructions.
2. AI-generated explanations preserve the meaning and critical details of the approved source.
3. Patients who do not understand the instructions receive an assistance pathway.
4. Shared-phone scenarios do not disclose sensitive information without appropriate authorisation.
5. Contradictory attendance records remain unverified until reconciliation.
6. Unreachable contacts are recorded accurately and do not trigger endless contact attempts.
7. Scheduled visit guidance respects appointment time and the required check-in buffer.
8. Unreliable queue information does not produce unsupported waiting-time estimates.
9. Predictive models are evaluated against a simple baseline before any patient-facing use.
10. Requests for diagnosis, prescribing, treatment modification, or autonomous emergency triage remain outside the system's authority.

## Expected Benefits

The proposed system aims to make follow-up coordination more reliable and accessible.

It can help patients understand their next steps, help staff identify unresolved cases, reduce avoidable errors caused by incomplete records, improve visibility into contact and access barriers, and create a traceable record of follow-up outcomes.

These benefits are intended outcomes that require prototype evaluation and appropriate real-world validation. They are not claims of measured clinical effectiveness.

## Current Scope and Limitations

Aarambh Follow-up Navigator is presented as a proposed solution and implementation plan.

The actual implementation status of individual modules depends on the development stage of the project.

Real-time appointment integration, live queue estimation, travel-time services, multilingual clinical validation, and predictive modelling require suitable data sources, testing, and approvals.

The case-pack statistics describe a simulated hospital scenario and must not be interpreted as audited statistics from a real hospital.

## References

1. B. Das, D. Neupane, S. S. Gill, and G. B. Singh, Factors affecting non-adherence to medical appointments among patients with hypertension at public health facilities in Punjab, India. Journal of Clinical Hypertension, 2021. DOI: 10.1111/jch.14142.

2. L. H. A. Salazar, W. D. Parreira, A. M. da Rocha Fernandes, and V. R. Q. Leithardt, No-Show in Medical Appointments with Machine Learning Techniques: A Systematic Literature Review. Information, Volume 13, Issue 11, Article 507, 2022. DOI: 10.3390/info13110507.

3. AI Synergy Hackathon 2026. Participant Case File: The Follow-Up Blind Spot and Round 1 Case Investigation Challenge.
## Project Vision

Aarambh Follow-up Navigator aims to bridge the gap between issuing a healthcare follow-up plan and helping patients complete the next step.

By combining accessible communication, structured workflow management, responsible AI assistance, reliable record reconciliation, and human-supervised coordination, the project proposes a practical approach to improving continuity of care in resource-constrained healthcare environments.
