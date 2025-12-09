---
layout: page
title: Path ORAM - Encrypted Data Structures
description: C++ implementation of Oblivious RAM protocols for secure storage systems, hiding data access patterns from untrusted servers
img:
importance: 1
category: featured
github: https://github.com/VictorGChen/PathORAM
---

## Overview

A C++ implementation of Oblivious RAM (ORAM) protocols designed to hide data access patterns from untrusted servers. Even with encrypted data, access patterns can leak sensitive information - this project addresses that security challenge.

## Key Features

- **Full Path ORAM Implementation**: Tree-based architecture with O(log N) access time
- **AES-256-CBC Encryption**: Industry-standard data security
- **rORAM Extension**: Enhanced version optimizing performance for range queries
- **Client-Server Architecture**: Separates data management responsibilities
- **Performance Benchmarking**: Reduced range query overhead by 300× across database sizes (2¹⁴-2¹⁶ blocks)

## Technical Implementation

### Core Components
- **Blocks & Buckets**: Fundamental storage units
- **BucketHeap**: Binary tree structure for efficient data organization
- **Client Module**: Handles cryptographic operations and position mapping
- **Server Module**: Manages storage and data retrieval

### Two Implementations
1. **Path ORAM** (`path_oram_disc`): Foundational scheme offering O(log N) access time
2. **rORAM** (`rORAM_paper`): Enhanced version with multiple trees, improved position maps, and batch evictions

## Technologies Used

- C++
- AES-256-CBC Encryption
- Git/GitHub for collaboration
- Advanced data structures and algorithms

## Performance

Benchmarked I/O performance across varying database sizes, demonstrating significant efficiency improvements for range queries while maintaining security guarantees.

## Links

- [GitHub Repository](https://github.com/VictorGChen/PathORAM)
- Full implementation details and documentation available on GitHub
