# Multi-Threaded Proxy Server with and without Cache

This project implements a multi-threaded proxy server in C, offering both cached and non-cached modes to enhance network efficiency and client anonymity. Leveraging concurrency and caching mechanisms, this server processes multiple client requests simultaneously and improves response time for frequently accessed websites.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technical Details](#technical-details)
- [Setup and Usage](#setup-and-usage)
- [Demo](#demo)
- [Contribution](#contribution)

---

## Overview
This proxy server acts as an intermediary between clients and external web servers. It reduces load on the main server by caching frequently accessed websites and provides anonymity for client requests. This project showcases a fundamental understanding of network requests, concurrency, and cache management.

### How It Works
- The server listens for client requests on a specified port.
- Each incoming request is managed by a new thread, allowing concurrent handling of multiple clients.
- For cached mode, the server checks if the requested resource is available in the cache, using an LRU (Least Recently Used) caching algorithm. If found, the resource is served from the cache; otherwise, it is fetched from the target server, stored in the cache, and served to the client.

## Features
- **Concurrency**: Handles multiple simultaneous requests using POSIX threads (pthread) and semaphores.
- **Caching**: Implements an LRU cache to store frequently accessed responses, reducing response time and server load.
- **Anonymity and Security**: Modifies IP requests to anonymize client data and restricts access to specific URLs as defined.
- **Extensibility**: Designed to support future enhancements such as request encryption, POST request handling, and URL blocking.

## Technical Details
- **Language**: C
- **Concurrency Mechanism**: POSIX threads (pthread) with semaphores for thread synchronization.
- **Caching**: Uses an LRU caching algorithm to manage storage of frequently accessed URLs.
- **Limitations**:
  - Only works on Linux.
  - Cache size and element size are fixed, limiting the storage of large websites.
  - Responses with multiple clients are stored separately, which may lead to slower retrieval for complex sites.

## Setup and Usage

1. **Clone the Repository**
   ```bash
   git clone https://github.com/AlphaDecodeX/MultiThreadedProxyServerClient.git
   cd MultiThreadedProxyServerClient