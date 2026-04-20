# Changelog

All notable changes to this project will be documented in this file.

## [1.2.0] - 2026-04-20

### Added

- Added `响应语言与信息缺口规则` to `SKILL.md`, clarifying language following, missing-data handling, and conditional judgment discipline.
- Added `模型使用纪律` to `SKILL.md` so strategic and financial models stay subordinate to the main analysis flow instead of turning into framework dumping.
- Added `路由与参考材料使用` to `SKILL.md` so hosts know when to use `src/router.js` and when to read `references/router-design.md`, `references/examples.md`, and `references/metric-playbook.md`.

### Changed

- Bumped the project version to `1.2.0` across `README.md` and `package.json`.
- Strengthened `SKILL.md` so the skill now covers response language, uncertainty handling, model selection discipline, and progressive disclosure guidance more explicitly.

## [1.1.0] - 2026-04-20

### Added

- Added `src/router.js` for internal skill intent routing.
- Added `src/index.js` as the public export entry for router utilities.
- Added intent routing support for `growth_analysis`, `funnel_analysis`, `retention_analysis`, `revenue_analysis`, `efficiency_analysis`, and `business_diagnosis`.
- Added [references/router-design.md](/d:/home/business-data-analyst-skill/references/router-design.md) to document the routing design and expected contract.
- Added strategic, competitive, marketing, operational, and financial analysis model guidance to [SKILL.md](/d:/home/business-data-analyst-skill/SKILL.md) and [references/metric-playbook.md](/d:/home/business-data-analyst-skill/references/metric-playbook.md).

### Changed

- Updated [README.md](/d:/home/business-data-analyst-skill/README.md) to document the new runtime routing layer and point change history to `CHANGELOG.md`.
