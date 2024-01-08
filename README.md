# Lilyhosting OpenAPI (The Proxmox API)

Self Hosting: To use this library, You would first get your proxmox user token, And now you can use it to instantiate a `LilyHostingAPI` object

Using an Hosting Provider (Lilyhosting. Etc): Then you would ask your provider for an API User Token, Example Lilyhosting gives you it for free for the last 3 days of usage untill you need to pay 0.50$/per an request. And now you can use it to instantiate a `LilyHostingAPI` object:


Example Usage:
```python
from lilyhosting.api import LilyHostingAPI

api = LilyHostingAPI("https://example.com:8006", "YOUR_API_TOKEN")
```

You can then use the `api` object to interact with the Proxmox API. For example, to get a list of all nodes in the cluster, you would do the following:

```python
nodes = api.get_nodes()
```

To get a list of all VMs in the cluster, you would do the following:

```python
vms = api.get_vms()
```

To get a specific VM by its ID, you would do the following:

```python
vm = api.get_vm("100")
```

To start a VM, you would do the following:

```python
api.start_vm("100")
```

To stop a VM, you would do the following:

```python
api.stop_vm("100")
```

To reboot a VM, you would do the following:

```python
api.reboot_vm("100")
```

To create a new VM, you would do the following:

```python
vm = api.create_vm("new-vm", "template-1", 10, 1024, 2)
```
