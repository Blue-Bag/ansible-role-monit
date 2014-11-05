Monit
========

Ansible role for configuring Monit. Sample usage see [example.yml](example.yml).

Requirements
------------

An ansible ready host.

Role Variables
--------------

* `monit_services`: List of hashes of services to be monitorized by monit.
  * `process`: Name of the process for monit reference.
  * `pidfile`: Path for this service's pidfile.
  * `start`: Command that starts the service.
  * `stop`: Command that stop the service.
  * `rules`: List of rules to be included in this service.
* `monit_service_detele_unlisted`: Remove existing service monitorization configurations not declared in the `services`. Defaults to `true`.
* `monit_mail_enabled`: Enable mail alerts. Defaults to `false`.
* `monit_mailserver_host`: Mailserver host address. Defaults to `localhost`.
* `monit_mailserver_host`: Mailserver host port. Defaults to `25`.
* `monit_mailserver_user`: Username for authentication on mailserver.
* `monit_mailserver_password`: Password for authentication on mailserver.
* `monit_mailserver_timeout`: Timeout for mailserver connection. Defaults to `5`.
* `monit_mailserver_ssl_version`: If defined, monit will use this algorithm for SSL connection to the mail server. Possible values are `SSLAUTO`, `SSLV2`, `SSLV3`, `TLSV1`, `TLSV11`, `TLSV12`.
* `monit_alert_address`: Mail address where the alerts will be sent to.
* `monit_alert_mail_from`: Sender mail address.
* `monit_alert_mail_subject`: Mail subject.
* `monit_alert_mail_message`: Mail message body.
* `monit_webinterface_enabled`: Enable monit web interface. Defaults to `true`.
* `monit_webinterface_bind`: IP address to bind web interface. Defaults to `0.0.0.0` (listen for external requests).
* `monit_webinterface_port`: Port for web interface. Defaults to `2812`.
* `monit_webinterface_rw_group`: Define group of users allowed to read and write on web interface. It is only applied when defined and is empty by default.
* `monit_webinterface_r_group`: Define group of users allowed to read on web interface. It is only applied when defined and is empty by default.
* `monit_webinterface_acl_rules`: List of ACL rules for the web interface, such as "localhost" or "hauk:password". It is only applied when defined and is empty by default.
