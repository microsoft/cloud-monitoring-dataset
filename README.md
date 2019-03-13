# Cloud Monitoring Dataset

The Cloud Monitoring Dataset is a set of real-world time series derived from Microsoft service and client telemetry signals. The data set contains anomalous patterns manually labeled by experts. The dataset is used for development, evaluation and improvement of anomaly detection algorithms in Microsoft's cloud monitoring tools.

## Data Domains

The Cloud Monitoring Dataset consists of 67 real-world time series in 8 domains ranging from online services to Windows PCs.  All data was collected from production Microsoft service telemetry.

The domains for the datasets are:

* Store purchase counts by client type
* Database query rates by individual machines in cluster
* Database query rates by application context
* Incoming service API query rate
* Outgoing service API latency
* Windows application crash rate by OS version and country
* Web app query rates to service API

Data granularity is per minute or per hour depending on the time series.

The dataset is labeled with anomaly time points using domain knowledge elicited from experts in each area. Anomalies are labeled either by the domain experts, or with the assitance of domain experts reviewing the time series data.  We developed a labeling web tool as part of this project.

Our data includes some time series that contain no anomaly labels.  These are included to test algorithms on their ability to avoid false positives.

## Dataset Format

Each dataset time series is contained in a CSV format file with 3 fields.

| Field     |      Description      |  Example |
|-----------|:----------------------|----------|
| TimeStamp | This is an ISO 8601 compliant date value.<br> It can be enclosed in double quotes.<br>Time zone designation is optional. | "2018-07-03 14:00:00" |
| Value     | Integer or float value for the time series metric for the time stamp.   |   3429.0003 |
| Label     | Designates whether time stamp is an anomaly.<br>1 means anomaly, 0 means not anomaly. |   0 |

The time series CSV file has a header with the field names.  A sample excerpt is the following.

    TimeStamp,Value,Label
    "2018-07-03 14:00:00",1,0
    "2018-07-03 15:00:00",0,0
    "2018-07-03 16:00:00",1,1
    "2018-07-03 17:00:00",1,0

## Annotation

Each time series CSV file is accompanied by a JSON file with a description of the time series.  The JSON file follows the CSV on the Web (CSVW) standard.
