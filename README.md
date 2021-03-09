nxos_upload ansible playbooks
Tool is used to upload nxos image file on the device.

Tool does NOT upgrade the device after upload.

Modules
nxos_upload_main.yml : This is the main playbook that calls on all the other playbooks.
images.yml : Editable/Dynamic variables file. See below on "how to use"
nxos_upload_to_device.yml : Contains tasks to upload the images found in the images.yml file.Different checks will be done on the image before upload takes place.
nxos_impact_checks.yml : Contains tasks that perfoms nxos image impact analysis on the device.
Requirements
Ansible 2.7.5 and above on the controlling machine.
The remote device must be running Cisco NXOS
The remote device must support SSH
How to run
STEP 1: Ensure you have the image available for the controller machine.

STEP 2: Edit the images.yml file. NB: Must remain in yml format. NB: If no kickstart image is used, key it as 'none' Example of images.yml file:

images.yml
3 dashes MUST be there.It indicates this is a .yml file
system_image: kickstart_image:

STEP 3: Run the tool, calling on the main fail $ ansible-playbook nxos_upload_main.yml

Variables
The tool expects the following variables:

system_image : NXOS System image file kickstart_image : NXOS kickstart image file('none' if not in use)

hosts : Inventory of devices

Authors
Allan Maseghe
