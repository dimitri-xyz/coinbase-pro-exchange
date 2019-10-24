# Haskell + Coinbase Pro

This library provides an unofficial Haskell client for the [Coinbase Pro API](https://docs.pro.coinbase.com). 

The library's goal is to provide the basic functionality for automated trading in Haskell on the Coinbase Pro exchange. We intend to implement the full functionality of both the public and authenticated REST and Websocket APIs, but development is currently very much incomplete.

Use of this software is provided under an MIT license, on an "as-is" basis, and without any warranty. Users should be aware that this software is a work in progress, and they should expect unimplemented or buggy functionality, including bugs that may lead to financial losses if used with a funded account on Coinbase Pro's live trading server.

Please report bugs and request features on the [issue tracker](https://github.com/dimitri-xyz/coinbase-pro-exchange/issues). Feedback and pull requests are welcome.

Because there is no FIX engine available in Haskell, the FIX API is beyond the scope of this project. Note also that this library does not implement any functionality provided by the [other Coinbase APIs](https://developers.coinbase.com) for wallets and e-commerce.

## Installation

An up-to-date version of this library is not currently available on Hackage. To install it, download the source from this repository and build with `cabal-install` or `stack` in the usual way:

### Download and build with cabal

```
> git clone https://github.com/dimitri-xyz/coinbase-pro-exchange.git
  ...
> cd coinbase-pro-exchange
> cabal install
  ...
> cabal build
  ...
```

### Download and build with stack

```
> git clone https://github.com/dimitri-xyz/coinbase-pro-exchange.git
  ...
> cd coinbase-pro-exchange
> stack build
  ...
```

## Configuration and Basic Usage

The client reads several environment variables at runtime to authenticate private API calls and to choose whether to connect to Coinbase Pro's sandbox server (for testing the API with fake money) or to the live server (for trading with real money).

Set `COINBASE_PRO_SANDBOX` to `TRUE` to connect to the sandbox server, or to `FALSE` to connect the live server. In `bash`, run the this command to use the sandbox server:

```bash
> export COINBASE_PRO_SANDBOX=TRUE # Use the sandbox server
```

Always test code on the sandbox server before running it on the live server.

To make authenticated private API calls, users must provide their API key, secret, and passphrase. (To generate these credentials for a sandbox or live account, see the "API Keys" section of the account settings at, respectively, https://public.sandbox.pro.coinbase.com or https://pro.coinbase.com). Set the `COINBASE_PRO_KEY`, `COINBASE_PRO_SECRET` and `COINBASE_PRO_PASSPHRASE` appropriately:

```bash
> export COINBASE_PRO_KEY=<your API key>
> export COINBASE_PRO_SECRET=<your API secret>
> export COINBASE_PRO_PASSPHRASE=<your API passphrase>
 ```

Provide credentials for the sandbox server if `COINBASE_PRO_SANDBOX` is set to `TRUE`, or credentials for the live server if it's set to `FALSE`.

After setting these environment variables set, you can connect to Coinbase's sever.

TODO: Provide an example of basic usage.

## Related Projects

This project continues development begun at [AndrewRademacher/coinbase-exchange])(https://github.com/AndrewRademacher/coinbase-exchange), which is no longer maintained. There is another Haskell client under current development at [mdunnio/coinbase-pro](https://github.com/mdunnio/coinbase-pro).
