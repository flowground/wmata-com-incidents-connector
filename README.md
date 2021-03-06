# ![LOGO](logo.png) Incidents **flow**ground Connector

## Description

A generated **flow**ground connector for the Incidents API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/wmata.com/incidents/1.0/swagger.json<br/>
Generated at: 2019-07-08T14:36:02+03:00

## API Description

Rail, bus, and elevator disruptions/outages.<br/>

## Authorization

Supported authorization schemes:
- API Key- API Key
## Actions

### XML - Bus Incidents
<blockquote><h4 class="text-primary">Description</h4>

<p>Returns a set of reported bus incidents/delays for a given Route. Omit the
Route to return all reported items.</p>

<p>Note that the Route parameter accepts only base route names and no
variations, i.e.: use 10A instead of 10Av1 and 10Av2.</p>

<p>Bus incidents/delays are refreshed once every 20 to 30 seconds approximately.</p>

<h4 class="text-primary">Response Elements</h4>

<table class="table table-condensed table-hover">
<thead>
<tr>
<th class="col-md-3">Element</th>

<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td>BusIncidents</td>

<td>
Array containing bus incident information (<a href=
"#BusIncident">BusIncident</a>).
</td>
</tr>

<tr>
<td colspan="2">
<div class="text-primary" style="margin-top: 1em">
<a id="BusIncident" name="BusIncident">BusIncident
Elements</a>
</div>
</td>
</tr>

<tr>
<td>DateUpdated</td>

<td>Date and time (Eastern Standard Time) of last update. Will be
in YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).</td>
</tr>

<tr>
<td>Description</td>

<td>Free-text description of the delay or incident.</td>
</tr>

<tr>
<td>IncidentID</td>

<td>Unique identifier for an incident.</td>
</tr>

<tr>
<td>IncidentType</td>

<td>Free-text description of the incident type. Usually
<span class="text-info">Delay</span> or <span class=
"text-info">Alert</span> but is subject to change at any time.</td>
</tr>

<tr>
<td>RoutesAffected</td>

<td>Array containing routes affected. Routes listed are usually
identical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),
but <em>may</em> differ from what our bus methods return.</td>
</tr>
</tbody>
</table></blockquote>

#### Input Parameters
* `Route` - _optional_ - Bus route.  Use full route code, i.e.: C2 instead of C2v1, C2v2, etc.<br/>
    Possible values: 90, X1.

### XML - Elevator/Escalator Outages
<blockquote><h4 class="text-primary">Description</h4>

<p>Returns a list of <em>reported</em> elevator and escalator outages at a
given station. Omit the StationCode parameter to return all reported
outages.</p>

<p>Note that for stations with multiple platforms and therefore StationCodes
(e.g.: Metro Center, L'Enfant Plaza, etc.), a distinct call is required for
each StationCode.</p>

<p>Elevator and escalator outages are refreshed once every 20 to 30 seconds approximately.</p>

<h4 class="text-primary">Response Elements</h4>

<table class="table table-condensed table-hover">
<thead>
<tr>
<th class="col-md-3">Element</th>

<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td>ElevatorIncidents</td>

<td>
Array containing elevator/escalator outage information
(<a href="#ElevatorIncident">ElevatorIncident</a>).
</td>
</tr>

<tr>
<td colspan="2">
<div class="text-primary" style="margin-top: 1em">
<a id="ElevatorIncident" name=
"ElevatorIncident">ElevatorIncident Elements</a>
</div>
</td>
</tr>

<tr>
<td>DateOutOfServ</td>

<td>Date and time (Eastern Standard Time) unit was reported out of
service. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
2014-10-27T15:17:00).</td>
</tr>

<tr>
<td>DateUpdated</td>

<td>Date and time (Eastern Standard Time) outage details was last
updated. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
2014-10-27T15:17:00).</td>
</tr>

<tr>
<td style="text-decoration: line-through">DisplayOrder</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>EstimatedReturnToService</td>

<td>Estimated date and time (Eastern Standard Time) by when unit is expected to return to normal service. May be NULL, otherwise will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
2014-10-27T23:59:59).</td>
</tr>

<tr>
<td>LocationDescription</td>

<td>Free-text description of the unit location within a station
(e.g.: <span class="text-info">Escalator between mezzanine and
platform</span>).</td>
</tr>

<tr>
<td>StationCode</td>

<td>Unit's station code. Use this value in other rail-related APIs
to retrieve data about a station.</td>
</tr>

<tr>
<td>StationName</td>

<td>Full station name, may include entrance information (e.g.:
<span class="text-info">Metro Center, G and 11th St
Entrance</span>).</td>
</tr>

<tr>
<td style="text-decoration: line-through">SymptomCode</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>SymptomDescription</td>

<td>Description for why the unit is out of service or otherwise in
reduced operation.</td>
</tr>

<tr>
<td style="text-decoration: line-through">TimeOutOfService</td>

<td><span class="text-danger">Deprecated.</span> Use the time
portion of the DateOutOfServ element.</td>
</tr>

<tr>
<td>UnitName</td>

<td>Unique identifier for unit, by type (a single elevator and
escalator may have the same UnitName, but no two elevators or two
escalators will have the same UnitName).</td>
</tr>

<tr>
<td style="text-decoration: line-through">UnitStatus</td>

<td><span class="text-danger">Deprecated.</span> If listed here,
the unit is inoperational or otherwise impaired.</td>
</tr>

<tr>
<td>UnitType</td>

<td>Type of unit. Will be <span class="text-info">ELEVATOR</span>
or <span class="text-info">ESCALATOR</span>.</td>
</tr>
</tbody>
</table></blockquote>

#### Input Parameters
* `StationCode` - _optional_ - Two-letter station code.  Use the Station List method to return a list of all station codes.<br/>
    Possible values: A03, E09.

### XML - Rail Incidents
<blockquote><h4 class="text-primary">Description</h4>

<p>Returns reported rail incidents (significant disruptions and delays to
normal service). The data is identical to WMATA's <a href=
"http://www.metroalerts.info/rss.aspx?rs">Metrorail Service Status
feed</a>.</p>

<p>Rail incidents are refreshed once every 20 to 30 seconds approximately.</p>

<h4 class="text-primary">Response Elements</h4>

<table class="table table-condensed table-hover">
<thead>
<tr>
<th class="col-md-3">Element</th>

<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td>Incidents</td>

<td>
Array containing rail disruption information (<a href=
"#Incident">Incident</a>).
</td>
</tr>

<tr>
<td colspan="2">
<div class="text-primary" style="margin-top: 1em">
<a id="Incident" name="Incident">Incident Elements</a>
</div>
</td>
</tr>

<tr>
<td>DateUpdated</td>

<td>Date and time (Eastern Standard Time) of last update. Will be
in YYYY-MM-DDTHH:mm:SS format (e.g.: 2010-07-29T14:21:28).</td>
</tr>

<tr>
<td style="text-decoration: line-through">DelaySeverity</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>Description</td>

<td>Free-text description of the incident.</td>
</tr>

<tr>
<td style="text-decoration: line-through">EmergencyText</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td style="text-decoration: line-through">EndLocationFullName</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>IncidentID</td>

<td>Unique identifier for an incident.</td>
</tr>

<tr>
<td>IncidentType</td>

<td>Free-text description of the incident type. Usually Delay or
Alert but is subject to change at any time.</td>
</tr>

<tr>
<td>LinesAffected</td>

<td>Semi-colon and space separated list of line codes (e.g.:
<span class="text-info">RD;</span> or <span class="text-info">BL;
OR;</span> or <span class="text-info">BL; OR; RD;</span>). We do
plan to update this to return something more reasonable like an
array, but until then, use code similar to the following:<br>
<br>
<code>"RD; GR; BL;".split(/;[\s]?/).filter(function(fn) { return fn
!== ''; })</code></td>
</tr>

<tr>
<td style="text-decoration: line-through">PassengerDelay</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td style="text-decoration: line-through">
StartLocationFullName</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>
</tbody>
</table></blockquote>

### JSON - Bus Incidents
<blockquote><h4 class="text-primary">Description</h4>

<p>Returns a set of reported bus incidents/delays for a given Route. Omit the
Route to return all reported items.</p>

<p>Note that the Route parameter accepts only base route names and no
variations, i.e.: use 10A instead of 10Av1 and 10Av2.</p>

<p>Bus incidents/delays are refreshed once every 20 to 30 seconds approximately.</p>

<h4 class="text-primary">Response Elements</h4>

<table class="table table-condensed table-hover">
<thead>
<tr>
<th class="col-md-3">Element</th>

<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td>BusIncidents</td>

<td>
Array containing bus incident information (<a href=
"#BusIncident">BusIncident</a>).
</td>
</tr>

<tr>
<td colspan="2">
<div class="text-primary" style="margin-top: 1em">
<a id="BusIncident" name="BusIncident">BusIncident
Elements</a>
</div>
</td>
</tr>

<tr>
<td>DateUpdated</td>

<td>Date and time (Eastern Standard Time) of last update. Will be
in YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).</td>
</tr>

<tr>
<td>Description</td>

<td>Free-text description of the delay or incident.</td>
</tr>

<tr>
<td>IncidentID</td>

<td>Unique identifier for an incident.</td>
</tr>

<tr>
<td>IncidentType</td>

<td>Free-text description of the incident type. Usually
<span class="text-info">Delay</span> or <span class=
"text-info">Alert</span> but is subject to change at any time.</td>
</tr>

<tr>
<td>RoutesAffected</td>

<td>Array containing routes affected. Routes listed are usually
identical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),
but <em>may</em> differ from what our bus methods return.</td>
</tr>
</tbody>
</table></blockquote>

#### Input Parameters
* `Route` - _optional_ - Base bus route; variations are not recognized (i.e.: C2 instead of C2v1, C2v2, etc.).<br/>
    Possible values: 90, X1.

### JSON - Elevator/Escalator Outages
<blockquote><h4 class="text-primary">Description</h4>

<p>Returns a list of <em>reported</em> elevator and escalator outages at a
given station. Omit the StationCode parameter to return all reported
outages.</p>

<p>Note that for stations with multiple platforms and therefore StationCodes
(e.g.: Metro Center, L'Enfant Plaza, etc.), a distinct call is required for
each StationCode.</p>

<p>Elevator and escalator outages are refreshed once every 20 to 30 seconds approximately.</p>

<h4 class="text-primary">Response Elements</h4>

<table class="table table-condensed table-hover">
<thead>
<tr>
<th class="col-md-3">Element</th>

<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td>ElevatorIncidents</td>

<td>
Array containing elevator/escalator outage information
(<a href="#ElevatorIncident">ElevatorIncident</a>).
</td>
</tr>

<tr>
<td colspan="2">
<div class="text-primary" style="margin-top: 1em">
<a id="ElevatorIncident" name=
"ElevatorIncident">ElevatorIncident Elements</a>
</div>
</td>
</tr>

<tr>
<td>DateOutOfServ</td>

<td>Date and time (Eastern Standard Time) unit was reported out of
service. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
2014-10-27T15:17:00).</td>
</tr>

<tr>
<td>DateUpdated</td>

<td>Date and time (Eastern Standard Time) outage details was last
updated. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
2014-10-27T15:17:00).</td>
</tr>

<tr>
<td style="text-decoration: line-through">DisplayOrder</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>EstimatedReturnToService</td>

<td>Estimated date and time (Eastern Standard Time) by when unit is expected to return to normal service. May be NULL, otherwise will be in YYYY-MM-DDTHH:mm:ss format (e.g.:
2014-10-27T23:59:59).</td>
</tr>

<tr>
<td>LocationDescription</td>

<td>Free-text description of the unit location within a station
(e.g.: <span class="text-info">Escalator between mezzanine and
platform</span>).</td>
</tr>

<tr>
<td>StationCode</td>

<td>Unit's station code. Use this value in other rail-related APIs
to retrieve data about a station.</td>
</tr>

<tr>
<td>StationName</td>

<td>Full station name, may include entrance information (e.g.:
<span class="text-info">Metro Center, G and 11th St
Entrance</span>).</td>
</tr>

<tr>
<td style="text-decoration: line-through">SymptomCode</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>SymptomDescription</td>

<td>Description for why the unit is out of service or otherwise in
reduced operation.</td>
</tr>

<tr>
<td style="text-decoration: line-through">TimeOutOfService</td>

<td><span class="text-danger">Deprecated.</span> Use the time
portion of the DateOutOfServ element.</td>
</tr>

<tr>
<td>UnitName</td>

<td>Unique identifier for unit, by type (a single elevator and
escalator may have the same UnitName, but no two elevators or two
escalators will have the same UnitName).</td>
</tr>

<tr>
<td style="text-decoration: line-through">UnitStatus</td>

<td><span class="text-danger">Deprecated.</span> If listed here,
the unit is inoperational or otherwise impaired.</td>
</tr>

<tr>
<td>UnitType</td>

<td>Type of unit. Will be <span class="text-info">ELEVATOR</span>
or <span class="text-info">ESCALATOR</span>.</td>
</tr>
</tbody>
</table></blockquote>

#### Input Parameters
* `StationCode` - _optional_ - Station code.  Use the Station List method to return a list of all station codes.<br/>
    Possible values: A03, E09.

### JSON - Rail Incidents
<blockquote><h4 class="text-primary">Description</h4>

<p>Returns reported rail incidents (significant disruptions and delays to
normal service). The data is identical to WMATA's <a href=
"http://www.metroalerts.info/rss.aspx?rs">Metrorail Service Status
feed</a>.</p>

<p>Rail incidents are refreshed once every 20 to 30 seconds approximately.</p>

<h4 class="text-primary">Response Elements</h4>

<table class="table table-condensed table-hover">
<thead>
<tr>
<th class="col-md-3">Element</th>

<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td>Incidents</td>

<td>
Array containing rail disruption information (<a href=
"#Incident">Incident</a>).
</td>
</tr>

<tr>
<td colspan="2">
<div class="text-primary" style="margin-top: 1em">
<a id="Incident" name="Incident">Incident Elements</a>
</div>
</td>
</tr>

<tr>
<td>DateUpdated</td>

<td>Date and time (Eastern Standard Time) of last update. Will be
in YYYY-MM-DDTHH:mm:SS format (e.g.: 2010-07-29T14:21:28).</td>
</tr>

<tr>
<td style="text-decoration: line-through">DelaySeverity</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>Description</td>

<td>Free-text description of the incident.</td>
</tr>

<tr>
<td style="text-decoration: line-through">EmergencyText</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td style="text-decoration: line-through">EndLocationFullName</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td>IncidentID</td>

<td>Unique identifier for an incident.</td>
</tr>

<tr>
<td>IncidentType</td>

<td>Free-text description of the incident type. Usually Delay or
Alert but is subject to change at any time.</td>
</tr>

<tr>
<td>LinesAffected</td>

<td>Semi-colon and space separated list of line codes (e.g.:
<span class="text-info">RD;</span> or <span class="text-info">BL;
OR;</span> or <span class="text-info">BL; OR; RD;</span>). We do
plan to update this to return something more reasonable like an
array, but until then, use code similar to the following:<br>
<br>
<code>"RD; GR; BL;".split(/;[\s]?/).filter(function(fn) { return fn
!== ''; })</code></td>
</tr>

<tr>
<td style="text-decoration: line-through">PassengerDelay</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>

<tr>
<td style="text-decoration: line-through">
StartLocationFullName</td>

<td><span class="text-danger">Deprecated.</span></td>
</tr>
</tbody>
</table></blockquote>

## License

**flow**ground :- Telekom iPaaS / wmata-com-incidents-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
