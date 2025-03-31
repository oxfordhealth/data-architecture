# Macro Architecture

The macro architecture shows a high level flow of data from source systems via the main streams:

- **Business Intelligence** - Producing the TOBI platform and automated reports/dashboards.
- **Clinical Systems & Integration** - Ensuring data consistency between systems and producing the Shared Care Record.
- **Performance & Information** - Providing on demand reporting and contractual reporting, utilising and supplementing BI data.
- **Research & Development** - Anonymise and analyse data through Machine Learning models for research purposes.

## Macro Diagram

![](res/drawio/MacroArchitecture.drawio)

_Note: Diagram may take a minute to load._

# Overall Detailed Architecture

## Overall Diagram

![](res/drawio/Architecture.drawio)

_Note: Diagram may take a minute to load._

# Future Architecture Aiming For

The aim is to consolidate all source/raw data access to a single point, the **raw lakehouse** - this is a data lakehouse that will store the data as [delta](https://delta.io/) as well as a SQL endpoint that allows the enduser to connect to via tools such as SSMS or using libraries such as [SQLAlchemy](https://www.sqlalchemy.org/). It will also serve as the point of access for the relevent data teams within the trust:

- Business Intelligence
- Clinical Systems & Integration
- Performance & Information
- Research & Development

## Future Diagram

![](res/drawio/FutureArchitecture.drawio)

_Note: Diagram may take a minute to load._

## Data Sharing

If we want to share data outside of the trust, there are a couple of avenues that can be taken

- Raw data can be shared from the **raw lakehouse**, as this is just a copy of the source row level data.
- Data sharing as part of the Integration team remains the same.
- Data conformed across multiple source systems & has Business Rules (but is still row-level) applied can be shared from the Business Layer, much like the current National Submissions.
- Aggregated reporting data can be shared from the **Oxford Health Data Warehouse** either via PowerBI reports as a self service report, or via the Performance & Information team.

*[SSMS]: SQL Server Management Studio