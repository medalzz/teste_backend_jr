
# Reporting Channel RESTful API

A reporting channel API project made for studying purposes, following RESTful principles.

Made with PHP and [Flight](https://github.com/mikecao/flight) routing system.

## API Reference

#### Get all items

```
  GET /registros
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `deleted` | `bool`   |  Removed reports           |
| `type`    | `string` |  Report category           |
| `order`   | `string` |  Order results by column   |
|`order_dir`| `string` |  ASC or DESC               |
| `limit`   | `int`    |Max nº of results / starting index|
|`offset`| `int` |Max nº of results when `limit` is passed|


#### Create item

```
  POST /registros
```

|Parameter|Type|Description           |
| :------ | :------- | :---------------------------- |
| `deleted` | `bool` | **Required** Removed reports  |
| `type`    |`string`| **Required** Report category  |
| `message` |`string`| **Required** Report message   |
|`is_identified`|`bool`| **Required** Anonymous report|


#### Get item

```
  GET /registros/${id}
```

|Parameter|Type|Description           |
|:--------|:---| :--------------------- |
| `id` | `int` | **Required**. ID of item to fetch |


#### Update item

```
  PUT|PATCH /registros/${id}
```

|Parameter|Type|Description           |
| :------ | :------- | :---------------------------- |
| `id` | `int` | **Required**. ID of item to fetch |
| `deleted` | `bool` | Removed reports  |
| `type`    |`string`| Report category  |
| `message` |`string`| Report message   |
|`is_identified`|`bool`| Anonymous report|

**Note:** At least one of the previous parameters must be passed

#### Delete item

```
  DELETE /registros/${id}
```

|Parameter|Type|Description           |
|:--------|:---| :--------------------- |
| `id` | `int` | **Required**. ID of item to fetch |

## Creating development environment

1- Clone the repo.

2- Start the container on port 8000:

```bash
  docker compose up -d
```