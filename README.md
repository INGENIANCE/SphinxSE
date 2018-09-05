SphinxSE
=========

This role can be used to deploy a containerized SphinxSE.

Requirements
------------

1) A non-containerized MySQL database must be running and accessible according to the parameters passed to the role for the SphinxSE container to run.  
2) A Sphinx.conf to be used.

Role Variables
--------------

Variable name: variable type - description

sphinxse_ansible_user_id: String - Linux user used by Ansible to create SphinxSE folder structure.  
sphinxse_docker_registry_path : String - Path to the Docker registry where to find SphinxSE image.  
sphinxse_docker_repo_path : String - Path to the Docker SphinxSE image repository.  
sphinxse_path_config : String - Path to the SphinxSE configuration file.  
sphinxse_path_volumes : String - Path to the SphinxSE volumes.  
sphinxse_docker_registry_username : String - Username credential of the Docker registry where to find SphinxSE image.  
sphinxse_docker_registry_password : String - Password credential of the Docker registry where to find SphinxSE image.

Dependencies
------------

None

Example Playbook
----------------
The following playbook deploys a SphinxSE container to a target server :

    ---
    - name: Deploy SphinxSE to target server
      hosts: "host_name"
      remote_user: "remote_user"
      vars:
        sphinxse_ansible_user_id: "ubuntu"
        sphinxse_docker_registry_path : "/path/of/registry"
        sphinxse_docker_repo_path : "registry.gitlab.com/test_group/docker-images"
        sphinxse_path_config : "/path/to/config"
        sphinxse_path_volumes : "/path/to/volume"
        sphinxse_docker_registry_username : "registry_username"
        sphinxse_docker_registry_password : "RegistryPWD"
      roles:
        - sphinxse

License
-------

GNU General Public License

Author Information
------------------

email: afontaine@ingeniance.fr
