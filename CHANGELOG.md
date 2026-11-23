# Changelog

All notable changes to this project are documented in this file.

Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)
Versioning: [Semantic Versioning](https://semver.org/)

> No version has been tagged yet. The entries below summarize the git history up to the first release.

---

## [Unreleased]

### Added

- End-to-end Medallion Architecture pipeline (Bronze, Silver, Gold) built with PySpark and Delta Lake for a fictional marketplace: raw ingestion with source metadata, validation and deduplication with quarantine tables, and Gold metrics for daily revenue, inventory risk and price anomalies.
- Synthetic data generator that produces intentionally imperfect orders, inventory and price events, plus committed sample data.
- Local pipeline runner (`run_pipeline.py`) that executes all three layers end to end and exports Gold parquet.
- Streamlit operations dashboard that reads Gold through Databricks SQL, or from local sample data in offline mode.
- Databricks notebooks for ingestion, validation, business metrics and the technical evaluation walkthrough.
- Delta Lake operations module covering `MERGE` upsert, `OPTIMIZE`/`ZORDER`, `VACUUM`, table history and time travel, with tests for idempotent replay (#2).
- GitHub Actions CI with a Delta JAR cache and a CI badge, a `GATE_RUNNER` variable for the runner selection, and a Python test and lint gate (#3).
- Documentation: customer scenario, architecture, technical evaluation and workshop guide, plus a README rewritten for readability and a stated release type (`reference`) (#17).
- `AGENTS.md` with contributor guidance for coding agents.

### Security

- Added a gitleaks secrets scan to CI (#8).

### Fixed

- Test failures related to the Delta JAR, an `AMBIGUOUS_REFERENCE` error and timestamp handling.
- CI build backend configuration, and separation of app and dev dependencies.
- README badge and clone URL organization, and a stale test count (#6).
- Code formatting so that `black --check` passes (#11).
