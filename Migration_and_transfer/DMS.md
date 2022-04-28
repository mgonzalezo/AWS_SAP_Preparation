# AWS DMS migration task & General Concepts on Migration:

- Create a source endpoint, a target endpoint, and a replication instance before you create a migration task. 
- Choose a migration method:
  - Migrating data to the target database–creates files or tables in the target database and automatically defines the metadata that is required at the target
  - Capturing changes during migration–This process captures changes to the source database that occur while the data is being migrated from the source to the target. 
  - Replicating only data changes on the source database.
- reads the recovery log file of the source database management system (DBMS) and groups together the entries for each transaction

## General Information

<p align="left">
  <img alt="alt text" src="migrar1.png" width="400">
  <br>
    <em>Migration Paths. Source: https://courses.datacumulus.com//</em>
</p>
</n>
</n>
<p align="left">
  <img alt="alt text" src="migrar2.png" width="400">
  <br>
    <em>Rehosting and Replataforming Paths. Source: https://courses.datacumulus.com/</em>
</p>
</n>
</n>
<p align="left">
  <img alt="alt text" src="migrar3.png" width="400">
  <br>
    <em>Repurchase and Refactoring Paths. Source: https://courses.datacumulus.com/</em>
</p>
</n>
</n>
<p align="left">
  <img alt="alt text" src="migrar4.png" width="400">
  <br>
    <em>Retire and Retain Paths. Source: https://courses.datacumulus.com/</em>
</p>
</n>
</n>
<p align="center">
  <img alt="alt text" src="migrar5.png" width="600">
  <br>
    <em>RTO & RPO Table. Source: https://courses.datacumulus.com/</em>
</p>
</n>
</n>
<p align="center">
  <img alt="alt text" src="migrar6.png" width="700">
  <br>
    <em>AWS SMS. Source: https://courses.datacumulus.com/</em>
</p>
</n>
</n>