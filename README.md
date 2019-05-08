# ![LOGO](logo.png) Incidents **flow**ground Connector

## Description

A generated **flow**ground connector for the Incidents API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/wmata.com/incidents/1.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:59+03:00

## API Description

Rail, bus, and elevator disruptions/outages.

## Authorization

Supported authorization schemes:
- API Key- API Key
## Actions

### XML - Bus Incidents

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a set of reported bus incidents/delays for a given Route. Omit the<br/>
> Route to return all reported items.</p><br/>
> <br/>
> <p>Note that the Route parameter accepts only base route names and no<br/>
> variations, i.e.: use 10A instead of 10Av1 and 10Av2.</p><br/>
> <br/>
> <p>Bus incidents/delays are refreshed once every 20 to 30 seconds approximately.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>BusIncidents</td><br/>
> <br/>
> <td><br/>
> Array containing bus incident information (<a href=<br/>
> "#BusIncident">BusIncident</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="BusIncident" name="BusIncident">BusIncident<br/>
> Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateUpdated</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) of last update. Will be<br/>
> in YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Description</td><br/>
> <br/>
> <td>Free-text description of the delay or incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentID</td><br/>
> <br/>
> <td>Unique identifier for an incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentType</td><br/>
> <br/>
> <td>Free-text description of the incident type. Usually<br/>
> <span class="text-info">Delay</span> or <span class=<br/>
> "text-info">Alert</span> but is subject to change at any time.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RoutesAffected</td><br/>
> <br/>
> <td>Array containing routes affected. Routes listed are usually<br/>
> identical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),<br/>
> but <em>may</em> differ from what our bus methods return.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `Route` - _optional_ - Bus route.  Use full route code, i.e.: C2 instead of C2v1, C2v2, etc.
    Possible values: 90, X1.

### XML - Elevator/Escalator Outages

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a list of <em>reported</em> elevator and escalator outages at a<br/>
> given station. Omit the StationCode parameter to return all reported<br/>
> outages.</p><br/>
> <br/>
> <p>Note that for stations with multiple platforms and therefore StationCodes<br/>
> (e.g.: Metro Center, L'Enfant Plaza, etc.), a distinct call is required for<br/>
> each StationCode.</p><br/>
> <br/>
> <p>Elevator and escalator outages are refreshed once every 20 to 30 seconds approximately.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>ElevatorIncidents</td><br/>
> <br/>
> <td><br/>
> Array containing elevator/escalator outage information<br/>
> (<a href="#ElevatorIncident">ElevatorIncident</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="ElevatorIncident" name=<br/>
> "ElevatorIncident">ElevatorIncident Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateOutOfServ</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) unit was reported out of<br/>
> service. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T15:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateUpdated</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) outage details was last<br/>
> updated. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T15:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DisplayOrder</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>EstimatedReturnToService</td><br/>
> <br/>
> <td>Estimated date and time (Eastern Standard Time) by when unit is expected to return to normal service. May be NULL, otherwise will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T23:59:59).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>LocationDescription</td><br/>
> <br/>
> <td>Free-text description of the unit location within a station<br/>
> (e.g.: <span class="text-info">Escalator between mezzanine and<br/>
> platform</span>).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StationCode</td><br/>
> <br/>
> <td>Unit's station code. Use this value in other rail-related APIs<br/>
> to retrieve data about a station.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StationName</td><br/>
> <br/>
> <td>Full station name, may include entrance information (e.g.:<br/>
> <span class="text-info">Metro Center, G and 11th St<br/>
> Entrance</span>).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">SymptomCode</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>SymptomDescription</td><br/>
> <br/>
> <td>Description for why the unit is out of service or otherwise in<br/>
> reduced operation.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">TimeOutOfService</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> Use the time<br/>
> portion of the DateOutOfServ element.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>UnitName</td><br/>
> <br/>
> <td>Unique identifier for unit, by type (a single elevator and<br/>
> escalator may have the same UnitName, but no two elevators or two<br/>
> escalators will have the same UnitName).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">UnitStatus</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> If listed here,<br/>
> the unit is inoperational or otherwise impaired.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>UnitType</td><br/>
> <br/>
> <td>Type of unit. Will be <span class="text-info">ELEVATOR</span><br/>
> or <span class="text-info">ESCALATOR</span>.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `StationCode` - _optional_ - Two-letter station code.  Use the Station List method to return a list of all station codes.
    Possible values: A03, E09.

### XML - Rail Incidents

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns reported rail incidents (significant disruptions and delays to<br/>
> normal service). The data is identical to WMATA's <a href=<br/>
> "http://www.metroalerts.info/rss.aspx?rs">Metrorail Service Status<br/>
> feed</a>.</p><br/>
> <br/>
> <p>Rail incidents are refreshed once every 20 to 30 seconds approximately.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Incidents</td><br/>
> <br/>
> <td><br/>
> Array containing rail disruption information (<a href=<br/>
> "#Incident">Incident</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Incident" name="Incident">Incident Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateUpdated</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) of last update. Will be<br/>
> in YYYY-MM-DDTHH:mm:SS format (e.g.: 2010-07-29T14:21:28).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DelaySeverity</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Description</td><br/>
> <br/>
> <td>Free-text description of the incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">EmergencyText</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">EndLocationFullName</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentID</td><br/>
> <br/>
> <td>Unique identifier for an incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentType</td><br/>
> <br/>
> <td>Free-text description of the incident type. Usually Delay or<br/>
> Alert but is subject to change at any time.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>LinesAffected</td><br/>
> <br/>
> <td>Semi-colon and space separated list of line codes (e.g.:<br/>
> <span class="text-info">RD;</span> or <span class="text-info">BL;<br/>
> OR;</span> or <span class="text-info">BL; OR; RD;</span>). We do<br/>
> plan to update this to return something more reasonable like an<br/>
> array, but until then, use code similar to the following:<br><br/>
> <br><br/>
> <code>"RD; GR; BL;".split(/;[\s]?/).filter(function(fn) { return fn<br/>
> !== ''; })</code></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">PassengerDelay</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through"><br/>
> StartLocationFullName</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

### JSON - Bus Incidents

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a set of reported bus incidents/delays for a given Route. Omit the<br/>
> Route to return all reported items.</p><br/>
> <br/>
> <p>Note that the Route parameter accepts only base route names and no<br/>
> variations, i.e.: use 10A instead of 10Av1 and 10Av2.</p><br/>
> <br/>
> <p>Bus incidents/delays are refreshed once every 20 to 30 seconds approximately.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>BusIncidents</td><br/>
> <br/>
> <td><br/>
> Array containing bus incident information (<a href=<br/>
> "#BusIncident">BusIncident</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="BusIncident" name="BusIncident">BusIncident<br/>
> Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateUpdated</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) of last update. Will be<br/>
> in YYYY-MM-DDTHH:mm:ss format (e.g.: 2014-10-28T08:13:03).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Description</td><br/>
> <br/>
> <td>Free-text description of the delay or incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentID</td><br/>
> <br/>
> <td>Unique identifier for an incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentType</td><br/>
> <br/>
> <td>Free-text description of the incident type. Usually<br/>
> <span class="text-info">Delay</span> or <span class=<br/>
> "text-info">Alert</span> but is subject to change at any time.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RoutesAffected</td><br/>
> <br/>
> <td>Array containing routes affected. Routes listed are usually<br/>
> identical to base route names (i.e.: not 10Av1 or 10Av2, but 10A),<br/>
> but <em>may</em> differ from what our bus methods return.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `Route` - _optional_ - Base bus route; variations are not recognized (i.e.: C2 instead of C2v1, C2v2, etc.).
    Possible values: 90, X1.

### JSON - Elevator/Escalator Outages

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a list of <em>reported</em> elevator and escalator outages at a<br/>
> given station. Omit the StationCode parameter to return all reported<br/>
> outages.</p><br/>
> <br/>
> <p>Note that for stations with multiple platforms and therefore StationCodes<br/>
> (e.g.: Metro Center, L'Enfant Plaza, etc.), a distinct call is required for<br/>
> each StationCode.</p><br/>
> <br/>
> <p>Elevator and escalator outages are refreshed once every 20 to 30 seconds approximately.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>ElevatorIncidents</td><br/>
> <br/>
> <td><br/>
> Array containing elevator/escalator outage information<br/>
> (<a href="#ElevatorIncident">ElevatorIncident</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="ElevatorIncident" name=<br/>
> "ElevatorIncident">ElevatorIncident Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateOutOfServ</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) unit was reported out of<br/>
> service. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T15:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateUpdated</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) outage details was last<br/>
> updated. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T15:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DisplayOrder</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>EstimatedReturnToService</td><br/>
> <br/>
> <td>Estimated date and time (Eastern Standard Time) by when unit is expected to return to normal service. May be NULL, otherwise will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T23:59:59).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>LocationDescription</td><br/>
> <br/>
> <td>Free-text description of the unit location within a station<br/>
> (e.g.: <span class="text-info">Escalator between mezzanine and<br/>
> platform</span>).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StationCode</td><br/>
> <br/>
> <td>Unit's station code. Use this value in other rail-related APIs<br/>
> to retrieve data about a station.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StationName</td><br/>
> <br/>
> <td>Full station name, may include entrance information (e.g.:<br/>
> <span class="text-info">Metro Center, G and 11th St<br/>
> Entrance</span>).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">SymptomCode</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>SymptomDescription</td><br/>
> <br/>
> <td>Description for why the unit is out of service or otherwise in<br/>
> reduced operation.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">TimeOutOfService</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> Use the time<br/>
> portion of the DateOutOfServ element.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>UnitName</td><br/>
> <br/>
> <td>Unique identifier for unit, by type (a single elevator and<br/>
> escalator may have the same UnitName, but no two elevators or two<br/>
> escalators will have the same UnitName).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">UnitStatus</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> If listed here,<br/>
> the unit is inoperational or otherwise impaired.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>UnitType</td><br/>
> <br/>
> <td>Type of unit. Will be <span class="text-info">ELEVATOR</span><br/>
> or <span class="text-info">ESCALATOR</span>.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `StationCode` - _optional_ - Station code.  Use the Station List method to return a list of all station codes.
    Possible values: A03, E09.

### JSON - Rail Incidents

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns reported rail incidents (significant disruptions and delays to<br/>
> normal service). The data is identical to WMATA's <a href=<br/>
> "http://www.metroalerts.info/rss.aspx?rs">Metrorail Service Status<br/>
> feed</a>.</p><br/>
> <br/>
> <p>Rail incidents are refreshed once every 20 to 30 seconds approximately.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Incidents</td><br/>
> <br/>
> <td><br/>
> Array containing rail disruption information (<a href=<br/>
> "#Incident">Incident</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Incident" name="Incident">Incident Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateUpdated</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) of last update. Will be<br/>
> in YYYY-MM-DDTHH:mm:SS format (e.g.: 2010-07-29T14:21:28).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DelaySeverity</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Description</td><br/>
> <br/>
> <td>Free-text description of the incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">EmergencyText</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">EndLocationFullName</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentID</td><br/>
> <br/>
> <td>Unique identifier for an incident.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>IncidentType</td><br/>
> <br/>
> <td>Free-text description of the incident type. Usually Delay or<br/>
> Alert but is subject to change at any time.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>LinesAffected</td><br/>
> <br/>
> <td>Semi-colon and space separated list of line codes (e.g.:<br/>
> <span class="text-info">RD;</span> or <span class="text-info">BL;<br/>
> OR;</span> or <span class="text-info">BL; OR; RD;</span>). We do<br/>
> plan to update this to return something more reasonable like an<br/>
> array, but until then, use code similar to the following:<br><br/>
> <br><br/>
> <code>"RD; GR; BL;".split(/;[\s]?/).filter(function(fn) { return fn<br/>
> !== ''; })</code></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">PassengerDelay</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through"><br/>
> StartLocationFullName</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span></td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

## License

**flow**ground :- Telekom iPaaS / wmata-com-incidents-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
