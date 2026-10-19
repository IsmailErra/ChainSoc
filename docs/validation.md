# Validation record and evidence limits

[Back to the case study](../README.md)

The supplied sources document a working lab demonstration. This repository review did not execute the original application because its source and running environment were not supplied. Screenshot text reports application output, and is not an independent verification of chain state.

## Demonstration trace

| Step | Report reference | Observation | Qualification |
| --- | --- | --- | --- |
| Introduce a synthetic event | §3.1.1, figure 3.1, PDF p.42 | Target terminal uses `logger` for `demo1` | Controlled input, not evidence of a real compromise |
| Invoke the collector | §3.1.2, figure 3.2, PDF p.43 | Watcher runs the script and prints an alert | Screenshot first clears the last-processed marker and invokes the script manually |
| Receive notification | §3.1.3, figure 3.3, PDF p.43 | Inbox contains the security alert and event text | No timed delivery measurement or storage acknowledgment |
| Find the event on Vault | §3.1.4, figure 3.4, PDF p.43 | `vault_logs.txt` contains `demo1` | Confirms the shown transfer result |
| Inspect evidence output | §3.1.5, figure 3.5, PDF p.44 | `BLOCKCHAIN_STORAGE_SUCCESS`, CID, digest, and transaction values appear | No raw receipt or exported contract state accompanies them |
| Inspect the dashboard | §3.1.6, figures 3.6–3.7, PDF pp.44–45 | Events, pending/stored labels, and proof fields appear | Some evidence is still pending. UI state alone does not prove verification |
| Produce a report | §3.1.7, figure 3.8, PDF p.45 | Printable report lists raw event, digest, CID, and transaction | The presentation demo also shows the print/save workflow |

## Component checks

The report additionally shows failed SSH logins and log inspection (figures 2.4–2.5), IPFS add/read operations (figures 2.11–2.12), Remix compilation/deployment (figures 2.15–2.16), and contract write/read interaction (figures 2.17–2.18).

The contract exercise uses `abc123hash` as a placeholder. It establishes the demonstrated interface behavior, not a correct SHA-256 calculation. The later pipeline output shows digest-shaped values, but the exact original byte stream and contract records are unavailable for independent recomputation.

## Reported behavior with incomplete validation

| Behavior | What the report provides | Evidence still needed |
| --- | --- | --- |
| Four YAML detection rules | Patterns, thresholds, severities, one YAML example | Detector source and positive/negative tests for each rule |
| One-minute automated processing | Cron entries and a qualitative timing statement | Timestamped event-to-detection measurements across repeated runs |
| Automatic integrity verification | UI description, script names, status messages | Exact original bytes, retrieved bytes, recomputed digest, and contract read result |
| Tamper detection | Integrity/attack controls and narrative claims | Before/after file changes with the verifier output and recorded baseline |
| Dashboard blockchain interaction | A control explicitly described as simulated, plus separate Vault/Remix records | Frontend/backend source and request/receipt trace |

## Claims excluded from the showcase's results

The report's benchmark tables and conclusion claim attack resistance, 99.9% availability, support for 10–1000+ nodes, 33% fault tolerance, and relative cost/resource improvements. They do not supply the test setup, repeated measurements, failure logs, or baseline implementation needed to assess those claims. The attack table labels its total as seven tests while displaying six attack categories, further limiting interpretation.

This repository therefore makes no measured DDoS-resistance, man-in-the-middle-defense, fault-tolerance, cost-saving, throughput, uptime, or superiority claim over other SOC platforms.

## Trust assumptions and engineering limits

- **Collection precedes proof.** A compromised Target can emit misleading data or remove an event before collection. Anchoring the collected content does not prove source truth.
- **Tamper evidence needs comparison.** A changed file produces a different digest, but a verifier still needs to compare the correct bytes against a trusted baseline. The blockchain does not automatically monitor arbitrary file changes.
- **Content addressing and persistence differ.** An IPFS CID identifies content. Continued retrieval depends on retaining and serving that content. A stored CID alone does not prevent loss.
- **The local chain is under lab control.** Ganache does not establish independent consensus or persistence against an administrator who resets the lab.
- **The single orchestration path can fail.** Watcher and Vault availability remain necessary for the demonstrated processing path. Replicated infrastructure was proposed as future work.
- **Plaintext has confidentiality implications.** The prototype does not document encryption before IPFS storage.
- **Proof association needs validation.** Repeated entries appear in Vault output. Dashboard evidence values are not fully matched to individual Vault entries in the supplied captures.

## Proposed next verification work

These are future checks, not completed tests:

1. Preserve an event as a file with an explicit encoding and newline policy. Recompute its SHA-256 after IPFS retrieval and compare it with a contract read.
2. Change one byte and confirm that the same verifier rejects the altered file while accepting the original.
3. Send several events between polls, then interrupt SMTP, IPFS, and RPC in turn. Verify durable recovery and whether any events are dropped or duplicated.
4. Test each YAML rule at, below, and above its threshold, including expiration of its time window.
5. Confirm that UI statuses follow actual receipt/verification outcomes, including pending and failed transactions.
6. Stop Watcher, Vault, and storage services separately. Measure behavior before making availability claims.

All source references use PDF page numbers. Printed report pages run nine pages behind the PDF page number after the front matter.
