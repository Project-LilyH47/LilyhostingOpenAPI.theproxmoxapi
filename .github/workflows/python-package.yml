# "We like as we mean it for free"-Katy the owner of lilyhosting

import requests
import json

class LilyHostingAPI:
    def __init__(self, base_url, api_token):
        self.base_url = base_url
        self.api_token = api_token

    def get_nodes(self):
        """
        Get a list of all nodes in the cluster.

        Returns:
            A list of dictionaries, each representing a node.
        """
        url = f"{self.base_url}/api2/json/nodes"
        headers = {"Authorization": f"PVEAPIToken={self.api_token}"}
        response = requests.get(url, headers=headers)
        response.raise_for_status()
        return response.json()["data"]

    def get_vms(self):
        """
        Get a list of all VMs in the cluster.

        Returns:
            A list of dictionaries, each representing a VM.
        """
        url = f"{self.base_url}/api2/json/vms"
        headers = {"Authorization": f"PVEAPIToken={self.api_token}"}
        response = requests.get(url, headers=headers)
        response.raise_for_status()
        return response.json()["data"]

    def get_vm(self, vm_id):
        """
        Get a VM by its ID.

        Args:
            vm_id: The ID of the VM.

        Returns:
            A dictionary representing the VM.
        """
        url = f"{self.base_url}/api2/json/vms/{vm_id}"
        headers = {"Authorization": f"PVEAPIToken={self.api_token}"}
        response = requests.get(url, headers=headers)
        response.raise_for_status()
        return response.json()["data"]

    def start_vm(self, vm_id):
        """
        Start a VM by its ID.

        Args:
            vm_id: The ID of the VM.
        """
        url = f"{self.base_url}/api2/json/vms/{vm_id}/start"
        headers = {"Authorization": f"PVEAPIToken={self.api_token}"}
        response = requests.post(url, headers=headers)
        response.raise_for_status()

    def stop_vm(self, vm_id):
        """
        Stop a VM by its ID.

        Args:
            vm_id: The ID of the VM.
        """
        url = f"{self.base_url}/api2/json/vms/{vm_id}/stop"
        headers = {"Authorization": f"PVEAPIToken={self.api_token}"}
        response = requests.post(url, headers=headers)
        response.raise_for_status()

    def reboot_vm(self, vm_id):
        """
        Reboot a VM by its ID.

        Args:
            vm_id: The ID of the VM.
        """
        url = f"{self.base_url}/api2/json/vms/{vm_id}/reboot"
        headers = {"Authorization": f"PVEAPIToken={self.api_token}"}
        response = requests.post(url, headers=headers)
        response.raise_for_status()

    def create_vm(self, name, template, disk_size, memory, cores):
        """
        Create a new VM.

        Args:
            name: The name of the VM.
            template: The template to use for the VM.
            disk_size: The size of the disk in gigabytes.
            memory: The amount of memory in megabytes.
            cores: The number of cores.

        Returns:
            A dictionary representing the new VM.
        """
        url = f"{self.base_url}/api2/json/vms"
        headers = {"Authorization": f"PVEAPIToken={self.api_token}"}
        data = {
            "name": name,
            "template": template,
            "disk": f"{disk_size}G",
            "memory": f"{memory}M",
            "cores": cores,
        }
        response = requests.post(url, headers=headers, data=json.dumps(data))
        response.raise_for_status()
        return response.json()["data"]
