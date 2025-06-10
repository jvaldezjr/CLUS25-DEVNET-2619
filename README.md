# CLUS25-DEVNET-2619

# Getting Started

The playbook uses several environment variables, as well as some static variables used for development and testing.

You will need to configure your own env variables, such as:
*  `export MERAKI_DASHBOARD_API_KEY=yourKey`
*  `export MERAKI_ORG_ID=orgID`

**NB:** the test_upgrade_time needs to be reoplaced

Static variables for the iperf client / server will need to be replaced and interface IPs updated.

# How to build on this

* Uncomment the 'Gather Meraki Organizations' task and use its response to dynamically set the test_org_id variable.
* Modify the 'Get firmware versions for each network' task to loop over a list of organization IDs extracted from the 'Gather Meraki Organizations' task
* Replace the FreshDesk tasks with your own ticketing system
* Add additional throughput tests (e.g. inter-VLAN tests, reverse the direction of the tests, add UDP tests)
* Define acceptance criteria for the tests in a .yml file to read into the playbook
  * Define pass / fail / needs review thresholds to auto-close the firmware upgrade ticket
* Re-run the iperf tests after the scheduled firmware upgrade and document those in the ticket
* Add additional pre / post upgrade checks and post those to the ticket (e.g. wireless assurance data) to check for differences in user outcomes


# Resources
* [Meraki API documentation](https://developer.cisco.com/meraki/api-v1/)
* [Meraki Postman collections](https://www.postman.com/meraki-api?tab=collections)
* [Meraki Python SDK](https://github.com/meraki/dashboard-api-python) / [DevNet learning lab](https://developer.cisco.com/learning/modules/intro-meraki-python-sdk/)
* [Meraki Ansible collection](https://docs.ansible.com/ansible/latest/collections/cisco/meraki/index.html) / [DevNet learning lab](https://developer.cisco.com/learning/labs/meraki-dashboard-ansible/introduction/)
* [DevNet Code Exchange](https://developer.cisco.com/codeexchange/search/?products=Meraki)
