# Electrum ETH

[![Runtime](https://img.shields.io/badge/Runtime-Python_3.8%2B-1f2937?style=for-the-badge&labelColor=111827)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-374151?style=for-the-badge&labelColor=111827)](./LICENCE)
[![Profile](https://img.shields.io/badge/Profile-ElectrumX_Server-4b5563?style=for-the-badge&labelColor=111827)](#boot-sequence)

```text
node rpc -> indexer/db -> electrum sessions
```

Electrum-facing server process for chain indexing, history lookup, mempool tracking, and network serving.

![Electrum ETH setup screen](screen/setup.jpg)

## Boot Sequence

```bash
pip install -r requirements.txt
pip install .

export COIN=<coin-class-name>
export DB_DIRECTORY=/var/lib/electrumx
export DAEMON_URL=http://user:pass@127.0.0.1:<node-rpc-port>/
export SERVICES=tcp://0.0.0.0:50001

electrumx_server
```

`COIN` must match a coin class available to this build.

## Runtime Notes

- package: `e-x`
- version: `1.16.0`
- loop: `asyncio`
- transports: `tcp`, `ssl`, `ws`, `wss`, `rpc`
- storage: LevelDB or RocksDB
- control plane: environment variables

## Operator Surface

```text
electrumx_server          main process
electrumx_rpc             runtime/admin rpc
electrumx_compact_history history compaction
```

## Tree

```text
electrumx/server/   long-running services, sessions, daemon bridge
electrumx/lib/      coins, hashes, scripts, serializers, shared utils
docs/               protocol and ops docs
tests/              protocol, storage, daemon, parser coverage
contrib/            example configs and deployment helpers
```

## License

MIT. See `LICENCE`.
