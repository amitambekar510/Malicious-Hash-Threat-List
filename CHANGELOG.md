# Changelog — Malicious Hash Threat Intelligence Feed

## [2026-01-15] — Automated Pipeline Launch

### Added
- Automated 12-hour collection from MalwareBazaar
- SHA256 prioritized (2 hashes/cycle)
- Validation: VirusTotal (≥3), MalwareBazaar
- Partition management: MD5 (3K), SHA1 (1K), SHA256 (60K)

### Statistics
| Hash Type | Before | Added | After |
|-----------|--------|-------|-------|
| SHA256 | 78,000 | 2,644 | 80,644 |
| MD5 | 3,800 | 334 | 4,134 |
| SHA1 | 580 | 47 | 627 |

---

## [2025-10-01] — Hash Feed Expansion

### Added
- MalwareBazaar recent samples API
- MalwareBazaar by file type (PE executables)
- SHA256 partition management (3 files)

### Statistics
| Hash Type | Before | Added | After |
|-----------|--------|-------|-------|
| SHA256 | 15,000 | 63,000 | 78,000 |
| MD5 | 1,200 | 2,600 | 3,800 |
| SHA1 | 200 | 380 | 580 |

---

## [2025-04-01] — Initial Release

### Added
- Basic hash collection structure
- MD5, SHA1, SHA256 format standards