# eVoteAU
Electronic voting needs to be a reality. 

// Developed by Jason Cartwright (@techAU)<br/>
// Last updated 16/5/22 <br/>
// Version 0.2

<h2>Positives</h2>
Increased convenience for submissions 
Lower ongoing costs, reduction of AEC staff
Elimination of millions paper votes, cardboard booths etc 
Instant results
Eliminate donkey votes
Eliminate multi-votes

<h2>Challenges</h2>
Authentication
Remove voter details from vote selection
Log submission details for audit

<h2> User experience </h2>

Users of eVoteAU would be able to vote online, via the web or mobile app. 

To authenticate a user, a user would first sign into the MyGov app/site. 

From here, the user is able to connect their MyGov to AEC / creating an account, similar to how ATO, Medicare, ServicesAustralia oauth system works today. 

MyGov enforces strong pw and MFA should be a good starting point, particularly given millions of Australian's already have this configured as a result of Centerlink payments, CovidSafe checkins etc. 

With the accounts connected, the user would select which election they wish to vote in (Local/State/Federal). This would be based on their registered address and only elections they are eligible to vote in would be presented. 

Once the user selects Election XYZ, the candidates in that electorate are displayed. Heres't where things can vastly improve on the current paper option. 

Candidates can be randomly displayed by session, by day, or fixed based on a pre-determined random selection. The cards for each candidate can not only show their name, but also their photo, party, a summary of their policy positions, and link the user to their website to read further detail on their policy to be best informed when casting their vote. This is far superior to the current offering.

User votes - Once the vote has been submitted, a confirmation prompt is displayed to inform the voter this is final. Upon confirmation, the vote status for this user is updated to voted and is no longer able to vote in this election. 

A user could log back in at a later date and see their vote date/time stamp, the device ID, device manufacturer, device model, user-agent string used to cast the vote.

<H2>Privacy Structure </H2>

It is important that the Vote selection is seperated from voter. 

To achieve this, once the authentication with MyGov, and the election is selected, the user's GovID username is converted to a hash and never shared with the AEC. 

Example (SHA512): H234235235 becomes 6392D1643684237C5810D410F11B74DA9F4F346FFCAE571EC7C2459D24A907DC69AE429C1B5E42AB608A87B671CBB0EEC19C78EB70A4249AD850EAD1629DC08F

As you cast your vote, the vote selection is registered against the hash to verify uniqueness, segmenting the private information about who is voting, with the details. 

This means the AEC never get to see the username and details of the person who submitted the vote, instead the hash, vote selection, IP address, the device ID, device manufacturer, device model, user-agent string used. This data can halp in the event of an audit. 

<H2>Logging and Audits</H2>
The details of a vote submission would be logged to an external system. Only strict access would be provided to authorised personnel and when accessed (read-only) would also be automatically published to a public website for the world to see. 
