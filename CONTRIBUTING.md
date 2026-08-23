# Contributing to Malicious Hash Threat Intelligence Feed

## Ways to Contribute

1. **Report False Positives** — Legitimate software hashes
2. **Submit New Malicious Hashes** — From sandbox, IR, malware analysis
3. **Request Tool Integrations** — EDR, AV, sandbox platforms
4. **Improve Documentation** — PRs welcome

## Hash Format Requirements

| Type | Length | Format | Example |
|------|--------|--------|---------|
| MD5 | 32 | lowercase hex | `d41d8cd98f00b204e9800998ecf8427e` |
| SHA1 | 40 | lowercase hex | `da39a3ee5e6b4b0d3255bfef95601890afd80709` |
| SHA256 | 64 | lowercase hex | `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855` |

### Invalid
- Uppercase characters
- Wrong length
- Non-hex characters
- With prefixes (`sha256:`, `md5:`, etc.)

### Validation Checklist
- [ ] Exact correct length for hash type
- [ ] Lowercase hex only
- [ ] Verified on VirusTotal (≥3 detections)
- [ ] Verified on MalwareBazaar (if available)
- [ ] Not a legitimate system file / known good software

## Automated Pipeline

- Source: MalwareBazaar (recent + by type)
- 2 new hashes per 12-hour cycle (SHA256 prioritized)
- Validated against VT + MalwareBazaar
- Deduplicated across all partitions

## Partition Limits
- MD5: 3,000 per file
- SHA1: 1,000 per file
- SHA256: 60,000 per file

## License

MIT License.