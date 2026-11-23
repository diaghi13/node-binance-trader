# node-binance-trader

Developing a Binance trading strategy requires market data, signal detection, and a way to test decisions before placing orders. node-binance-trader is a TypeScript framework for recording that data, backtesting strategies, and executing trades from signals.

## Features

- Record Binance candles, order-book depth, and trades for selected asset pairs in PostgreSQL.
- Detect buy and sell signals through the server component.
- Execute trades from signals received from your own server.
- Trade with leverage on pairs available for margin trading.
- Backtest strategies against historical tick data recorded by the server.

## Installation

Install Node.js, npm, and PostgreSQL before setting up the project. From the project checkout, install dependencies and compile the TypeScript source:

```sh
npm install
npx tsc
```

Compilation uses the repository's TypeScript configuration. Check its output directory before running the compiled scripts.

Configure the PostgreSQL connection and the asset pairs you want the server to track. The trader also needs Binance API credentials for order execution. Keep credentials out of version control and grant only the permissions required for your use case.

## Usage

The framework separates data collection and signal detection from trade execution. Run the server to record market data, then use the backtest component to evaluate strategies against those records. Run the trader when you are ready to execute signals from your server.

For example, launch a compiled server script with Node.js source-map support:

```sh
node --enable-source-maps ./path/to/compiled/server.js
```

Replace `./path/to/compiled/server.js` with the actual compiled server entry point. The path is illustrative; it is not a documented executable or CLI provided by the donor project. Database settings, trading pairs, and credentials must be configured according to the source before launch.

**Live trading can lose money.** Backtest results do not guarantee future returns, and leverage increases exposure to losses. Review strategy behavior and order execution before allowing the trader to place real orders.

The upstream project is archived following the shutdown of bitcoinvsalts.com. Its hosted hub should not be assumed available; use your own server as the signal source.

<!-- seorepo:network:start -->
## More tools from our network

- [**octo-cli**](https://github.com/boostlyapi/octo-cli) — CLI на Go для публикации данных из PostgreSQL, MSSQL и MySQL через бессерверные веб-сервисы в OpenFaaS или Knative. Конфигурация сервиса задаётся в YAML.
- [**tool**](https://github.com/boostlyapi/tool) — CLI на Go для Apache Kafka: чтение и отправка сообщений в JSON, просмотр топиков, управление смещениями consumer groups и базовое администрирование.
- [**docker-ikev2-vpn-server**](https://github.com/Cabral-it/docker-ikev2-vpn-server) — Docker-based IKEv2 VPN server with shared-secret authentication and .mobileconfig generation for iOS and macOS, based on gaomd/docker-ikev2-vpn-server.
- [**akrobateo**](https://github.com/Dyooooou/akrobateo) — A Go Kubernetes operator that exposes LoadBalancer services through node hostPorts using DaemonSets and synchronizes their load balancer addresses.
- [**node-hnsn**](https://github.com/ghb13/node-hnsn) — A TypeScript node for decentralized document timestamping with Bitcoin and IPFS, with an HTTP API for signed work claims and file uploads.
- [**wg-access-server**](https://github.com/EngHirsi/wg-access-server) — A WireGuard VPN server with a web UI for user authentication, one-click device registration, QR-code setup, and configurable network isolation.
<!-- seorepo:network:end -->

## License

MIT. This project is based on [bitcoinvsalts/node-binance-trader](https://github.com/bitcoinvsalts/node-binance-trader). Retain the original copyright and MIT permission notices when distributing this code or substantial portions of it. The software is provided without warranty; you are responsible for its use.
