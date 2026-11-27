# EcoRoute – Technical Process Report (Stage 5)

**Team E** – Collaborative Software Tools  
Project Lead: Michelle Obando Sibaja · Technical Expert 1 (AI & Routing Data): José Angel Nuño Vazquez · Technical Expert 2 (Emissions & Fleet Impact): Michelle Obando Sibaja

Source: Stage 4 System Prompt v1.1 and Technical Report Draft v2.

---

## 1. Executive Summary
_Pending – Issue #1 (Michelle)_

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
_Pending – Issue #2 (Michelle)_

## 5. Open Issues (INSUFFICIENT_DATA)
_To be consolidated after all sections are merged._
