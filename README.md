Website Deployer
=========

This role pulls ASP.NET 4.8 executables from a repository, creates a container image and uploads it to a configured image repository. It also contains tasks for creating a namespace in a Kubernetes cluster, pulling the image and creating a container from the image. It also creates associated network components to make the website available for users.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Following variables should be provided as input parameters:
  - src_repo #Repository that contains ASP.NET 4.8 website executables
  - src_username #Username to access source repository
  - src_password #Password or Token to access source repository
  - branch_name #Branch from which source files are to be cloned
  - docker_repo #Container image repository URL
  - docker_image_path #Path with which to tag the image
  - project_name #Name of Kubernetes namespace which will also be used to uniquely tag the image
  - k8s_host #API URL of Kubernetes cluster
  - k8s_api_key #User token from service account in Kubernetes cluster which has cluster-admin privileges

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
