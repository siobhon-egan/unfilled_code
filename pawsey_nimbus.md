# Code for Pawsey Nimbus instance

Useful bits of links and code related to Pawsey Nimbus instance

[Pawsey GitHub landing page](https://pawseysc.github.io/training.html)

[Using Nimbus](https://pawseysc.github.io/using-nimbus/)

[The Unix Shell: Pawsey Edition](https://pawseysc.github.io/shell-hpc/)

[Nimbus Documentation Land Page](https://support.pawsey.org.au/documentation/display/US/Nimbus+Documentation+Landing+Page)

## Volume storage and disk space

[Pawsey info on attaching volumes](https://pawseysc.github.io/using-nimbus/07-volume-storage/index.html)

Get info on data storage

```
df -h | grep vda
```
> /dev/vda1        39G  3.6G   36G  10% /

Get info on size of files in directory
```
ls -sh
```


## Transfering data

[Pawsey info](https://pawseysc.github.io/using-nimbus/08-moving-data/index.html)

**1. From local computer to instance**

Transfer a file from local repo to Pawsey instance

`scp -i name_of_your_key.pem local_file_path login_name@###.###.###.###: instance_file_path`

Transfer a directory from local repo to Pawsey instance

`scp -r -C -i ~/.ssh/segan-phd.pem Documents/Uni/PhD/Projects/7.wildlife_ngs_metabarcoding/NGS_data/AGRF_CAGRF20093816_JD8WJ-test/raw_data/ ubuntu@146.118.66.39:`

example

`scp -r -i ~/.ssh/segan-phd.pem Downloads/AGRF_CAGRF20093816_JDC6Y ubuntu@146.118.66.39:`

**2. From instance to local computer**

Transfer file from nimbus to local computer

`scp -i name_of_your_key.pem login_name@###.###.###.###:instance_file_path/file.txt .`

Transfer directory from nimbus instance (directory called `analysis_done`) to local computer (directory `current directory`)

`scp -r -C -i ~/.ssh/segan-phd.pem ubuntu@146.118.66.39:/analysis_done/ .`

Transfer directory from nimbus instance (directory called `analysis_done`) to local computer (directory `nimbus_output`)

`scp -r -C -i ~/.ssh/segan-phd.pem ubuntu@146.118.66.39:/analysis_done/ nimbus_output/`


## Software

This command updates the local database of available software packages for Ubuntu. At the end of the command, it tells you how many packages can be upgraded. To see them run the following command: `apt list --upgradable`.

The second command you need is `sudo apt upgrade`

Search for packages (Ubuntu)

To search for packages use
`apt-cache search keyword`

To list already installed packages:
`dpkg -l`

To check if a specific package is installed:
`dpkg -l | grep package_name`

Install packages available within your selected linux distribution software package repository:
`sudo apt-get install`

Update all installed packages (from the repository):
`sudo apt-get update`
