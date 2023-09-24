# taw

## A small tool to ease daily work with AWS EC2 instances
This tool intends to be a high-level layer over `aws-cli` and its functionalities are oriented to my most common micro tasks involving EC2 instances like getting info about instances, starting, stopping, or changing instance type.    

### Requirements
As I mentioned above, `taw` uses under the hood `aws-cli`, so you need to install and configure properly `aws-cli`. Other dependencies you need to install are `fzf`, `awk` and `jq`.

### Installation
Install `taw` is as easy as run `./install` and then you can use it directly from your terminal. Open a new terminal and type `taw version` or `taw -v` to check if it is correctly installed.

### Basic usage
First of all, you need to run the command `taw fetch` to download the list of all of the EC2 instances you have access and also all the EC2 available types. Notice that, anytime you have access to new EC2 instances, you need to run again `taw fetch` to update the local list of available instances. In general, you use `taw fetch` as the first command immediately after installation and every time you need to update your available EC2 instances.

`taw list`: this command shows a list of all of the EC2 instances you have access to. Then, you can select an instance using the fuzzy finder capabilities to get more detailed information about the instance.

`taw start`: use this commmand to start an EC2 instance using the fuzzy finder to select it. This command also updates the host name in the ssh config file using the instance public DNS. 

`taw stop`: use this command to stop an EC2 instance using the fuzzy finder to select it. 

`taw type`: use this command to change the type of and EC2 instance using the fuzzy finder to select both the instnace and the type.

`taw help`: use this command to show the command line help.