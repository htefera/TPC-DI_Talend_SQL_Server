## TPC-DI using Talend and SQL Server

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
