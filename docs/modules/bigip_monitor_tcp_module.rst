.. _bigip_monitor_tcp:


bigip_monitor_tcp - Manages F5 BIG-IP LTM tcp monitors.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.4


.. contents::
   :local:
   :depth: 2


Synopsis
--------

* M
* a
* n
* a
* g
* e
* s
*  
* F
* 5
*  
* B
* I
* G
* -
* I
* P
*  
* L
* T
* M
*  
* t
* c
* p
*  
* m
* o
* n
* i
* t
* o
* r
* s
*  
* v
* i
* a
*  
* i
* C
* o
* n
* t
* r
* o
* l
*  
* S
* O
* A
* P
*  
* A
* P
* I
* .


Requirements (on host that executes module)
-------------------------------------------

  * f5-sdk >= 2.2.3


Options
-------

.. raw:: html

    <table border=1 cellpadding=4>
    <tr>
    <th class="head">parameter</th>
    <th class="head">required</th>
    <th class="head">default</th>
    <th class="head">choices</th>
    <th class="head">comments</th>
    </tr>
                <tr><td>interval<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td></td>
        <td><div>The interval specifying how frequently the monitor instance of this template will run. If this parameter is not provided when creating a new monitor, then the default value will be 5. This value <b>must</b> be less than the <code>timeout</code> value.</div>        </td></tr>
                <tr><td>ip<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td></td>
        <td><div>IP address part of the IP/port definition. If this parameter is not provided when creating a new monitor, then the default value will be '*'.</div><div>If this value is an IP address, and the <code>type</code> is <code>tcp</code> (the default), then a <code>port</code> number must be specified.</div>        </td></tr>
                <tr><td>name<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td></td>
        <td><div>Monitor name.</div></br>
    <div style="font-size: small;">aliases: monitor<div>        </td></tr>
                <tr><td>parent<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>/Common/tcp</td>
        <td></td>
        <td><div>The parent template of this monitor template. Once this value has been set, it cannot be changed. By default, this value is the <code>tcp</code> parent on the <code>Common</code> partition.</div>        </td></tr>
                <tr><td>partition<br/><div style="font-size: small;"> (added in 2.5)</div></td>
    <td>no</td>
    <td>Common</td>
        <td></td>
        <td><div>Device partition to manage resources on.</div>        </td></tr>
                <tr><td>password<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td></td>
        <td><div>The password for the user account used to connect to the BIG-IP. This option can be omitted if the environment variable <code>F5_PASSWORD</code> is set.</div>        </td></tr>
                <tr><td>port<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td></td>
        <td><div>Port address part of the IP/port definition. If this parameter is not provided when creating a new monitor, then the default value will be '*'. Note that if specifying an IP address, a value between 1 and 65535 must be specified</div><div>This argument is not supported for TCP Echo types.</div>        </td></tr>
                <tr><td>receive<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td></td>
        <td><div>The receive string for the monitor call.</div>        </td></tr>
                <tr><td>send<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td></td>
        <td><div>The send string for the monitor call.</div>        </td></tr>
                <tr><td>server<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td></td>
        <td><div>The BIG-IP host. This option can be omitted if the environment variable <code>F5_SERVER</code> is set.</div>        </td></tr>
                <tr><td>server_port<br/><div style="font-size: small;"> (added in 2.2)</div></td>
    <td>no</td>
    <td>443</td>
        <td></td>
        <td><div>The BIG-IP server port. This option can be omitted if the environment variable <code>F5_SERVER_PORT</code> is set.</div>        </td></tr>
                <tr><td>time_until_up<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td></td>
        <td><div>Specifies the amount of time in seconds after the first successful response before a node will be marked up. A value of 0 will cause a node to be marked up immediately after a valid response is received from the node. If this parameter is not provided when creating a new monitor, then the default value will be 0.</div>        </td></tr>
                <tr><td>timeout<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td></td>
        <td><div>The number of seconds in which the node or service must respond to the monitor request. If the target responds within the set time period, it is considered up. If the target does not respond within the set time period, it is considered down. You can change this number to any number you want, however, it should be 3 times the interval number of seconds plus 1 second. If this parameter is not provided when creating a new monitor, then the default value will be 16.</div>        </td></tr>
                <tr><td>type<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>tcp</td>
        <td><ul><li>tcp</li><li>tcp_echo</li><li>tcp_half_open</li><li>TTYPE_TCP</li><li>TTYPE_TCP_ECHO</li><li>TTYPE_TCP_HALF_OPEN</li></ul></td>
        <td><div>The template type of this monitor template.</div><div>Deprecated in 2.4. Use one of the <code>bigip_monitor_tcp_echo</code> or <code>bigip_monitor_tcp_half_open</code> modules instead.</div>        </td></tr>
                <tr><td>user<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td></td>
        <td><div>The username to connect to the BIG-IP with. This user must have administrative privileges on the device. This option can be omitted if the environment variable <code>F5_USER</code> is set.</div>        </td></tr>
                <tr><td>validate_certs<br/><div style="font-size: small;"> (added in 2.0)</div></td>
    <td>no</td>
    <td>True</td>
        <td><ul><li>True</li><li>False</li></ul></td>
        <td><div>If <code>no</code>, SSL certificates will not be validated. This should only be used on personally controlled sites using self-signed certificates. This option can be omitted if the environment variable <code>F5_VALIDATE_CERTS</code> is set.</div>        </td></tr>
        </table>
    </br>



Examples
--------

 ::

    
    - name: Create TCP Monitor
      bigip_monitor_tcp:
          state: "present"
          server: "lb.mydomain.com"
          user: "admin"
          password: "secret"
          name: "my_tcp_monitor"
          type: "tcp"
          send: "tcp string to send"
          receive: "tcp string to receive"
      delegate_to: localhost
    
    - name: Remove TCP Monitor
      bigip_monitor_tcp:
          state: "absent"
          server: "lb.mydomain.com"
          user: "admin"
          password: "secret"
          name: "my_tcp_monitor"
      delegate_to: localhost

Return Values
-------------

Common return values are documented here :doc:`common_return_values`, the following are the fields unique to this module:

.. raw:: html

    <table border=1 cellpadding=4>
    <tr>
    <th class="head">name</th>
    <th class="head">description</th>
    <th class="head">returned</th>
    <th class="head">type</th>
    <th class="head">sample</th>
    </tr>

        <tr>
        <td> parent </td>
        <td> New parent template of the monitor. </td>
        <td align=center> changed </td>
        <td align=center> string </td>
        <td align=center> tcp </td>
    </tr>
            <tr>
        <td> receive </td>
        <td> The new receive string for this monitor. </td>
        <td align=center> changed </td>
        <td align=center> string </td>
        <td align=center> tcp string to receive </td>
    </tr>
            <tr>
        <td> ip </td>
        <td> The new IP of IP/port definition. </td>
        <td align=center> changed </td>
        <td align=center> string </td>
        <td align=center> 10.12.13.14 </td>
    </tr>
            <tr>
        <td> interval </td>
        <td> The new interval in which to run the monitor check. </td>
        <td align=center> changed </td>
        <td align=center> int </td>
        <td align=center> 2 </td>
    </tr>
            <tr>
        <td> send </td>
        <td> The new send string for this monitor. </td>
        <td align=center> changed </td>
        <td align=center> string </td>
        <td align=center> tcp string to send </td>
    </tr>
            <tr>
        <td> time_until_up </td>
        <td> The new time in which to mark a system as up after first successful response. </td>
        <td align=center> changed </td>
        <td align=center> int </td>
        <td align=center> 2 </td>
    </tr>
            <tr>
        <td> timeout </td>
        <td> The new timeout in which the remote system must respond to the monitor. </td>
        <td align=center> changed </td>
        <td align=center> int </td>
        <td align=center> 10 </td>
    </tr>
            <tr>
        <td> port </td>
        <td> The new port of IP/port definition. </td>
        <td align=center> changed </td>
        <td align=center> string </td>
        <td align=center> admin@root.local </td>
    </tr>
        
    </table>
    </br></br>

Notes
-----

.. note::
    - Requires the f5-sdk Python package on the host. This is as easy as pip install f5-sdk.
    - Requires BIG-IP software version >= 12



Status
~~~~~~

This module is flagged as **preview** which means that it is not guaranteed to have a backwards compatible interface.


Support
~~~~~~~

This module is community maintained without core committer oversight.

For more information on what this means please read :doc:`modules_support`


For help in developing on modules, should you be so inclined, please read :doc:`community`, :doc:`dev_guide/developing_test_pr` and :doc:`dev_guide/developing_modules`.