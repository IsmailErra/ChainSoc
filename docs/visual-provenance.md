# Visual provenance

[Back to the case study](../README.md)

The visuals are original project evidence extracted directly from the supplied PDF's embedded images. They retain native pixel dimensions within each crop. No data, statuses, hashes, or event counts were replaced. PNG optimization is lossless.

## Source materials reviewed

- **Report:** `G2_chainsoc.pdf`, 48 PDF pages, academic year 2025–2026.
- **Presentation:** `Boudhih Hajar Erraouidate Ismail Benhilal Oumaima Meska Anass.pptx`, 12 slides, dated May 21, 2026. Slide 8 illustrates the final data flow. The embedded demo runs approximately 326.65 seconds.

Both sources were reviewed for technical content and visual candidates. Sampled demo frames show terminals, the React dashboard, a print/save dialog, Vault evidence output, and the received email. The PDF contains cleaner and more readable versions of the same evidence, so the published image set uses the PDF originals.

The complete documents and video are intentionally excluded. They contain material unnecessary for the case study, including lab credentials, personal inbox details, and desktop context.

## Selected images

Crop coordinates below use the embedded image's native pixels: `(left, top, right, bottom)`. PDF page numbers count the cover as page 1.

| Asset | Source | Native source size | Crop | Selection reason |
| --- | --- | --- | --- | --- |
| [Original pipeline](../assets/architecture/original-pipeline.png) | Figure 1.1, PDF p.14 / printed p.5 | 1224 × 522 | Full image | Original technical architecture for comparison with the English Mermaid diagram |
| [Monitoring overview](../assets/dashboards/monitoring-overview.png) | Figure 3.6, PDF p.44 / printed p.35 | 1905 × 797 | `(250, 170, 1640, 797)` | Strongest overview of the actual interface and alert states |
| [Event evidence](../assets/dashboards/event-evidence.png) | Figure 3.7, PDF p.45 / printed p.36 | 1727 × 873 | `(280, 0, 1640, 852)` | Connects raw content to the digest, CID, and transaction while retaining pending states |
| [Evidence report](../assets/dashboards/evidence-report.png) | Figure 3.8, PDF p.45 / printed p.36 | 1908 × 843 | `(30, 178, 1150, 780)` | Readable event report body without browser controls or excess blank space |
| [Watcher detection](../assets/security-tests/watcher-detection.png) | Figure 3.2, PDF p.43 / printed p.34 | 1156 × 420 | `(78, 230, 1090, 370)` | Collector invocation and its alert output, including the visible marker reset |
| [Email alert](../assets/security-tests/email-alert.png) | Figure 3.3, PDF p.43 / printed p.34 | 1184 × 474 | `(218, 30, 1175, 450)` | Received message content, excluding sender address and personal inbox sidebar |
| [Vault output](../assets/security-tests/vault-blockchain-output.png) | Figure 3.5, PDF p.44 / printed p.35 | 1156 × 796 | `(68, 145, 1156, 775)` | Actual storage output, retaining repeated records and all displayed identifiers |
| [Contract readback](../assets/security-tests/contract-readback.png) | Figure 2.18, PDF p.37 / printed p.28 | 1323 × 366 | `(0, 0, 1320, 346)` | Actual Remix result, explicitly labeled as a placeholder-data exercise |
| [IPFS add](../assets/security-tests/ipfs-add.png) | Figure 2.11, PDF p.33 / printed p.24 | 667 × 123 | `(0, 0, 667, 90)` | Compact component test showing a content identifier returned by IPFS |

The README integrates the main demonstration images next to the claims they support. Component-level IPFS and Remix images appear in the implementation notes. Readers can open any image at native resolution to inspect small text.

## Excluded candidates

- Generic cybersecurity artwork, stock icons, presentation backgrounds, school branding, and schedule diagrams add little implementation evidence.
- User-creation and connection-summary material includes lab credentials and is not published.
- Ganache account-list screens may expose local development keys or account material. Those images are not published.
- Full email and desktop captures contain personal context. Only the cropped message body is included.
- Full-screen demo frames are less readable than the PDF originals and include unrelated desktop content.
- Additional terminal screenshots largely repeat setup steps already explained in the notes.

The published crops retain lab hostnames and local usernames where they are part of the terminal evidence. Content identifiers, digests, and local transaction hashes are evidence identifiers, not login credentials. No private keys, passwords, or application passwords are included in the selected images or text.
