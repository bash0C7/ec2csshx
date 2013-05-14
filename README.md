# ec2cssh

Cluster SSH connect to pattern mached hosts (Connected by cssh) (Hosts in ssh config written by ec2ssh)

## Installation

Add this line to your application's Gemfile:

    gem 'ec2cssh'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install ec2cssh

## Prepair

- install ec2ssh & run ec2ssh init
- install cssh

## Usage

ex)

````sh
$ ec2cssh connect '\S+-production' 
````

run 'ec2ssh update' command and grep Host name  by Server name pattern parameter.
finaly connect hosts using 'cssh' command


### Parameters

#### 1. Server name pattern (required)

ex) 

'ec2ssh update' result
````
### EC2SSH BEGIN ###
# Generated by ec2ssh http://github.com/mirakui/ec2ssh
# DO NOT edit this block!
# Updated Sun Dec 05 00:00:14 +0900 2010

# section: default
Host app-server-1.us-west-1
  HostName ec2-xxx-xxx-xxx-xxx.us-west-1.compute.amazonaws.com
Host app-server-2.us-west-1
  HostName ec2-xxx-xxx-xxx-xxx.us-west-1.compute.amazonaws.com
Host db-server-1.ap-southeast-1
  HostName ec2-xxx-xxx-xxx-xxx.ap-southeast-1.compute.amazonaws.com
### EC2SSH END ###
````

Server name pattern: 'app-server.*' => connect to app-server-1.us-west-1 and app-server-2.us-west-1

### Options(optional)

#### 1. --ec2ssh_update : ec2ssh update command

ex) --ec2ssh_update 'ec2ssh update --aws-key my_key1'

default 'ec2ssh update'

#### 2. --cssh : cssh command

ex) --cssh 'cssh --config /path/to/configfile'
ex) --cssh 'csshx'

default 'cssh'

#### 3. --port

SSH Port No

ex) --port '9999'

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
