# Network-Traffic-Inspector

1.) Description

  The project's primary goal was to examine intercepted packets to identify users who are            acquiring software from websites on blacklists or those considered illicit. We conducted an        analysis of both source and destination IP addresses to determine the user's geographical          location. By monitoring the path of packets through the network, we were able to pinpoint users    engaged in the download of software or data from these prohibited websites. Additionally, we       established a database to retain comprehensive packet details, including geographical              information, for future reference.

  2.) Technolgies and Tools Used

  This figure describes the overall working of the application. The admin continuously monitors different activities performed by the users in the network. If any user is performing any illegal activity such as performing downloads on illegal or blacklisted sites, then it detects at the admin side. Then, by using PyGeoIP, the admin correlates the IP address to the physical location of the destination of the packet. This is done by querying the database with a particular IP address. The database returns the record containing the city, region name, postal code, country name, latitude and longitude which is plotted on Google Earth. The database contains the URL, destination IP, timestamp, latitude, longitude etc. It is stored in an encrypted format to add on to the security of the system. Also, database can be used for future analysis and creating statistics of the illegal activities performed which can help enhancing the security.


3.) Implementation:

Initially, packets are captured using wireshark and live packet are captured using Ettercap.
Dpkt – a python module used as an analyzing tool for parsing packets. It analyzes each individual packet and analyzes the protocol layer. It provides IP address of the user downloading the application from an illegal or a blacklisted site.
The geographical location of the packet can be found by using PyGeoIP which queries the GeoLiteCity database.
Google maps API gives a geographical display of the destination of the packet that is being analyzed in KML format. All the information about the packet i.e. source and destination IP, timestamp, URL, geographical latitude, longitude and location plotted gets stored in the database.
All the information stored in the database is encrypted for security purposes.
