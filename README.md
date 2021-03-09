nxos_upload ansible playbooks

Tool is used to upload nxos image file on the device.

Tool does NOT upgrade the device after upload.

Modules

nxos_upload_main.yml : This is the main playbook that calls on all the other playbooks.

images.yml : Editable/Dynamic variables file. See below on "how to use"

nxos_upload_to_device.yml : Contains tasks to upload the images found in the images.yml file.Different checks will be done on the image before upload takes place.

nxos_impact_checks.yml : Contains tasks that perfoms nxos image impact analysis on the device.


Authors
Allan Maseghe
