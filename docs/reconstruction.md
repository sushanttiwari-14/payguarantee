# Snapshot reconstruction

The source is https://github.com/Aniket-pd/payproof. All 11 commits reachable from its default branch were replayed in chronological, topology-respecting order into a fresh linear Git repository. The source includes two roots and a merge: checkpoint 5 is intentionally a CI-only tree, and checkpoint 6 restores the merged application tree. This preserves each full snapshot rather than applying patches across unrelated roots.

Each checkpoint copies tracked file bytes and Git executable/symlink modes. Markdown files are excluded, except `presentation/NOTICE.md`, which preserves attribution. The MIT license and font license text files remain unchanged wherever present in the source snapshot. Documentation-only checkpoints produce empty commits. Commit author/committer use the configured local Git identity and current reconstruction timestamps. Original commit objects, parents, author metadata, and commit IDs are not imported.

All reconstructed trees were verified by exact path, blob ID (content), and file mode equality against the filtered source tree. Blob equality is intentional: file contents remain identical while commit identities are new. The final separate documentation commit adds newly written documentation only.

| Checkpoint | Retained files | Excluded Markdown files | Verification |
| --- | ---: | ---: | --- |
| 01 | 148 | 19 | Exact bytes and modes |
| 02 | 150 | 19 | Exact bytes and modes |
| 03 | 158 | 21 | Exact bytes and modes |
| 04 | 158 | 23 | Exact bytes and modes |
| 05 | 1 | 0 | Exact bytes and modes |
| 06 | 158 | 23 | Exact bytes and modes |
| 07 | 158 | 23 | Exact bytes and modes |
| 08 | 169 | 25 | Exact bytes and modes |
| 09 | 169 | 25 | Exact bytes and modes |
| 10 | 169 | 26 | Exact bytes and modes |
| 11 | 169 | 26 | Exact bytes and modes |

The application name, package metadata, API paths, archive name, and UI branding remain PayProof to retain source fidelity. `payguarantee` is the new repository/folder name. No copied implementation is claimed as newly authored. Historical evidence dates and original asset notices remain intact.
