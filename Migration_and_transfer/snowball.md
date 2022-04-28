# AWS Snowball Edge

- The following list is ordered from largest to smallest positive impact on performance when exporting files to Snowball:
  - Perform multiple write operations at one time (run each command from multiple terminal windows on a computer)
  - Transfer small files in batches (batch files together in a single archive.)
  - Write from multiple computers (AWS Snowball Edge device can be connected to many computers on a network)
  - Don’t perform other operations on files during transfer (Renaming files during transfer, changing their metadata, or writing data to the files during a copy operation has a negative impact on transfer performance.)
  - Reduce local network use (reducing other local network traffic between the AWS Snowball Edge device,)
- Eliminate unnecessary hops (set up your AWS Snowball Edge device, your data source, and the computer running the terminal connection between them )