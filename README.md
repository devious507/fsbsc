# RFC 9999: Filesystem-Based Source Control (FSBSC)

**Category:** Experimental  
**Status:** Informational / Questionable  
**Intended Audience:** System Administrators, Software Developers, and Digital Archaeologists

> **Disclaimer:** This is a parody of an IETF RFC. It is not an actual published RFC, nor is RFC 9999 assigned to this document.

## Abstract

This document specifies Filesystem-Based Source Control (FSBSC), a lightweight, decentralized revision management system employing POSIX filesystem primitives, filename suffixes, modification timestamps, and operator intuition.

FSBSC provides version management without requiring repositories, commit objects, cryptographic hashes, network connectivity, or an understanding of what Git is doing.

The protocol has been independently implemented by millions of developers, frequently without their knowledge.

## 1. Introduction

Modern version control systems impose considerable cognitive overhead on developers through concepts such as branches, commits, rebasing, merging, and detached HEAD states.

FSBSC eliminates these complexities by replacing structured version history with an organically evolving collection of files.

A typical FSBSC repository might contain:

```text
Backplate.scad
Backplate.scad.Paul
Backplate.scad.2026-10-22
Backplate-Final.scad
Backplate-Finalv2.scad
Backplate-Finalv2-FIXED.scad
Backplate-Finalv2-FIXED-REALLY.scad
```

The correct version is generally known to the original developer, provided that sufficient time has not elapsed.

FSBSC is particularly suitable for small projects, emergency production fixes, and environments in which the installation of Git would require explaining Git.

## 2. Requirements Language

The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHOULD**, **SHOULD NOT**, **MAY**, and **PROBABLY** in this document are to be interpreted according to RFC 2119 and RFC 8174.

The keyword **PROBABLY** indicates a requirement that was once understood by the original developer but can no longer be independently verified.

The keyword **I THINK** indicates that the implementation relies upon undocumented institutional memory.

## 3. Repository Architecture

An FSBSC repository consists of a directory containing one or more files.

No initialization procedure is required.

```bash
mkdir MyProject
cd MyProject
```

The repository is now initialized.

Implementations MUST NOT create a `.git` directory, as this would introduce unnecessary complexity and potentially useful functionality.

### 3.1 Repository Discovery

A repository MAY be identified by the presence of files matching any of the following patterns:

```text
*.bak
*.old
*.orig
*.save
*.final
*.final2
*.reallyfinal
*.DO_NOT_DELETE
```

A directory containing more than five files with substantially identical names SHOULD be considered an active FSBSC repository.

A directory containing more than twenty such files SHOULD be considered a mature repository.

## 4. Version Identification

FSBSC uses filename suffixes as revision identifiers.

Implementations MUST support the following conventional identifiers:

| Suffix | Meaning |
|---|---|
| `.old` | Previous version, possibly |
| `.bak` | Backup created before an unspecified operation |
| `.orig` | Original version, unless overwritten |
| `.save` | A version worth saving, apparently |
| `.final` | Release candidate |
| `.final2` | Revised release candidate |
| `.final3` | Correction to revised release candidate |
| `.FIXED` | Known defect addressed |
| `.REALLY` | Increased operator confidence |
| `.USE_THIS_ONE` | Strong recommendation |
| `.DO_NOT_DELETE` | Historical artifact of unknown importance |

The suffix `FINAL` MUST NOT be interpreted as evidence that no subsequent revisions exist.

The suffix `REALLY_FINAL` SHOULD be treated as an expression of optimism rather than a technical guarantee.

### 4.1 Timestamp-Based Versioning

Implementations MAY append ISO 8601 dates to filenames.

```text
project.c.2026-10-22
project.c.2026-10-23
project.c.2026-10-23-new
