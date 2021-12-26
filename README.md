Role Name
=========

Install containerd without docker and make it use the proxy.

Requirements
------------

None

Role Variables
--------------

  - ansible_python_interpreter: "/usr/bin/python3"
  - docker_apt_ignore_key_error: true
  - docker_apt_gpg_key: "https://download.docker.com/linux/{{ ansible_distribution | lower }}/gpg"
  - docker_apt_repository: "deb [arch={{ docker_apt_arch }}] https://download.docker.com/linux/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} {{ docker_apt_release_channel }}"
  - docker_apt_arch: "amd64"
  - docker_apt_release_channel: "stable"
  - http_proxy: "<proxy>"
  - https_proxy: "<proxy>"
  - no_proxy: "<no proxy, more no proxy>"
  - cgroupdriver: "SystemdCgroup = true" #leave empty or comment to use cgroupfs

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars:
        - ansible_python_interpreter: "/usr/bin/python3"
        - docker_apt_ignore_key_error: true
        - docker_apt_gpg_key: "https://download.docker.com/linux/{{ ansible_distribution | lower }}/gpg"
        - docker_apt_repository: "deb [arch={{ docker_apt_arch }}] https://download.docker.com/linux/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} {{ docker_apt_release_channel }}"
        - docker_apt_arch: "amd64"
        - docker_apt_release_channel: "stable"
        - http_proxy: "<proxy>"
        - https_proxy: "<proxy>"
        - no_proxy: "<no proxy, more no proxy>"
        - cgroupdriver: "SystemdCgroup = true" #forcing containerd to use Systemd as cgroupDriver instead of cgroupfs as defined by containerd-fallback
      roles:
         - raskosk.containerd

License
-------

Apache License 2.0

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
