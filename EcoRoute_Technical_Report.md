# EcoRoute – Technical Process Report (Stage 5)

**Team E** – Collaborative Software Tools  
Project Lead: Michelle Obando Sibaja · Technical Expert 1 (AI & Routing Data): José Angel Nuño Vazquez · Technical Expert 2 (Emissions & Fleet Impact): Michelle Obando Sibaja

Source: Stage 4 System Prompt v1.1 and Technical Report Draft v2.

---

## 1. Executive Summary
EcoRoute is an AI-based route-planning system for last-mile e-commerce deliveries. It balances distance, delivery time, vehicle capacity and CO2 emissions across a mixed fleet of bicycles, scooters, motorcycles and vans. This report consolidates the Stage 3 workflow and the Stage 4 audit (System Prompt v1.1 and Technical Report Draft v2) into a single version-controlled document.

Key results: the end-to-end workflow covers order validation, fleet availability, AI route optimisation, cost and emissions estimation, delivery execution and redelivery handling. The AI documentation prompt passed 3/3 adversarial red-teaming tests (roleplay override, indirect prompt injection and missing data) and did not generate unsupported figures during the tested scenarios; undocumented values are reported as INSUFFICIENT_DATA. These results apply only to the tested scenarios and do not guarantee complete security.

Next step: the Technical Experts must supply the missing operational data listed in Section 5 (emission factors, vehicle capacities and cost model) before EcoRoute can move to a pilot.

## 2. Route Optimization Methodology
The EcoRoute workflow proposes an AI-based route optimisation methodology for last-mile e-commerce deliveries. Its intended objectives are to consider travel distance, delivery time, vehicle capacity, operational costs and CO2 emissions.

### Route Optimisation Process

1. Receive and validate order data before starting the routing process.
2. Check fleet availability and reschedule orders if no vehicles are available.
3. Collect traffic data to support route planning.
4. Assign available vehicles to delivery orders.
5. Optimise routes using AI.
6. Evaluate route feasibility. If routes are not feasible, adjust vehicle allocation and repeat the optimisation process.
7. Estimate operational costs and CO2 emissions before confirming the routes.

### Data Requirements and Limitations

The following technical parameters remain undocumented:

- AI optimisation algorithm: INSUFFICIENT_DATA.
- Mathematical objective function and optimisation weights: INSUFFICIENT_DATA.
- Traffic data source: INSUFFICIENT_DATA.
- Vehicle capacity per vehicle type: INSUFFICIENT_DATA.
- Delivery time windows: INSUFFICIENT_DATA.
- Operational cost parameters: INSUFFICIENT_DATA.
- Emission factors per vehicle type: INSUFFICIENT_DATA.

In accordance with the Stage 4 anti-hallucination protocol, missing parameters must not be estimated or presented as verified project data. External values require documented sources and explicit project-team approval.

The workflow describes the intended optimisation process. Its actual performance and potential improvements cannot be quantified until the required operational data and optimisation parameters are available.
## 3. Process Workflow & Decision Points
The EcoRoute process follows the Stage 3 workflow updated during Stage 4 (v1.1 input). It covers the complete delivery process, from receiving orders to recording successful delivery results.

### Main Process Flow

Start → Receive Orders → Check Fleet Availability → Collect Traffic Data → Assign Vehicles → Optimize Routes Using AI → Estimate Costs and Emissions → Confirm Routes → Execute Deliveries → Record Results → End.

The main process flow is subject to the following decision points and conditional branches.

### Decision Points

| Decision point | Yes | No |
|---|---|---|
| Valid Data? | Check Fleet Availability | Correct Data → Receive Orders |
| Vehicles Available? | Collect Traffic Data | Reschedule Orders → Check Fleet Availability |
| Feasible Routes? | Estimate Costs and Emissions | Adjust Vehicle Allocation → Assign Vehicles |
| Delivery Successful? | Record Results | Schedule Redelivery |

### Error and Exception Handling

- Invalid order data is corrected and revalidated before proceeding.
- Unavailable vehicles trigger order rescheduling and a new fleet availability check.
- Infeasible routes trigger vehicle reallocation and a new optimisation cycle.
- Unsuccessful deliveries trigger the Schedule Redelivery step.

### Process Limitations

- Maximum number of data correction attempts: INSUFFICIENT_DATA.
- Maximum number of order rescheduling attempts: INSUFFICIENT_DATA.
- Maximum number of route optimisation retries: INSUFFICIENT_DATA.
- Maximum number of delivery retries: INSUFFICIENT_DATA.
- Escalation rules when retry limits are reached: INSUFFICIENT_DATA.

All undocumented parameters must remain flagged until documented sources and explicit project-team approval are provided, in accordance with the Stage 4 anti-hallucination protocol.

## 4. Emissions & Fleet Impact
EcoRoute is designed to treat CO2 emissions as an optimisation criterion alongside distance, time and vehicle capacity. The workflow step Estimate Costs and Emissions runs before routes are confirmed. Favouring lower-emission vehicles whenever capacity and time constraints allow is an intended objective, not yet a verified system capability: the optimisation algorithm and objective function remain INSUFFICIENT_DATA.

| Vehicle | Emission profile | Typical use | Emission factor (g CO2/km) | Load capacity |
|---|---|---|---|---|
| Bicycle | Human-powered (no engine) | To be verified | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Scooter | Not specified (electric or combustion) | To be verified | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Motorcycle | Not specified | To be verified | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Van | Not specified (electric or combustion) | To be verified | INSUFFICIENT_DATA | INSUFFICIENT_DATA |

Impact assessment: the CO2 reduction achieved by AI route optimisation cannot be quantified yet. INSUFFICIENT_DATA: baseline emissions per route and emission factor per vehicle type. In line with the Stage 4 anti-hallucination protocol, no estimated or industry-average values are used.

Data required to close this section: emission factor per vehicle type (g CO2/km), load capacity per vehicle type (kg), and kilometres travelled per route before and after optimisation.

## 5. Open Issues (INSUFFICIENT_DATA)
Consolidated list of undocumented parameters from Sections 2–4. None of these values may be estimated; each must be supplied with a documented source and explicit project-team approval before EcoRoute moves to a pilot.

| Open issue | Section | Owner |
|---|---|---|
| AI optimisation algorithm | 2 | Technical Expert 1 |
| Objective function and optimisation weights | 2 | Technical Expert 1 |
| Traffic data source | 2 | Technical Expert 1 |
| Delivery time windows | 2 | Technical Expert 1 |
| Operational cost parameters / cost model | 2 | Technical Expert 1 |
| Retry limits (data correction, rescheduling, optimisation, delivery) and escalation rules | 3 | Technical Expert 1 |
| Emission factor per vehicle type (g CO2/km) | 4 | Technical Expert 2 |
| Load capacity per vehicle type (kg) | 2, 4 | Technical Expert 2 |
| Typical use per vehicle type | 4 | Technical Expert 2 |
| Baseline emissions per route (before/after optimisation) | 4 | Technical Expert 2 |
