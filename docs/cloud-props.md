## Cloud properties

### AZs

Currently the CPI does not support any cloud properties for AZs.

Example:

```yaml
azs:
- name: z1
```

### Network

Schema for `cloud_properties` section used by network subnet:

* **name** [String, required]: Name of the network. Example: `vboxnet0`. Default: `vboxnet0`.
* **type** [String, optional]: Type of the network. See [`VBoxManage modifyvm` networking settings](https://www.virtualbox.org/manual/ch08.html#idp46691722135120) for valid values. Example: `hostonly`. Default: `hostonly`.

Example of manual network:

```yaml
networks:
- name: private
  type: manual
  subnets:
  - range:   192.168.50.0/24
    gateway: 192.168.50.1
    dns:     [192.168.50.1]
    cloud_properties:
      name: vboxnet0
```

### VM

Schema for `cloud_properties` section:

* **cpus** [Integer, optional]: Number of CPUs. Example: `1`. Default: `1`.
* **memory** [Integer, optional]: RAM in megabytes. Example: `1024`. Default: `512`.
* **ephemeral_disk** [Integer, optional]: Ephemeral disk size in megabytes. Example: `10240`. Default: `5000`.
* **paravirtprovider** [String, optional]: Paravirtual provider type. See [`VBoxManage modifyvm` general settings](https://www.virtualbox.org/manual/ch08.html#idp46691713664256) for valid values. Default: `minimal`.

Example of a VM type:

```yaml
vm_types:
- name: default
  cloud_properties:
    cpus: 2
	  memory: 2_048
	  ephemeral_disk: 4_096
	  paravirtprovider: minimal
```

### Disk

Currently the CPI does not support any cloud properties for disks.
