# Scenarios

This document describes the mapping between use cases defined in this repository and their corresponding scenarios managed in the [evaluator](https://evaluation.tier4.jp/).

## Use Case to Scenario Mapping

The following table provides the traceability between the use cases and their implementation as scenarios in the evaluator.

### [Urban-Dense](https://evaluation.tier4.jp/evaluation/vehicle_catalogs/aaf96902-ab17-4957-93a0-e3b6aa7b9efd?project_id=awf) Catalog

#### Non Traffic Rules (NTR) Use Cases

| Use Case ID | Use Case Name | Scenario Link |
| ----------- | ------------- | ------------- |
| UC-NTR-001-0001 | Wait for an overtake while stationary | [case1](https://evaluation.tier4.jp/evaluation/scenarios/0c51ed83-bffa-419e-9725-c649fe4780f3?project_id=awf) / [case2](https://evaluation.tier4.jp/evaluation/scenarios/70003386-d425-48ed-8746-7a2368d53b67?project_id=awf) |
| UC-NTR-001-0002 | Depart while being overtaken | [case1](https://evaluation.tier4.jp/evaluation/scenarios/767d8164-3cf8-4682-9aa3-c19eb796d166?project_id=awf) / [case2](https://evaluation.tier4.jp/evaluation/scenarios/180c2e27-e623-4080-8c1e-f9853d475235?project_id=awf) |
| UC-NTR-001-0003 | Wait for an overtake from same direction lane while stationary | [case1](https://evaluation.tier4.jp/evaluation/scenarios/b1bbb34c-a939-46b3-818b-cb8d88dd87d7?project_id=awf) / [case2](https://evaluation.tier4.jp/evaluation/scenarios/37a18e54-a640-400f-8b53-aa4f6d2b6772?project_id=awf) |
| UC-NTR-001-0004 | Depart while being overtaken from same direction lane | [case1](https://evaluation.tier4.jp/evaluation/scenarios/85d6da59-ffe8-463e-ae1b-3edef764f79b?project_id=awf) / [case2](https://evaluation.tier4.jp/evaluation/scenarios/3b735080-1058-4124-b697-6d7603d221e2?project_id=awf) |
| UC-NTR-001-0005 | Wait for an overtake from opposite direction lane while stationary | [case](https://evaluation.tier4.jp/evaluation/scenarios/2edfabd2-d2ef-4ae1-8d37-58d7dceb6576?project_id=awf) |
| UC-NTR-001-0006 | Depart while being overtaken from opposite direction lane | [case](https://evaluation.tier4.jp/evaluation/scenarios/15396f83-daa6-4eb9-9c7c-618050a924a3?project_id=awf) |
| UC-NTR-001-0007 | Handle cut-in from a faster vehicle | [case](https://evaluation.tier4.jp/evaluation/scenarios/83ef39b2-c573-485f-bb17-bd595f626d24?project_id=awf) |
| UC-NTR-001-0008 | Handle cut-in from a faster vehicle that then slows down | [case](<https://evaluation.tier4.jp/evaluation/scenarios/cc6b1c53-61bd-444a-bced-10231d0cdbe7?project_id=awf>) |
| UC-NTR-001-0009 | Handle cut-in from vehicle starting from roadside| [case](https://evaluation.tier4.jp/evaluation/scenarios/24d11ead-d78e-4748-8dc6-20d5486e8314?project_id=awf) |
| UC-NTR-002-0001 | Overtake the stopping or low velocity vehicle | [case1](https://evaluation.tier4.jp/evaluation/scenarios/d3520449-a045-4787-86e0-bb243014b117?project_id=awf) / [case2](https://evaluation.tier4.jp/evaluation/scenarios/577641a4-c755-4db1-aa6c-1dcadc0ada60?project_id=awf) |
| UC-NTR-002-0002 | Overtake the vehicles in side of the road | [case1](https://evaluation.tier4.jp/evaluation/scenarios/c4ee37cd-e1c9-487f-ba15-3d07db8c87c4?project_id=awf) / [case2](https://evaluation.tier4.jp/evaluation/scenarios/8992be0b-22a3-4a61-ade9-fdf3e07de9b2?project_id=awf) |
| UC-NTR-002-0003 | Overtake the moving vehicles in side of the road | [case1](https://evaluation.tier4.jp/evaluation/scenarios/f1c4b217-e246-4e95-90c1-037e14583365?project_id=awf) / [case2](https://evaluation.tier4.jp/evaluation/scenarios/4236876f-7f1a-440b-8edd-eb83bee97f47?project_id=awf) |
| UC-NTR-002-0004 | Wait for overtaking vehicle to clear off the ego lane | [case](https://evaluation.tier4.jp/evaluation/scenarios/6a86e217-8ada-4f54-9ded-1d77648b4257?project_id=awf) |
| UC-NTR-003-0001 | Handle cut-in from oncoming vehicle at intersection | [case](https://evaluation.tier4.jp/evaluation/scenarios/037f2b6b-0586-4d1c-9d4e-c43aee394a99?project_id=awf) |
| UC-NTR-003-0002 | Handle oncoming vehicle while turning right at intersection | [case](https://evaluation.tier4.jp/evaluation/scenarios/1ac5d90e-aafa-420e-8aff-692a9cc3e039?project_id=awf) |
| UC-NTR-003-0003 | Decide to stop or pass for slow oncoming vehicle at intersection | [case](https://evaluation.tier4.jp/evaluation/scenarios/80bf640c-702d-4c36-bc7d-f12a41f892bf?project_id=awf) |
