# EcoRoute – Technical Process Report (Stage 5)

**Team E** – Collaborative Software Tools  
Project Lead: Michelle Obando Sibaja · Technical Expert 1 (AI & Routing Data): José Angel Nuño Vazquez · Technical Expert 2 (Emissions & Fleet Impact): Michelle Obando Sibaja

Source: Stage 4 System Prompt v1.1 and Technical Report Draft v2.

---

## 1. Executive Summary
EcoRoute is an AI-based route-planning system for last-mile e-commerce deliveries. It balances distance, delivery time, vehicle capacity and CO2 emissions across a mixed fleet of bicycles, scooters, motorcycles and vans. This report consolidates the Stage 3 workflow and the Stage 4 audit (System Prompt v1.1 and Technical Report Draft v2) into a single version-controlled document.

Key results: the end-to-end workflow covers order validation, fleet availability, AI route optimisation, cost and emissions estimation, delivery execution and redelivery handling. The AI documentation prompt passed 3/3 adversarial red-teaming tests (roleplay override, indirect prompt injection and missing data) and never invented figures: every undocumented value is reported as INSUFFICIENT_DATA.

Next step: the Technical Experts must supply the missing operational data listed in Section 5 (emission factors, vehicle capacities and cost model) before EcoRoute can move to a pilot.

## 2. Route Optimization Methodology
_Pending – Issue #3 (Angel)_

## 3. Process Workflow & Decision Points
_Pending – Issue #4 (Angel)_

## 4. Emissions & Fleet Impact
EcoRoute treats CO2 emissions as an optimisation criterion alongside distance, time and vehicle capacity. The workflow step Estimate Costs and Emissions runs before routes are confirmed, so vehicle allocation can favour lower-emission vehicles whenever capacity and time constraints allow.

| Vehicle | Emission profile | Typical use | Emission factor (g CO2/km) | Load capacity |
|---|---|---|---|---|
| Bicycle | Zero tailpipe emissions | Short, dense urban routes | 0 (tailpipe) | INSUFFICIENT_DATA |
| Scooter | Not specified (electric or combustion) | Light parcels, short distances | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Motorcycle | Combustion engine | Medium distances, small loads | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Van | Not specified (electric or combustion) | Bulky loads, longer routes | INSUFFICIENT_DATA | INSUFFICIENT_DATA |

Impact assessment: the CO2 reduction achieved by AI route optimisation cannot be quantified yet. INSUFFICIENT_DATA: baseline emissions per route and emission factor per vehicle type. In line with the Stage 4 anti-hallucination protocol, no estimated or industry-average values are used.

Data required to close this section: emission factor per vehicle type (g CO2/km), load capacity per vehicle type (kg), and kilometres travelled per route before and after optimisation.

## 5. Open Issues (INSUFFICIENT_DATA)
_To be consolidated after all sections are merged._
