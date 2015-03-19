# Boundary Openstack Plugin

This plugin grabs metrics from the openstack node where it is started and parses the data to be able to integrate into boundary. To be able to start, ceilometer should be well configured on the machine and credentials needs to be created.
Additional metrics can be added from the ceilometer by editing the plugin.py and adding or replacing different mapping tuple objects.

## Prerequisites

### Supported OS

|     OS    | Linux | Windows | SmartOS | OS X |
|:----------|:-----:|:-------:|:-------:|:----:|
| Supported |   v   |         |         |      |

#### Openstack
- Version Juno+
- Ceilometer > 0

#### Boundary Meter Versions V4.0 Or Greater

To get the new meter:

    curl -fsS \
        -d "{\"token\":\"<your API token here>\"}" \
        -H "Content-Type: application/json" \
        "https://meter.boundary.com/setup_meter" > setup_meter.sh
    chmod +x setup_meter.sh
    ./setup_meter.sh

|  Runtime | node.js | Python | Java |
|:---------|:-------:|:------:|:----:|
| Required |         |    +   |      |

- [How to install Python?](https://help.boundary.com/hc/articles/202270132)
- Python libraries: ceilometerclient (this is automatically installed if ceilometer is installed)

### Plugin Setup

None

### Plugin Configuration Fields

#### For All Versions

|Field Name      |Description                                                |
|:---------------|:----------------------------------------------------------|
|service_tenant  |The tenant to get into the service panel for OpenStack     |
|service_endpoint|The endpoint to get into the service panel for OpenStack   |
|service_user    |The user to get into the service panel for OpenStack       |
|service_timeout |The timeout to get into the service panel for OpenStack    |
|service_password|The password to get into the service panel for OpenStack   |

### Metrics Collected

#### For All Versions

|Metric Name             |Description                       |
|:-----------------------|:---------------------------------|
|OS_CPUUTIL_AVG          |                                  |
|OS_CPUUTIL_SUM          |                                  |
|OS_CPUUTIL_MIN          |                                  |
|OS_CPUUTIL_MAX          |                                  |
|OS_CPU_AVG              |                                  |
|OS_CPU_SUM              |                                  |
|OS_INSTANCE_SUM         |                                  |
|OS_INSTANCE_MAX         |                                  |
|OS_MEMORY_SUM           |                                  |
|OS_MEMORY_AVG           |                                  |
|OS_MEMORY_USAGE_SUM     |                                  |
|OS_MEMORY_USAGE_SUM     |                                  |
|OS_VOLUME_SUM           |                                  |
|OS_VOLUME_AVG           |                                  |
|OS_IMAGE_SIZE_SUM       |                                  |
|OS_IMAGE_SIZE_AVG       |                                  |
|OS_DISK_READ_RATE_SUM   |                                  |
|OS_DISK_READ_RATE_AVG   |                                  |
|OS_NETWORK_IN_BYTES_SUM |                                  |
|OS_NETWORK_IN_BYTES_AVG |                                  |
|OS_NETWORK_OUT_BYTES_SUM|                                  |
|OS_NETWORK_OUT_BYTES_AVG|                                  |
