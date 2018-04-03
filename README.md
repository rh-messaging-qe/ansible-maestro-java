Role Name
=========

This role is used to deploy a Maestro test cluster and related tools

Requirements
------------

None.

Role Variables
--------------

Variables controlling the configuration of a broker instance.

| Name              | Default Value       | Description          |
|-------------------|---------------------|----------------------|
| `maestro_user` | maestro | Maestro system user name |
| `maestro_url` | mqtt://localhost:1883 | URL of the Maestro broker |
| `maestro_timezone` | Europe/Prague | Timezone of the Maestro test cluster |

Role Variables: worker
--------------

| `maestro_worker_download_url` | null | Provided either the download URL directly or as an environment variable exported via MAESTRO_WORKER_DOWNLOAD_URL |
| `maestro_worker_install_dest` | "/home/{{ maestro_user }}/" | Install directory |
| `maestro_worker_skip_install` | false | Whether to skip installation of the worker |
| `maestro_worker_log_dir` |  "{{ maestro_worker_install_dest }}/log" | Test log directory |
| `maestro_worker_role` | sender | Worker role (either sender or receiver) |
| `maestro_worker_restart_server` | true | Whether to automatically restart the worker after deployment |

Role Variables: exporter
--------------

| `maestro_exporter_download_url` | null | Provided either the download URL directly or as an environment variable exported via MAESTRO_EXPORTER_DOWNLOAD_URL |
| `maestro_exporter_install_dest` | "/home/{{ maestro_user }}/" | Install directory |
| `maestro_exporter_skip_install` | false | Whether to skip installation of the exporter |
| `maestro_exporter_log_dir` |  "{{ maestro_exporter_install_dest }}/log" | Test log directory |
| `maestro_exporter_restart_server` | true | Whether to automatically restart the exporter after deployment |

Role Variables: inspector
--------------

| `maestro_inspector_download_url` | null | Provided either the download URL directly or as an environment variable exported via MAESTRO_inspector_DOWNLOAD_URL |
| `maestro_inspector_install_dest` | "/home/{{ maestro_user }}/" | Install directory |
| `maestro_inspector_skip_install` | false | Whether to skip installation of the inspector |
| `maestro_inspector_log_dir` |  "{{ maestro_inspector_install_dest }}/log" | Test log directory |
| `maestro_inspector_restart_server` | true | Whether to automatically restart the inspector after deployment |


Role Variables: agent
--------------

| `maestro_agent_download_url` | null | Provided either the download URL directly or as an environment variable exported via MAESTRO_agent_DOWNLOAD_URL |
| `maestro_agent_install_dest` | "/home/{{ maestro_user }}/" | Install directory |
| `maestro_agent_skip_install` | false | Whether to skip installation of the agent |
| `maestro_agent_log_dir` |  "{{ maestro_agent_install_dest }}/log" | Test log directory |
| `maestro_agent_restart_server` | true | Whether to automatically restart the agent after deployment |

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: test
      vars:
        maestro_worker_download_url: "{{ lookup('env','MAESTRO_WORKER_DOWNLOAD_URL') }}"
      roles:
        - ansible-maestro-java

License
-------

Apache 2.0

Author Information
------------------

Messaging QE team @ redhat.com
