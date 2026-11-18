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

## License

MIT. This project is based on [bitcoinvsalts/node-binance-trader](https://github.com/bitcoinvsalts/node-binance-trader). Retain the original copyright and MIT permission notices when distributing this code or substantial portions of it. The software is provided without warranty; you are responsible for its use.
