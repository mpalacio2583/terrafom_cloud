== Overview

Ansible Automation Platform 2 + Terraform is a project created by ASA Red hat Colombia to provide Ansible students with a project that allows them to build a playbook stream where the following is done:
1. IaC stage with (Terraform)
2. Inventory verification stages (Ansible)
3. NodeJS (Ansible) application deployment stage
4. Stage to functional tests of the application. (Ansible)
Note: all tested to work on AZURE and AWS public clouds.

=== Usage

1. Set up the environmental variable GUID to your GUID

----
export GUID=abcd
----
. Edited your `ansible.cfg` depending if you are executing on `bastion` or remotely
* Pay attention to the value of `ssh_args`
. Configure your _chosen_ `ssh` config file
* Set the correct user
* Set the correct key(s)
* If necessary, e.g. executing from a remote *control node*, install the right key(s)
+
NOTE: You can easily test your chosen `ssh` config file e.g. `ssh -F ssh.cfg app1` etc
. Execute your main wrapping playbook
[source,bash]
----
 ansible-playbook main.yml
----

=== Structure

[source,bash]
----
.
├── README.adoc                       <1>
├── ansible.cfg                       <2>
├── cleanup.yml                       <3>
├── haproxy.cfg.j2                    <4>
├── hosts                             <5>
├── index.html.app1                   <6>
├── index.html.app2                   <6>
├── index.html.j2                     <6>
├── main.yml                          <7>
├── ssh-bastion.cfg                   <8>
└── ssh-laptop.cfg                    <9>
----

. This README file
. Simple ansible.cfg
. Convenience playbook that removes the 3tier app - use to retest your work
. A badly written jinja2 template for HAProxy - *HINTS*
** This should loop over the apps group
** Perhaps the Tomcat port should be a variable?
. inventory file - referenced from `ansible.cfg`
** Note the use of a lookup in line 2, if you prefer consider:
** Hard coding it `GUID=abcd` or passing it in via `-e GUID=abcd`.
. Too many index.html files?
. Main entry point
. `ssh` configuration file for working off a `bastion` host
. `ssh` configuration file for working off a laptop or remote *control node*


=== Potential strategies

* Divide and Conquer
. Break `main.yml` into individual plays
. Discard the redundant ones
. Wrap in a `main.yml` or similar using `import_playbooks:`

* Role Play
. Identify the key roles e.g. common, frontends, apps, database etc
. Convert the relevant plays into roles
. Create wrapping playbook with multiple *plays* invoking *roles* on *groups*


command: ansible-playbook -i hosts main.yml

Download image terraform: quay.io/nmartins/terraform_ee 
name: Terraform EE
Pull: Only pull the image.
