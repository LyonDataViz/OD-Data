# OD-Data
Origin-destination datasets with a method


## Format of the [dataset.json](dataset.json) file

Just a list of URLs for the data.json files.

## Format of the data.csv file

It's a classical CSV file, preferably with commas (`,`) as separator.

One line represents one O/D trajectory. The column names are referenced in the data.json file.

## Format of the data.json file

Complete example:

```{javascript}
{
  "file": "path/to/data.csv",
  "name": "Title of the dataset",
  "header": 1,
  "separator": ",",
  "meta": {
    "start_date": "start_time",
    "end_date": "end_time",
    "start_latitude": "start_station_latitude",
    "start_longitude": "start_station_longitude",
    "end_latitude": "end_station_latitude",
    "end_longitude": "end_station_longitude",
    "group_1": "start_city",
    "group_2": "end_city"
  },
  "attributes": [
    {
      "name": "start_station_id",
      "type": "quantitative"
    },

  ],
  "author": "Liu Liqun",
  "description": "FordGoBike in US (Three cities)",
  "source": "https://www.fordgobike.com/system-data"
}
```

The `file` attribute indicates the URL of the CSV file. An alternative is to use `file_iocane` for a [iocane-encrypted](https://beta.observablehq.com/@fil/hello-iocane) URL.

The `name` attribute is the title of the dataset.

The `meta` object describes the well-known data fields: origin and destination's coordinates, dates, groups…

The `attributes` object describes the secondary fields: duration, price, age… that will be used to color maps or for statistical analysis.

*Dates* must be formatted in a way that moment.js can parse. It is possible to specify the date format as a `dateformat` attribute.

*Separator* is, by default, the comma ",". It is passed to d3.dsv.

*Header* is unused (yet).

*Author* is the author or maintainer of the dataset.

*Description* describes the dataset.

*Source* is the source of the dataset.


## Usage

An [Observable notebook](https://beta.observablehq.com/) will show how to use this set of datasets in a unified manner.