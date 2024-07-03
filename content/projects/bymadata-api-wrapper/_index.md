---
title: BymaData API Wrapper
# date: 2024-01-01
# date: 2024-01-01T00:00:00Z
draft: true
toc: true

description: Unofficial wrapper for the recently released BymaData API. 
---


Unofficial wrapper for the recently released [BymaData API service](https://www.bymadata.com.ar/). Developed by [Matias Gleser](https://twitter.com/MatiasGleser).

## Features

- Full support for all BymaData API services.
- Support for Python 3.6+

## Installation

To install this module, run:

```console
pip install git+https://github.com/matiasgleser/bymadata-api-wrapper.git
```

## Usage

### Endpoints

Three valid endpoints are allowed (Snapshot, Delayed, and EndOfDay). The client must ensure they have credentials that grant access to the specified endpoint.

```python
from bymadata_api_wrapper import SnapshotAPI, DelayedAPI, EndOfDayAPI

# Specify client ID and client secret key to initialize
sn = SnapshotAPI(client_id="<Client ID>", client_secret="<Client Secret Key>")  # Snapshot endpoint
delayed = DelayedAPI(client_id="<Client ID>", client_secret="<Client Secret Key>")  # Delayed endpoint
eod = EndOfDayAPI(client_id="<Client ID>", client_secret="<Client Secret Key>")  # EndOfDay endpoint
```

### Available Paths

For all endpoints, several paths are available:

#### Equity Data

```python
# Equity Data
sn.equity(ticker=None, settle_period="0003", group="ACCIONES", subgroup=None, operative_form="CONTADO", currency="ARS")
```

#### Fixed Income Data

```python
# Fixed Income Data
sn.fixed_income(ticker=None, settle_period="0003", group="TITULOSPUBLICOS", market="PPT", operative_form="CONTADO", currency="ARS")
```

#### Futures Data

```python
# Futures Data
sn.futures(group="FUTMONEDAS")
```

#### Options Data

```python
# Options Data
sn.options(ticker=None, currency="ARS")
```

#### Repos Data

```python
# Repos Data
sn.repos(group="CAUCIONES")
```

#### Trading Lots Data

```python
# Trading Lots Data
sn.trading_lots(group="PXL", currency="ARS")
```

#### Loans Data

```python
# Loans Data
sn.loans(group="PRESTAMOSV", currency="ARS")
```

#### Indices Data

```python
# Indices Data
sn.indices()
```

#### Turnover Data

Returns aggregate market turnover data.

```python
# Turnover Data
sn.turnover()
```

#### Intraday Operations Data

Returns intraday operations for a security. A security can be determined by its `security_id` parameter or constructed by function parameters. If both are determined, `security_id` takes preference.

```python
# Intraday Operations Data
sn.intraday_ops(ticker=None, settle_period="0003", currency="ARS", market="CT", operative_form="C", security_id=None)
```

### Wrapper Functions and Corresponding API Endpoints

| Wrapper Function   | API Path                | Full API URI                                        |
| ------------------ | ----------------------- | --------------------------------------------------- |
| `equity()`         | `equity`                | `api-mgr.byma.com.ar/{endpoint}/equity`             |
| `fixed_income()`   | `fixed_income`          | `api-mgr.byma.com.ar/{endpoint}/fixed_income`       |
| `futures()`        | `futures`               | `api-mgr.byma.com.ar/{endpoint}/futures`            |
| `options()`        | `options`               | `api-mgr.byma.com.ar/{endpoint}/options`            |
| `repos()`          | `collateralized_repos`  | `api-mgr.byma.com.ar/{endpoint}/collateralized_repos`|
| `trading_lots()`   | `trading_lots`          | `api-mgr.byma.com.ar/{endpoint}/trading_lots`       |
| `loans()`          | `loans`                 | `api-mgr.byma.com.ar/{endpoint}/loans`              |
| `indices()`        | `indices`               | `api-mgr.byma.com.ar/{endpoint}/indices`            |
| `turnover()`       | `turnover`              | `api-mgr.byma.com.ar/{endpoint}/turnover`           |
| `intraday_ops()`   | `intraday`              | `api-mgr.byma.com.ar/{endpoint}/intraday`           |

## Contributing

If you encounter a bug or would like to see new features added to **bymadata-api-wrapper**, please [file an issue](https://github.com/matiasgleser/bymadata-api-wrapper/issues) or [submit a pull request](https://help.github.com/en/articles/creating-a-pull-request).
