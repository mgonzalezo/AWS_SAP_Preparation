# AWS - OpsWorks

Let's you use Chef and Puppet to automate how servers are configured, deployed, and managed across
your Amazon EC2 instances or on-premises compute environments. It can’t deploy AWS Lambda applications.

AWS OpsWorks Stacks automatically installs the latest updates during setup, after an instance finishes booting. AWS OpsWorks Stacks does not automatically install updates after an instance is online, to avoid interruptions such as restarting application servers. Instead, you manage updates to your online instances yourself, so you can minimize any disruptions.

On Linux-based instances in Chef 11.10 or older stacks, run the Update Dependencies stack command, which installs the current set of security patches and other updates on the specified instances.