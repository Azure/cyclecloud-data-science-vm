# Single Data Science VM #

This project demonstrates launching the Microsoft Azure Data Science VM as a standalone node.
The Data Science VM may be used as the base image in most CycleCloud clusters.


## License ##

To use the Microsoft DataScience VM, you must first accept the license agreement.
The simplest way to do so is to run the following Azure CLI commands:

``` bash
    az vm image accept-terms --publisher microsoft-ads --offer linux-data-science-vm --plan linuxdsvm
    az vm image accept-terms --publisher microsoft-ads --offer linux-data-science-vm-ubuntu --plan linuxdsvmubuntu
    az vm image accept-terms --publisher microsoft-ads --offer windows-data-science-vm --plan windows2016
```


## Pre-Requisites ##


This sample requires the following:

  1. CycleCloud must be installed and running.

     a. If this is not the case, see the CycleCloud QuickStart Guide for
        assistance.

  2. The CycleCloud CLI must be installed and configured for use.

  3. You must have access to log in to CycleCloud.

  4. You must have access to upload data and launch instances in your chosen
     Cloud Provider account.

  5. You must have access to a configured CycleCloud "Locker" for Project Storage
     (Cluster-Init and Chef).

  6. Optional: To use the `cyclecloud project upload <locker>` command, you must
     have a Pogo configuration file set up with write-access to your locker.

     a. You may use your preferred tool to interact with your storage "Locker"
        instead.


## Configuring the Project ##


The first step is to configure the project for use with your storage locker:

  1. Open a terminal session with the CycleCloud CLI enabled.

  2. Switch to the data-science-vm project directory.


## Deploying the Project ##


To upload the project (including any local changes) to your target locker, run the
`cyclecloud project upload` command from the project directory.  The expected output looks like
this:

``` bash

   $ cyclecloud project upload my_locker
   Sync completed!

```


**IMPORTANT**

For the upload to succeed, you must have a valid Pogo configuration for your target Locker.


## Importing the Cluster Template ##


To import the cluster:

 1. Open a terminal session with the CycleCloud CLI enabled.

 2. Switch to the data-science-vm project directory.

 3. Run ``cyclecloud import_template Data-Science-VM -f templates/data-science-vm.txt``.
    The expected output looks like this:
    
    ``` bash
    
    $ cyclecloud import_template Data-Science-VM -f templates/data-science-vm.txt --force
    Importing template Data-Science-VM....
    ----------------------------
    Data-Science-VM : *template*
    ----------------------------
    Keypair:
    Cluster nodes:
	dsvm: off
    Total nodes: 1
    ```

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

