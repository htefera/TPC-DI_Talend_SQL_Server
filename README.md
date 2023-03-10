# TPC-DI using Talend Data Integration and SQL Server

### Introduction

TPC Benchmark™ DI (TPC-DI) is a performance test of tools that move and integrate data
between various systems. Data Integration (DI) tools are available from a number of vendors,
but until now there has been no standard way to compare them. Such tools have also been
referred to as Extract, Transform and Load (ETL) tools at times. The benchmark workload
manipulates a defined volume of data, preparing the data for use in a Data Warehouse. The
benchmark model includes data representing an extract from an On-Line Transaction
Processing (OTLP) system being transformed along with data from ancillary data sources
(including tabular and hierarchical structures), and loaded into a Data Warehouse. The source
and destination schemas, data transformations and implementation rules have been designed
to be broadly representative of modern data integration requirements <br> 



The benchmark exercises a breadth of system components associated with DI environments,
which are characterized by:
* The manipulation and loading of large volumes of data
* A mixture of transformation types including error checking, surrogate key lookups, data type conversions, aggregation operations, data updates, etc.
* Historical loading and incremental updates of a destination Data Warehouse using the transformed data 
* Consistency requirements ensuring that the integration process results in reliable and accurate data
* Multiple data sources having different formats
* Multiple data tables with varied data types, attributes and inter-table relationships.


The TPC-DI operations are modeled as follows:
* Source data is generated using TPC provided code. The data is provided in flat files similar to the output of many extraction tools
* Transformation of the data begins with the System Under Test (SUT) reading the Source Data
* The transformations validate the Source Data and properly structure the data for loading into a Data Warehouse
* The process concludes when all Source Data has been transformed and is available in the Data Warehouse

## Objective 
The data model for the TPC-DI benchmark represents a retail brokerage. The focus of the TPC-DI benchmark is on the processes involved in transforming data from an OLTP environment and other relevant sources such as OLAP systems, and populating a data warehouse <br>

The benchmark defines:
* Multiple data source schemas and file formats
* The Source Data generation requirements and data placement
* The destination data warehouse schema
* A collection of transformation rules describing how the destination data warehouse is populated with data from the data sources
* Specific rules for the Historical Load and for Incremental Updates
* Requirements for the execution, timing and reporting of the metrics
* Methodology for the verification of the resulting data in the data warehouse
* Disclosure and auditing requirements for the implementation and execution of the workload.

## Benchmark Overview
The data model for the TPC-DI benchmark represents a retail brokerage. OLTP data is combined with data from additional sources to create the data warehouse

![](Tpc_di.png)

There are multiple tables in the OLTP system that are extracted into a staging area; the OLTP system contains data on customers, accounts, brokers, securities, trade details, account balances, market information, and so on. Extracts from these tables are represented as flat
files in the Staging Area.<br>

In the Historical Load phase of the benchmark, two other sources are used to provide information that is not directly available from the OLTP system. Financial information about companies and securities is obtained from a financial newswire (FINWIRE) service that has been
archived over an extended period of time.

## Implementation
We modeled and implemented the TPC-DI benchmark using Talend DI and SQL Server. Talend Open Studio for Data Integration is a well positioned as one of the leaders in the market for ETL, as stated by Gartner ir their 2019 Gartner Magic Quadrant for Data Integration Tools


For modeling the database, we use the data warehouse graphical depiction provided by the TPC-DI specifications document <br>
![](tpcdIdw.png)



