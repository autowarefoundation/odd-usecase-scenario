# Scenario Naming Pattern

The scenarios for PoV are named following the pattern below:
UC-[SCENARIO CATEGORY]-[SCENARIO SUB-CATEGORY]-[INCREMENTAL ID]

Where:

[SCENARIO CATEGORY] indicates the purpose of the test scenario. For now, one of the following values shall be used:
- PLN: Planning critical scenario
- CTL: Control critical scenario
- PER: Perception critical scenario

[SCENARIO SUB-CATEGORY] adopts different meanings depending on the main category. 

| SCENARIO CATEGORY             | SCENARIO SUB-CATEGORY |
| ----------------------------- | --------------------- |
| Planning critical scenario    | - 001: Object following<br>- 002: Free driving<br>- 003: Lane keeping<br>- 004: Emergency braking |
| Control critical scenario     | - 001: Road shape<br>- 002: Scenery elements<br>- 003: Weather conditions |
| Perception critical scenario  | - 001: Blindspot<br>- 002: Poor detection conditions |

[INCREMENTAL ID] is a 4-digit number starting at 0001 and continuously incremented for each scenario with the same ego motion category.