Ansible Role for JIRA
=====================

[![Build Status](https://travis-ci.org/pantarei/ansible-role-jira.svg?branch=master)](https://travis-ci.org/pantarei/ansible-role-jira)
 [![GitHub tag](https://img.shields.io/github/tag/pantarei/ansible-role-jira.svg)](https://github.com/pantarei/ansible-role-jira)
 [![GitHub license](https://img.shields.io/github/license/pantarei/ansible-role-jira.svg)](https://github.com/pantarei/ansible-role-jira/blob/master/LICENSE)
 [![Ansible Role](https://img.shields.io/ansible/role/5989.svg)](https://galaxy.ansible.com/detail#/role/5989)

Ansible Role for Atlassian JIRA Installation.

Requirements
------------

This role require Ansible 1.9 or higher.

This role was designed for Ubuntu Server 14.04 LTS.

Role Variables
--------------

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">parameter</th>
<th align="left">required</th>
<th align="left">default</th>
<th align="left">choices</th>
<th align="left">comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">jira_archive</td>
<td align="left">yes</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-jira/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">Download archive filename for cache during (re)install.</td>
</tr>
<tr class="even">
<td align="left">jira_catalina</td>
<td align="left">yes</td>
<td align="left">/usr/share/jira</td>
<td align="left"></td>
<td align="left">Location for the JIRA installation directory.</td>
</tr>
<tr class="odd">
<td align="left">jira_connector_port</td>
<td align="left">yes</td>
<td align="left">8080</td>
<td align="left"></td>
<td align="left">JIRA Apache Tomcat connector port.</td>
</tr>
<tr class="even">
<td align="left">jira_context_path</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"></td>
<td align="left">Pass value as <code>path</code> to <a href="https://github.com/pantarei/ansible-role-jira/blob/master/templates/usr/share/jira/conf/server.xml.j2">template</a>.</td>
</tr>
<tr class="odd">
<td align="left">jira_hash_salt</td>
<td align="left">yes</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-jira/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">Specific password hash salt for sha512.</td>
</tr>
<tr class="even">
<td align="left">jira_home</td>
<td align="left">yes</td>
<td align="left">/var/lib/jira</td>
<td align="left"></td>
<td align="left">Location for the JIRA home directory.</td>
</tr>
<tr class="odd">
<td align="left">jira_jvm_maximum_memory</td>
<td align="left">yes</td>
<td align="left">1024m</td>
<td align="left"></td>
<td align="left">JIRA JVM maximum memory usage.</td>
</tr>
<tr class="even">
<td align="left">jira_jvm_minimum_memory</td>
<td align="left">yes</td>
<td align="left">512m</td>
<td align="left"></td>
<td align="left">JIRA JVM minimum memory usage.</td>
</tr>
<tr class="odd">
<td align="left">jira_jvm_support_recommended_args</td>
<td align="left">no</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-jira/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">Atlassian Support recommended JVM arguments.</td>
</tr>
<tr class="even">
<td align="left">jira_pass</td>
<td align="left">yes</td>
<td align="left">Xea4aesh</td>
<td align="left"></td>
<td align="left">Password for JIRA system user.</td>
</tr>
<tr class="odd">
<td align="left">jira_proxy_name</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"></td>
<td align="left">Pass value as <code>proxyName</code> to <a href="https://github.com/pantarei/ansible-role-jira/blob/master/templates/usr/share/jira/conf/server.xml.j2">template</a>.</td>
</tr>
<tr class="even">
<td align="left">jira_scheme</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"><ul>
<li><code>null</code></li>
<li>http</li>
<li>https</li>
</ul></td>
<td align="left">Install JIRA in standalone mode if <code>null</code>, or integrating with Apache using HTTP if <code>http</code>, or integrating with Apache using HTTPS if <code>https</code>.</td>
</tr>
<tr class="odd">
<td align="left">jira_server_port</td>
<td align="left">yes</td>
<td align="left">8005</td>
<td align="left"></td>
<td align="left">JIRA Apache Tomcat server port.</td>
</tr>
<tr class="even">
<td align="left">jira_sha256</td>
<td align="left">yes</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-jira/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">Download archive sha256 checksum for cache during (re)install.</td>
</tr>
<tr class="odd">
<td align="left">jira_upgrade</td>
<td align="left">no</td>
<td align="left"><code>false</code></td>
<td align="left"><ul>
<li><code>true</code></li>
<li><code>false</code></li>
</ul></td>
<td align="left">If <code>true</code>, trigger upgrade by stop existing JIRA service, purge existing JIRA installation direcoty before normal tasks.</td>
</tr>
<tr class="even">
<td align="left">jira_url</td>
<td align="left">yes</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-jira/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">URL for download archive.</td>
</tr>
<tr class="odd">
<td align="left">jira_user</td>
<td align="left">yes</td>
<td align="left">jira</td>
<td align="left"></td>
<td align="left">Username for JIRA system user.</td>
</tr>
</tbody>
</table>

Dependencies
------------

No additional role dependencies.

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: hswong3i.jira, jira_user: 'jira', jira_pass: 'Xea4aesh', jira_upgrade: 'false' }

License
-------

-   Code released under [MIT](https://github.com/pantarei/ansible-role-jira/blob/master/LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

