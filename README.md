# orbitflare-sdk-proto

Internal crate for [`orbitflare-sdk`](https://crates.io/crates/orbitflare-sdk). Contains the compiled protobuf types for OrbitFlare's gRPC services (Yellowstone Geyser and JetStream).

You should not depend on this crate directly. Use [`orbitflare-sdk`](https://crates.io/crates/orbitflare-sdk) instead:

```bash
cargo add orbitflare-sdk --features grpc
```

## Protocol definitions

| Proto | Package | Service | Purpose |
| --- | --- | --- | --- |
| [`geyser.proto`](protos/geyser.proto) | `geyser` | `Geyser` | Yellowstone Geyser (Dragon's Mouth) streaming interface for subscribing to accounts, transactions, slots, blocks, and entries. |
| [`jetstream.proto`](protos/jetstream.proto) | `jetstream` | `Jetstream` | OrbitFlare JetStream v1 streaming service - filtered transaction and slot updates over gRPC. |
| [`jetstream_v2.proto`](protos/jetstream_v2.proto) | `jetstream.v2` | `JetstreamV2` | JetStream v2 with a flat transaction representation (lean by default, optional enrichment) plus slot subscriptions and unary RPCs. |
| [`solana-storage.proto`](protos/solana-storage.proto) | `solana.storage.ConfirmedBlock` | - | Shared Solana block and transaction storage types. Imported by `geyser.proto`; not a service of its own. |
