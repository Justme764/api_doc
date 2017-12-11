---
title: Electric Vehicle Charging

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:

search: true
---

# Introduction

The communication protocol for Electric Vehicle charging describes the format of a request for a charging service, and the response sent by a charging provider.

# Request

A statement of need for charging stations, typically sent by an electric vehicle.

## Arguments

```shell
# Post request to a local/remote discovery endpoint
curl "discovery_endpoint_here"
  --data "connector=tesla_supercharger"
  --data "level=3"
```

<table class="arguments">
  <tr>
    <td>
      <div class="field">connector</div>
      <div class="type">optional</div>
    </td>
    <td>The connector type required by the EV. Specified as a connector id. See <a href="#connector-types">Connector Types</a> for available values.</td>
  </tr>
  <tr>
    <td>
      <div class="field">level</div>
      <div class="type">optional</div>
    </td>
    <td>The charging level as defined by SAE standards. Specified as an integer. See <a href="#charging-levels">Charging Levels</a>.</td>
  </tr>
</table>

# Connector Types

<table class="reference connectors">
  <tr>
    <th>Connector ID</th>
    <th>Name</th>
    <th>Power Level</th>
  </tr>
  <tr>
    <td>nema_5_15</td>
    <td>NEMA 5-15 Wall Outlet</td>
    <td>1</td>
  </tr>
  <tr>
    <td>nema_5_20</td>
    <td>NEMA 5-20 Wall Outlet</td>
    <td>1</td>
  </tr>
  <tr>
    <td>j1772</td>
    <td>SAE J1772</td>
    <td>2</td>
  </tr>
  <tr>
    <td>mennekes</td>
    <td>SAE J3068 / IEC 62196 (Mennekes)</td>
    <td>2</td>
  </tr>
  <tr>
    <td>nema_14_50</td>
    <td>NEMA 14-50 (RV plug)	</td>
    <td>2</td>
  </tr>
  <tr>
    <td>chademo</td>
    <td>CHAdeMO</td>
    <td>3</td>
  </tr>
  <tr>
    <td>ccs</td>
    <td>SAE Combined Charging System (CCS)</td>
    <td>3</td>
  </tr>
  <tr>
    <td>tesla_hpwc</td>
    <td>Tesla HPWC</td>
    <td>2</td>
  </tr>
  <tr>
    <td>tesla_supercharger</td>
    <td>Tesla supercharger</td>
    <td>3</td>
  </tr>
</table>

# Charging Levels

<table class="reference levels">
  <tr>
    <th>Level</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Standard house outlet</td>
  </tr>
  <tr>
    <td>2</td>
    <td>240 volt AC charging</td>
  </tr>
  <tr>
    <td>3</td>
    <td>DC fast charging</td>
  </tr>
</table>
