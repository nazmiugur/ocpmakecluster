# Execution of playbooks:
# step1-3 binary download, setting path and creating inventory config according to clusterdetails.yml
# step4 creating inventory file of the cluster according to clusterdetails.yml. "firstIP" is given to bootstrap. Then comes master and workers in consecutive order. 2 DNS address should be supplied. Otherwise nic configuration template files that are producing shall script must be modified.
# step5  ISO files are created with embedded ignition files under /tmp folder with cluster subdomain prefix
# step6 assumes existence of RH IPA server as DNS. If not corresponding DNS configuration should be supplied prior to installation
# step7 creating nodes at vmware. Vcenter details should be supplied in vcenterdetails.yml file.
# step8 corresponding Loadbalancer configuration for haproxy is created. In other words it create haproxy.cfg in folder that playbook is run


# ansible-playbook step1-PrerequisiteFiles.yml 
# ansible-playbook step2-ManifestAndIgnitionConfigs.yml 
# ansible-playbook step3-InventoryConfig.yml 
# ansible-playbook step4_create_inv_custom.yml -i inventory.yml 
# ansible-playbook step5-ISOfiles.yml -i inventory.yml 
# ansible-playbook step7-createnodes.yml -i inventory.yml 
# ansible-playbook step8-createHaProxyCfg.yml -i inventory.yml 

