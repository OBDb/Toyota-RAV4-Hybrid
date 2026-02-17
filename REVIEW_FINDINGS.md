# Toyota RAV4 Hybrid Signalset Review Findings

**Date:** 2026-02-17  
**Branch:** `onboard-from-rav4`  
**Repo:** `~/.cache/obdb-workspace/Toyota-RAV4-Hybrid`  
**Reviewer:** Clutch (automated review using obdb-reviewer skill)

---

## Summary

Full coverage review of the Toyota RAV4 Hybrid signalset after the prior cleanup pass (commits 71c1767 and 7ed34c2 which removed 4 commands with wide unsupported year ranges).

**Final signalset state:** 80 commands, 56% coverage

**Actions taken in this review:**
- **No commands removed** — all remaining zero-coverage commands meet the "keep" criteria
- **Fixed 4 duplicate signal IDs** — added `_V2` suffix to second occurrences

---

## Coverage Report Summary

**`obdb coverage "Toyota/RAV4 Hybrid" --verbose`**

- Total commands: 80
- Model years with test data: 2016, 2017, 2019, 2020, 2021, 2022, 2023, 2024, 2025
- Commands with test responses: **45 (56%)**
- Commands with zero test responses: **35 (44%)**

---

## Zero-Coverage Commands Analysis

### Commands Unsupported Only in 2025 → KEPT (26 commands)

Per skill guidance: commands unsupported in only 1-2 model years should be kept, as they may work on other years.

| Command | Key Signals | Decision |
|---------|-------------|----------|
| 7B0.21A6 | RAV4HYBRID_INSPECTION_MODE | KEEP — only 2025 unsupported |
| 7B0.7B8.2105 | RAV4HYBRID_DECEL, DECEL2 | KEEP — only 2025 unsupported |
| 7B0.7B8.2106 | RAV4HYBRID_YAW_RATE, YAW_RATE2 | KEEP — only 2025 unsupported |
| 7B0.7B8.211D | RAV4HYBRID_RESERVOIR_WARNING, MAIN_IDLE | KEEP — only 2025 unsupported |
| 7B0.7B8.211F | RAV4HYBRID_STOP_LIGHT, PARKING_BRAKE | KEEP — only 2025 unsupported |
| 7B0.7B8.213C | RAV4HYBRID_STOP_LIGHT_RELAY | KEEP — only 2025 unsupported |
| 7B0.7B8.213D | RAV4HYBRID_ABS_WARNING, BRAKE_WARNING, SLIP_INDICATOR (+2) | KEEP — only 2025 unsupported |
| 7B0.7B8.2142 | RAV4HYBRID_FR/FL/RR_ACC (+1) | KEEP — only 2025 unsupported |
| 7B0.7B8.2146 | RAV4HYBRID_ZP_DEC, ZP_DEC2, ZP_YAW_RATE | KEEP — only 2025 unsupported |
| 7B0.7B8.215A | RAV4HYBRID_TRC_CTRL, TRC_ENGINE_CTRL, TRC_BRAKE_CTRL (+4) | KEEP — only 2025 unsupported |
| 7B0.7B8.215F | RAV4HYBRID_FR/FL/RR_WHEEL_ABS_CTRL_STATUS (+5) | KEEP — only 2025 unsupported |
| 7B0.7B8.21BE | RAV4HYBRID_FR/FL/RR_WHEEL_SPEED_OPEN (+8) | KEEP — only 2025 unsupported |
| 7C0.21A7 | RAV4HYBRID_SEAT_BELT_BEEP | KEEP — only 2025 unsupported |
| 7C0.7C8.2112 | RAV4HYBRID_TAIL_CANCEL, P_SEATBELT_BUCKLE, CHECK_ENGINE | KEEP — only 2025 unsupported |
| 7C0.7C8.2123 | RAV4HYBRID_COOLANT_T | KEEP — only 2025 unsupported |
| 7C4.7CC.2126 | RAV4HYBRID_ECT | KEEP — only 2025 unsupported |
| 7C4.7CC.2129 | RAV4HYBRID_T_DRIVER | KEEP — only 2025 unsupported |
| 7E0.2124 | RAV4HYBRID_COMMUNICATION_WITH_HV (+3) | KEEP — only 2025 unsupported |
| 7E0.2125 | RAV4HYBRID_POWER_STEERING_SIGNAL (+15) | KEEP — only 2025 unsupported |
| 7E0.7E8.2101 | RAV4HYBRID_CALCULATED_LOAD_7E0, MAF, MAP (+17) | KEEP — only 2025 unsupported |
| 7E0.7E8.2103 | RAV4HYBRID_SHORT_FT_B1S1, LONG_FT_B1S1, IGN_ADVANCE (+1) | KEEP — only 2025 unsupported |
| 7E0.7E8.2104 | RAV4HYBRID_TARGET_AIR_FUEL_RATIO, AF_LAMBDA_B1S1 (+2) | KEEP — only 2025 unsupported |
| 7E0.7E8.2105 | RAV4HYBRID_CATALYST_T_B1S1, CATALYST_T_B1S2 | KEEP — only 2025 unsupported |
| 7E0.7E8.2106 | RAV4HYBRID_MIL, NUMBER_OF_EMISSION_DTC (+20) | KEEP — only 2025 unsupported |
| 7E0.7E8.2145 | RAV4HYBRID_MISFIRE_RPM, MISFIRE_LOAD, CYL1_MISFIRE_CNT (+6) | KEEP — only 2025 unsupported |
| 7E0.7E8.21DA | RAV4HYBRID_GEAR_V2 | KEEP — only 2025 unsupported |

**Note:** The 7E0 commands confirmed working on 2017 (7E0.7E8.2121, 7E0.7E8.2151), so the 7E0 ECU is accessible on older years. The "Unsupported: 2025" status suggests a 2025 model year ECU change, not a vehicle-wide compatibility issue.

### Commands with No Coverage Data → KEPT (9 commands)

Per skill guidance: commands with no test data at all (not in command_support.yaml) are untested, not confirmed unsupported. They may work on this vehicle.

| Command | Key Signals | Decision |
|---------|-------------|----------|
| 7C4.2143 | RAV4HYBRID_AIR_OUTLET_SERVO_PULSE_D (+1) | KEEP — untested (no coverage data) |
| 7C4.7CC.2121 | RAV4HYBRID_CABIN_T | KEEP — untested (no coverage data) |
| 7C4.7CC.2122 | RAV4HYBRID_AAT | KEEP — untested (no coverage data) |
| 7C4.7CC.2124 | RAV4HYBRID_SOLAR_DRIVER | KEEP — untested (no coverage data) |
| 7C4.7CC.213C | RAV4HYBRID_BLOWER_MOTOR_SPEED_LEVEL | KEEP — untested (no coverage data) |
| 7C4.7CC.213D | RAV4HYBRID_ADJUSTED_AMBIENT_T | KEEP — untested (no coverage data) |
| 7C4.7CC.214B | RAV4HYBRID_EVAP_FIN_THERMISTOR | KEEP — untested (no coverage data) |
| 7C4.7CC.214C | RAV4HYBRID_EVAP_TARG_T | KEEP — untested (no coverage data) |
| 7C4.7CC.2153 | RAV4HYBRID_REGULATOR_P | KEEP — untested (no coverage data) |

**Note:** All 9 are on the HVAC ECU (7C4/7CC). These climate control signals are plausible — the RAV4 Hybrid has a heat pump HVAC system and these signals could be real but just untested on this model.

---

## Duplicate Command Check

Checked for general (no RAX) vs specific (with RAX) command duplicates — **none found**. The previous cleanup already removed the general `7B0.2103` in favor of the specific `7B0.7B8.2103`.

The 5 commands without RAX (`7B0.21A6`, `7C0.21A7`, `7C4.2143`, `7E0.2124`, `7E0.2125`) have no corresponding specific-RAX versions with the same cmd bytes.

---

## Duplicate Signal ID Fixes (Committed)

**Lint detected 4 duplicate signal IDs** across commands — a linting requirement violation. Fixed by adding `_V2` suffix to the second occurrence of each (by file order):

| Duplicate ID | First Occurrence (kept) | Second Occurrence (renamed) |
|---|---|---|
| RAV4HYBRID_YAW_RATE | 7B0.7B8.2106 (zero coverage) | 7B0.7B8.2147 → `_V2` (supported: 2017, 2019) |
| RAV4HYBRID_PARKING_BRAKE | 7B0.7B8.211F (zero coverage) | 7D0.7DA.2162 → `_V2` (supported: 2021-2022) |
| RAV4HYBRID_AAT | 7C4.7CC.2122 (no coverage) | 7D2.7DA.221F46 → `_V2` (supported: 2019, 2021-2025) |
| RAV4HYBRID_BATTERY_VOLTAGE | 7C0.7C8.221021 (supported: 2019, 2021-2025) | 7E0.7E8.2101 → `_V2` (zero coverage) |

**Commit:** `429bcae` — "fix: rename duplicate signal IDs with _V2 suffix"

---

## Remaining Lint Issues (Informational)

After fixes, `obdb lint` reports 28 issues (down from 32). All remaining are informational/style:

- **2 warnings:** Acronym-at-start-of-signal-name (ABS warning, ECB warning) — cosmetic
- **2 info:** `command-rax-duplication` for cmd=2124 (`7C4.7CC.2124` vs `7E0.2124`) — **false positive**: these use different ECU headers (7C4 vs 7E0) so there's no actual ambiguity; the linter doesn't account for different headers in this check
- **24 info:** Bracketed content in signal names, signal path suggestions, sentence case — cosmetic style issues, not correctness errors

These remaining issues are pre-existing style lint items from the source signalset and do not affect correctness or vehicle data quality.

---

## Prior Cleanup History

| Commit | Action |
|--------|--------|
| `2302d21` | Onboard Toyota RAV4 Hybrid from Toyota RAV4 (80 commands added) |
| `71c1767` | Removed RAV4HYBRID_FLI (zero support) + general 7B0.2103 (kept specific with RAX) |
| `7ed34c2` | Removed 3 commands with wide unsupported year ranges: 7E0.7E8.2128 (ODO, unsupported 2021-2023/2025), 7E0.7E8.2182 (ATF temps, unsupported 2017/2019-2025), 7E0.7E8.2185 (GEAR, unsupported 2017/2021-2023/2025) |
| `429bcae` | Fixed 4 duplicate signal IDs with _V2 suffix |

---

## Final State

- **80 commands** in signalset
- **45 commands** with confirmed test data (56% coverage)
- **35 commands** zero-coverage (kept per review criteria — 26 unsupported in 2025 only, 9 untested)
- **0 duplicate signal IDs**
- **JSON valid** ✓
- **Formatted** ✓
