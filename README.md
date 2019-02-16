# Cloud Monitoring Dataset


The Cloud Monitoring Dataset is a set of real-world time series from Microsoft labeled with anomalies.  The dataset is used for development of anomaly detection algorithms in Microsoft's monitoring tools.

The Cloud Monitoring Datset consists of 67 real-world time series in 8 domains spanning online services to Windows PCs.  All data was collected from production Microsoft service telemetry using Microsoft's Asimov Data Platform that was originally created for Xbox and Windows.

MS TIME data covers:

* Service API request rates
* Service API response latency
* Application crash rates
* Product purchase rates

Data granularity is either per minute or per hour depending on the time series.

MS TIME is available on Github under MIT License for public use.  

The domains for MS TIME include:

* Store purchase counts by distinct client type
* MongoDB query rates by individual machines in cluster
* MongoDB query rates by application context
* Incoming API query rate
* Outgoing API latency
* Windows application crash rate by OS version and country
* Web app query rate to cloud API

MS TIME data is labeled using domain knowledge elicited from experts in each area. Anomalies are labeled either by domain experts, or with the assitance of domain experts reviewing the time series data.  We developed a labeling web tool as part of this projec.

MS TIME includes time series that contain no anomaly labels.  These are included to test algorithms on their ability to avoid false positives.

The format of the dataset is described on github.
