# Electrum ETH

![Python](https://img.shields.io/badge/python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-2B2B2B?style=flat-square)
![Type](https://img.shields.io/badge/type-ElectrumX%20server-4B5563?style=flat-square)

## Overview

Electrum ETH is a Python-based ElectrumX server implementation. It indexes blockchain data and exposes Electrum protocol services for lightweight clients.

## Capabilities

- Asynchronous Electrum protocol server
- Blockchain indexing and transaction history lookup
- Mempool tracking
- Configurable TCP, SSL, WS, and WSS services
- Daemon failover via multiple RPC endpoints
- LevelDB or RocksDB backend support

## Setup

| Item | Value |
| --- | --- |
| Python | 3.8+ |
| Base deps | `aiorpcX`, `attrs`, `plyvel`, `aiohttp` |
| Install | `pip install -r requirements.txt` |
| Package | `pip install .` |

Required environment variables:

- `COIN`
- `DB_DIRECTORY`
- `DAEMON_URL`
- `SERVICES`

Example:

```bash
export COIN=Bitcoin
export DB_DIRECTORY=/var/lib/electrumx
export DAEMON_URL=http://user:pass@127.0.0.1:8332/
export SERVICES=tcp://0.0.0.0:50001
```

## Usage

Start the server:

```bash
electrumx_server
```

Useful commands:

- `electrumx_rpc`
- `electrumx_compact_history`

## Technical Notes

- Package name: `e-x`
- Version in source: `1.16.0`
- Main package: `electrumx/`
- Docs: `docs/`
- Test suite: `tests/`

## License

MIT. See `LICENCE`.
