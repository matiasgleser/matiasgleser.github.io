---
title: Usage

weight: 1
---


## Endpoints

Three valid endpoints are allowed (Snapshot, Delayed, and EndOfDay). The client must ensure they have credentials that grant access to the specified endpoint.

```python
from bymadata_api_wrapper import SnapshotAPI, DelayedAPI, EndOfDayAPI

# Specify client ID and client secret key to initialize
sn = SnapshotAPI(client_id="<Client ID>", client_secret="<Client Secret Key>")  # Snapshot endpoint
delayed = DelayedAPI(client_id="<Client ID>", client_secret="<Client Secret Key>")  # Delayed endpoint
eod = EndOfDayAPI(client_id="<Client ID>", client_secret="<Client Secret Key>")  # EndOfDay endpoint
```

## Available Paths

For all endpoints, several paths are available:

### Equity Data

```python
# Equity Data
sn.equity(ticker=None, settle_period="0003", group="ACCIONES", subgroup=None, operative_form="CONTADO", currency="ARS")
```

### Fixed Income Data

```python
# Fixed Income Data
sn.fixed_income(ticker=None, settle_period="0003", group="TITULOSPUBLICOS", market="PPT", operative_form="CONTADO", currency="ARS")
```

### Futures Data

```python
# Futures Data
sn.futures(group="FUTMONEDAS")
```

### Options Data

```python
# Options Data
sn.options(ticker=None, currency="ARS")
```

### Repos Data

```python
# Repos Data
sn.repos(group="CAUCIONES")
```

### Trading Lots Data

```python
# Trading Lots Data
sn.trading_lots(group="PXL", currency="ARS")
```

### Loans Data

```python
# Loans Data
sn.loans(group="PRESTAMOSV", currency="ARS")
```

### Indices Data

```python
# Indices Data
sn.indices()
```

### Turnover Data

Returns aggregate market turnover data.

```python
# Turnover Data
sn.turnover()
```

### Intraday Operations Data

Returns intraday operations for a security. A security can be determined by its `security_id` parameter or constructed by function parameters. If both are determined, `security_id` takes preference.

```python
# Intraday Operations Data
sn.intraday_ops(ticker=None, settle_period="0003", currency="ARS", market="CT", operative_form="C", security_id=None)
```


