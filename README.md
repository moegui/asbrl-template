[![pipeline status](https://gitlab.com/moegui/devops/asbrl-template/badges/master/pipeline.svg)](https://gitlab.com/moegui/devops/asbrl-template/commits/master)

Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

**Example**
- TEMPLATE_DEST: (String)
- TAGS:
    - RELEASE: (String)
    - ENVIRONMENT_TYPE: (String)
- PARAMETERS: (List)
    - NAME: (String)
    - TYPE: String (Default)
    - PATH: (String)
    - DESCRIPTION: (String)

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

      - name: Generate {{EnvironmentType}} cf-parameters
        include_role:
          name: asbrl-ssm-parameterstore
        vars:
          TEMPLATE_DEST: ./artifacts/{{EnvironmentType}}/cf-elasticstack-parameters.yml
          TAGS:
            RELEASE: "{{Release}}"
            ENVIRONMENT_TYPE: "{{EnvironmentType}}"
          PARAMETERS:
            - NAME: Monitoring
              PATH: Elasticsearch
              DESCRIPTION: Elasticsearch Allow the monitoring node
            - NAME: AlarmDiskUsed
              PATH: Cloudwatch
              TYPE: Number
              DESCRIPTION: Cloudwatch alarm threshold for metric Disk Used

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Moegui.com
