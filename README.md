# lancom-lcos9

OpenNMS configuration module for LANCOM LCOS9 devices.

## Requirements

Running OpenNMS *NIX operating system

- Download the configuration module from releases as tar.gz file
- OpenNMS 1.12+
- OpenNMS 14+
- LANCOM Devices
- Network access with SNMP v1, v2c, v3
- Optional: git

Running OpenNMS on Windows operating system

- Download the configuration module from releases as ZIP file
- If linking is not possible, you can copy the files to the location
- Optional: git

## Installation

.Download and install from GitHub
[source, bash]
----
cd $OPENNMS_HOME/etc/modules-available
git clone https://github.com/opennms-config-modules/snmp-mib2.git
----

# License & Authors

- Author:: Marcel Fuhrmann

Licensed under the GNU Affero General Public License 3+. You may obtain a copy of the License at http://www.gnu.org/licenses/agpl-3.0.html.


### Datacollection

.Install datacollection configuration
[source, bash]
----
cd $OPENNMS_HOME/etc/datacollection
ln -s ../modules-available/lancom-lco9/datacollection/*.xml .
----

.Include in datacollection-config.xml
[source, xml]
----
<include-collection dataCollectionGroup="LANCOM-LCOS9"/>
----

### Graph report definitions

.Install graph report definitions
[source, bash]
----
cd $OPENNMS_HOME/etc/snmp-graph.properties.d
ln -s ../modules-available/lancom-lcos9/snmp-graph.properties.d/*.properties .
----

### Event definitions

.Install SNMP event definitions
[source, bash]
----
cd $OPENNMS_HOME/etc/events
ln -s ../modules-available/lancom-lcos9/events/*.xml .
----
