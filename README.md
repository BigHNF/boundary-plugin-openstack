# TrueSight Pulse OpenStack Plugin

This plugin grabs metrics from the openstack node where it is started and parses the data to be able to integrate into boundary. To be able to start, ceilometer should be well configured on the machine and credentials needs to be created.
Additional metrics can be added from the ceilometer by editing the plugin.py and adding or replacing different mapping tuple objects.

## Prerequisites

### Supported OS

|     OS    | Linux | Windows | SmartOS | OS X |
|:----------|:-----:|:-------:|:-------:|:----:|
| Supported |   v   |         |         |      |

- OpenStack version Mitaka
- Ceilometer >= 2.3.0

#### For Centos/RHEL/Ubuntu

- To install OpenStack on centos v7.x/rhel v7.x [see instructions](https://www.rdoproject.org/install/quickstart/)
- To install OpenStack on ubuntu v14.04(trusty) [see instructions](http://docs.openstack.org/developer/devstack/guides/single-machine.html)

#### TrueSight Pulse Meter versions v4.0 or later

- To install new meter go to Settings->Installation or [see instructons|https://help.boundary.com/hc/en-us/sections/200634331-Installation]. 
- To upgrade the meter to the latest version - [see instructons|https://help.boundary.com/hc/en-us/articles/201573102-Upgrading-the-Boundary-Meter].


### Plugin Setup

#### For CentOS 7.x & RHEL 7.x and Ubuntu v14.04(trusty)
To get ceilometer configuration such as host, port and more, goto below file.
```
Default path for ceilometer configuration file is "/etc/ceilometer/ceilometer.conf"
```

     
### Plugin Configuration Fields


|Field Name      |Description                                                             |
|:---------------|:-----------------------------------------------------------------------|
|service_tenant  |The tenant to get into the service panel for OpenStack                  |
|service_endpoint|The endpoint to get into the service panel for OpenStack                |
|service_user    |The user to get into the service panel for OpenStack                    |
|service_timeout |The timeout to get into the service panel for OpenStack                 |
|service_password|The password to get into the service panel for OpenStack                |
|pollInterval    |The polling interval (in milliseconds) to call the openStack collector. Default value for this is 60000 ms, we                        recommend not have smaller value.                                       |

### Metrics Collected


|Metric Name             |Description                                                                |
|:-----------------------|:--------------------------------------------------------------------------|
|OS_CPUUTIL_AVG          |Average openstack CPU utilization on the running node                      |
|OS_CPUUTIL_SUM          |Summary of total openstack CPU utilization                                 |
|OS_CPUUTIL_MIN          |The minimum openstack CPU utilization by VMs running on the node           |
|OS_CPUUTIL_MAX          |The maximum openstack CPU utilization by VMs running on the node           |
|OS_CPU_AVG              |Average CPU time used by the openstack VMs                                 |
|OS_CPU_SUM              |Total CPU time used by the openstack VMs                                   |
|OS_INSTANCE_EVENT_SUM   |Total running instances events                                             |
|OS_INSTANCE_EVENT_MAX   |The maximum number of instances events                                     |
|OS_VOLUME_EVENT_SUM     |Total volumes created events                                               |
|OS_VOLUME_EVENT_AVG     |Average volumes created events                                             |
|OS_IMAGE_SIZE_SUM       |The total amount of space used by the created images                       |
|OS_IMAGE_SIZE_AVG       |Average amount of space used by the created images                         |
|OS_DISK_READ_RATE_SUM   |The total amount of disk read rate on all VMs running on the node          |
|OS_DISK_READ_RATE_AVG   |Average amount of disk read rate on all VMs running on the node            |
|OS_DISK_WRITE_RATE_SUM  |The total amount of disk write rate on all VMs running on the node         |
|OS_DISK_WRITE_RATE_AVG  |Average amount of disk write rate on all VMs running on the node           |
|OS_NETWORK_IN_BYTES_SUM |The total amount of network incoming bytes to all VMs running on the node  |
|OS_NETWORK_IN_BYTES_AVG |Average amount of network incoming bytes to all VMs running on the node    |
|OS_NETWORK_OUT_BYTES_SUM|The total amount of network outgoing bytes from all VMs running on the node|
|OS_NETWORK_OUT_BYTES_AVG|Average amount of network outgoing bytes from all VMs running on the node  |
|OS_MEMORY_RESIDENT_SUM  |The resident memory sum consumed by the VMs from the Physical Host         |
|OS_MEMORY_RESIDENT_AVG  |The resident memory avg consumed by the VMs from the Physical Host         |
