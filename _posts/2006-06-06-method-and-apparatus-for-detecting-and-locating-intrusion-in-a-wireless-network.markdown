---

title: Method and apparatus for detecting and locating intrusion in a wireless network
abstract: Method and apparatus for locating an intruding radio frequency signal in a wireless network. Relative distance measurements are computed between pairs of receivers from a plurality of receivers to the source of the intruding signal based on received signal strength. Loci of possible locations are plotted, points of intersection are determined, and a clustering algorithm is applied, yielding the location of the source of the intruding signal. The invention is distinguished in that its operation does not require knowledge of either the transmitted power or antenna gain of the intruding signal source.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07570213&OS=07570213&RS=07570213
owner: The United States of America as represented by the Secretary of the Air Force
number: 07570213
owner_city: Washington
owner_country: US
publication_date: 20060606
---
This patent application claims the priority benefit of the filing date of provisional application Ser. No. 60 690 540 having been filed in the United States Patent and Trademark Office on Jun. 14 2005 and now incorporated by reference herein.

The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

This invention relates generally to the field of location of radio frequency transmitters. This invention relates more specifically to the algorithms and processing techniques applied thereto for the location of rogue radio frequency transmitters based upon multiple measures of received signal strength.

There exist techniques that can provide an accurate fix on a transmitter s location. Generally however these techniques require one or more of the following a priori knowledge about the transmitter a finite calibrated geospatial reference frame a cooperative transmitter and or a large geographically fixed receiver network infrastructure.

U.S. Pat. No. 7 006 838 B2 to Diener et al discloses an apparatus and method for determining the location of an unknown wireless radio signal source. The unknown source s signal is received at a plurality of known receiving locations where one of the plurality is used as a reference. The source s signals received at all other receiving locations are compared to the reference. A reference signal is transmitted by a known location whereupon the difference of time of arrival between the known reference signal and the unknown source s signal is computed and the location of the unknown source computed therefrom. This system has the disadvantage however in that it is not passively listening to an intruding source rather it must actively transmit a reference signal having the effect of making its presence known.

U.S. Pat. No. 6 993 592 B2 to Krumm et al discloses a location measurement apparatus and process for determining the location of radio frequency badges where the badges transmit a message containing their unique identifier to receivers at known locations. The receivers measure signal strength of the transmitting badge if it exceeds a predefined threshold. The receivers then transmit data to a central computer as to the time identification and received signal strength indication RSSI for each badge which is entered into a table. Locations are computed for those badges whose signal strength exceeds the predefined threshold. This system is an example of an approach where a calibrated geospatial reference frame tracks and locates signal sources. Since the system is calibrated on signal strength to representative locations the received signal strength at any one of a plurality of fixed position receivers from a source is readily matched up. The utility of this system would be significantly diminished where intruding sources were outside of a calibrated geospatial reference frame because the necessary vectors would be unavailable.

U.S. Pat. No. 6 920 329 B2 to Kennedy Jr. et al discloses an apparatus and method to find the location of two way radios amongst a plurality of base stations at known geographic points. The invention employs a time of arrival determination which may also be combined with an angle of arrival determination. With this system antenna characteristics of the receiving base stations is critical as well as is their orientation meaning the system must be well calibrated. This would further suggest that the system has no utility for other than a permanently fixed deployment.

U.S. Pat. No. 6 861 982 B2 to Forstrom et al discloses a method for determining the location of a non cooperative radio frequency emitter requiring at least three receivers sharing common time with a time reference. Trilateration is employed on signal detection times from emitter to receivers. Since any or all of the receivers may be mobile communication with the reference provides an accurate adjustment of propagation time in compensation for the receiver s mobility. Since trilateration is employed this system will have no utility with fewer than three receivers deployed operating and in reception of the signal source.

U.S. Pat. No. 7 020 475 B2 to Bahl et al discloses a method for a mobile computer user to determine his location within a building. Wireless base stations are employed at known locations throughout a building. Signal strength is measured and looked up in a table of known locations of base stations and their respective signal strengths. The current location of the mobile computer user is determined as the one corresponding to the most likely base station. The method may be used in the opposite sense where the base stations detect the signal strength of the mobile computer user provided a reference signal strength versus distance of the mobile computer from the base stations is known. This system however depends entirely upon charted signal strengths at predetermined locations within a fixed structure. It would have little utility for geolocating a wider ranging intruder signal source of unknown signal strength.

U.S. Pat. No. 7 019 694 B2 to Krumm et al discloses a method for locating radio frequency transmitters. A plurality of receivers measure and forward signal strength to a central computer. Multiple measured signal strengths attributed to the same transmitter form a locating signal strength vector. Exemplary vectors are generated in a calibration procedure to various locations. The locating signal strength vector is compared to the previously obtained exemplary vectors to determine with which exemplary vector the locating signal strength vector corresponds so as to determine the location of the radio frequency transmitter. The benefits of this system include reception by as few as only one receiver and compatibility with an existing computer network. The drawback of this system however is that it is possible to locate a signal source only if receivers are already placed in and the network to which they are connected is extended to every conceivable location a signal source of interest might be.

Angle of Arrival AoA and Time Difference of Arrival TDOA methods are desirable to use but they require directional antennas that must be precisely sited and or complex receiver hardware with additional channel capacity for distributing precise time references. Aside from the time it would take to integrate calibrate and maintain these components their addition greatly increases the cost of a wireless intrusion detection system WIDS .

What is lacking from the prior art is a system that instead employs upon simple omni directional detection of rogue transmitters without the need for vast databases of a priori information such as calibrated RSSI look up tables that when simply placed in any geospatial location will immediately begin to detect and geolocate intruding signal sources in a wireless network.

The present invention performs location solely on the non directional Received Signal Strength Indication RSSI provided by the commercial off the shelf COTS wireless cards. When the present invention achieves a sighting of a rogue transmitter it logs and reports the observation time RSSI and other information. The RSSI alone is not a highly useful measurement in that it provides only two facts an indication of where the measured RSSI falls within the measurement scale relative to the maximum RSSI and that a stronger intrusion signal has a higher RSSI than a weaker signal.

Most wireless access points utilize omnidirection antennas in their wireless network infrastructure. These will provide the rogue transmitter a source of entry. RSSI in combination with the analytical tools does provide a valid geolocation method for the case of a rogue transmitter. However it is clearly invalid for the case of a rogue transmitter employing a high directionality high gain antenna.

If it is assumed that a rogue transmitter and the WIDS receivers are coplanar i.e. they are all at the same height or altitude the mathematical analysis can be limited to two dimensions. However while a two dimensional analysis is suitable for a drive by network intruder scenario for example it is clearly inadequate for three dimensional structures such as multi floor office buildings.

For distances that are less than a few tens of kilometers it is essentially immaterial that the equations used in the analysis of RSSI are based on plane trigonometry rather than spherical trigonometry. Thus if a grid system is used it may be assumed only to be based on rectangular coordinates where the origin orientation and scale are arbitrary. For the characteristically small RSSI reception distances it is sufficient to consider latitude longitude lat long coordinates to be rectangular on a plane assuming that longitude is scaled appropriately for the given latitude.

Little about RF propagation particularly through unknown numbers and composition of walls can be assumed. The single greatest variation seems to be the nearly random factor of radio frequency RF attenuation due to the environment walls floors ceilings people and other obstructions. In particular the attenuation due to walls is most unpredictable as their composition and style of construction vary widely within even a small area of a building. Signal paths that may be clear line of sight or travel through one two three or more walls must be accounted for. However experiments have indicated that in practice the ceteris paribus principle held and RF attenuation seemed to balance out on the multiple paths.

Rogue network intruders must transmit There is no way for a WIDS receiver to detect a purely passive monitor. WIDS sightings must be simultaneous to detect a mobile rogue transmitter. Stationary transmitters which transmit periodically can be located by integrating measurements obtained over a period of time.

The present invention provides a method and apparatus for detecting the presence of and locating the source of a radio frequency signal.

It is therefore an object of the present invention to provide a method and apparatus for locating an intruding radio frequency signal in a wireless network.

It is a further object of the present invention to provide a method and apparatus for determining the relative distance between the source of an intruding signal and two receivers based on respective received signal strength indications.

It is still a further object of the present invention to provide a method and apparatus for determining the location of an intruding signal source by identifying the intersection of loci of possible locations.

It is yet still a further object of the present invention to provide a method and apparatus for detecting and locating the source of an intruding signal without dependence upon directional antennas.

It is yet another object of the present invention to provide a method and apparatus for detecting and locating the source of an intruding signal without dependence upon knowledge of either or both the transmitting power or antenna gain of the intruding signal source.

An additional object of the present invention is to provide a method and apparatus for detecting and locating the source of an intruding signal without dependence upon time synchronization between receivers.

An additional object of the present invention is to provide a method and apparatus for detecting and locating the source of an intruding signal without being limited to locating such sources only within a pre calibrated geospace.

Briefly stated the present invention method and apparatus for detecting and locating intrusion in a wireless network achieves these and other objects through computing relative distance measurements between pairs from a plurality of receivers to the source of the intruding signal based on received signal strength and through determining the loci of possible locations by plotting the loci by finding the points of intersection of these loci and by applying a clustering algorithm thereto from which the actual location of the source of the intruding signal is found. The present invention is distinguished from the prior art in that its operation does not rely upon knowledge of either the transmitted power or antenna gain of the intruding signal source.

In the fundamental embodiment of the present invention method for detecting and locating a transmitting source of a radio frequency RF signal intrusion into a wireless network an intruding radio frequency signal is first received by a plurality of receivers. The received signal strength Ris then measured on each of the plurality of receivers. For each paired combination of receivers one relative distance measurement d to the location of the transmitting source is computed where the one relative distance measurement d is a function of the received signal strength Rof each of the receivers in each of the paired combinations. For each paired combination of the plurality of receivers the possible locations of the transmitting source lying on the locus of points satisfying d R R is computed. The computation further comprises computing the displacement c of the center of the locus from the first receiver in each paired combination according to

According to a fundamental embodiment of the present invention method for detecting and locating a transmitting source of a radio frequency RF signal intrusion into a wireless network the number of possible loci on which an intruding radio frequency signal source may be located is determined as M where

Still according to a fundamental embodiment of the present invention method for detecting and locating a transmitting source of a radio frequency RF signal intrusion into a wireless network the number of possible points at which the loci intersect and at which an intruding radio frequency signal source may be further deemed to be located is determined as I where

In contrast to and in improvement upon prior art devices the present invention may be rapidly deployed to an unsurveyed and uncalibrated location and commence locating a radio frequency source. This is a fundamental need which has yet been unfulfilled in the prior art.

The above and other objects features and advantages of the present invention will become apparent from the following description read in conjunction with the accompanying drawings in which like reference numerals designate the same elements.

Since a WIDS receiver in the present invention can measure only RSSI the first step thereafter is to convert measured RSSI to some measure of the distance from a WIDS receiver to the rogue transmitter.

There is a wealth of literature dealing with geolocation based on the absolute measurement of distance. Today s most notable example of this approach is the Global Positional Service GPS see for instance the detailed description by Strang and Borre Stra97 or a recent Scientific American article on GPS Eng04 . Strang and Borre Stra97 p. 448 describe the basis of GPS as follows Its measurements yield distances and not angles. We are dealing with trilateration and not triangulation. This has been desired for centuries because angles are definitely awkward. On a surface i.e. a 2 D world three distances define three circles that ideally intersect at a single point the target. GPS in the 3 D world finds the intersection of spheres there are two solutions with three spheres but one is discarded as being too far from the Earth s surface. While technically. GPS trilaterates in fact GPS needs at least one or more additional satellites in view to compensate for timing errors that result in distance errors. Time is thus considered to be a fourth dimension. In the present invention the term multilateration is used instead of trilateration as usually more than three distances are measured.

As for the measured RSSIs of the present invention it has already been pointed out that both the characteristics of the rogue transmitter and the RF propagation conditions are unknown. Therefore the present invention performs at best a relative distance measurement.

Referring to and depict the results of experiments performed to determine what the RSSI actually measures and to relate that value to an indication of distance. It can be seen that 

The prior art Aldu04 has experimented extensively with the relationship between RSSI and distance. One set of experiments found that the best fitting model for the observed data was a 4degree polynomial but the coefficients for terms with degree greater than one were small compared to that of the linear term that the simple linear fit to the data in the present invention is satisfactory. There is a discrepancy in Aldu04 in that their 4degree equation does not match the data from which it is derived nor does it show an inverse relationship between the RSSI and distance although that observation is made in the text of the paper. Inspection of their data indicates that the linear model is an excellent fit for the present invention.

In the present invention linear regression of RSSI versus distance is performed using Microsoft Excel for convenience in graphing the results. Any textbook on statistics for example Men73 p. 381 gives the equations for this process. n RSSI values are denoted by xand the corresponding distance values are denoted as y. Two sample means

Referring to and the result achieved when two WIDS receivers in the present invention are used to make a pair of relative distance measurements to a rogue transmitter is depicted.

The best that can be achieved by measuring RSSI when rogue transmitter characteristics and RF propagation conditions are unknown is to make a relative distance estimate. Specifically in the present invention dand drepresent the estimated distances from a rogue transmitter to WIDS receiver and WIDS receiver respectively where the scale of the distance measurement is assumed to be linear with zero offset but otherwise unknown. The relative distance d is then computed as d d d. The location of WIDS receiver is denoted as x y and the location of WIDS receiver is denoted as x y . The location of the rogue transmitter must lie on the locus of points that satisfy d d d. It can be shown that the locus of points is a circle or in the special case where d 1 the locus of points is a line. To simplify calculations when d 1 d 1.00001 is used instead resulting in a circle with a very large radius which closely approximates a straight line in the region of interest.

Note that if the actual distances dand dare known then two circles can be drawn one centered at x y with radius dand the other at x y with radius d. In such a situation the ambiguity of the location of the rogue transmitter would have been narrowed to just two points the intersection of the two circles. In this case however the reduction of knowledge results in the ambiguity of location being all the points on a circle.

In the present invention the circle is not centered on a WIDS receiver. Rather it is centered at some displacement c from WIDS receiver along a line joining the two WIDS receivers. The value of c is measured with respect to WIDS receiver because the relative distance was defined as d d drather than as d d. Denoting as D the distance between the two WIDS receivers where D square root over x x y y square root over x x y y . Then the value of c is computed as

For example consider the case where WIDS receiver is at 0 0 WIDS receiver is at 4 0 and the usually unknown position of the rogue transmitter is 0 3 . The rogue transmitters are denoted as Tx in . This configuration conveniently forms a 3 4 5 right triangle where d d d 5 3 1.667 which is the only information the WIDS system is allowed to know about the rogue transmitter.

Referring to shows the circle resulting from the equations for x y and r which clearly contains the point 0 3 where the rogue transmitter is located.

Referring to shows the result when the relative distances are the same as in the previous example but the relationship is reversed i.e. the rogue transmitter is closer to WIDS receiver .

Referring to shows yet another example. The WIDS receiver and locations are 1 1 and 4 4 respectively with relative distance d d d 2.

Therefore two RSSIs from a pair of sightings of a rogue transmitter by WIDS receivers which produces a single relative distance measurement yields a circle as the locus of points that satisfy that relative distance relationship. However if a third sighting is made three pairs of relative distances can be calculated from the three RSSIs resulting in three circles. Three intersecting circles however do not yield one point of intersection because the three circles are not independent and an interesting but frustrating relationship emerges.

Referring to and depicts the problem with only three sightings being that there are two possible locations of the rogue transmitter.

In the preferred embodiment of the present invention it is necessary to have a minimum of four sightings. Referring to and adding a fourth sighting to the examples shown in and enables unique solutions. The need for the fourth sighting when relative distances are used instead of absolute distances is analogous to the problem in statistics when a degree of freedom is lost for each linear dependency in a relationship. By analogy the Global Positioning System GPS which measures absolute distances instead of the weaker relative distances in the present invention requires a minimum of four satellite sightings with additional sightings being even better. Clearly this limitation of the present invention is not unprecedented among geolocation systems.

Still referring to and it is noted that half of the intersections between pairs of circles fall on the desired location of the rogue transmitter.

Referring to it is shown that notwithstanding four sightings it is critical to ensure that collinear placement of WIDS receivers is avoided because if the four WIDS receivers lie on a straight line two solutions are obtained rather than the unambiguous unique solution. Having three collinear WIDS receivers in the present invention is acceptable. The problem arises when there are four collinear receivers. While it was already discussed that it is recommended that more than four sightings be used to reduce errors due to actual RSSI measurements this may prove to be difficult to achieve with practical densities of deployed WIDS receivers but at the very least non collinear placement of any four WIDS receivers of the present invention should be avoided so as not to waste any opportunity to geolocate accurately to a single unambiguous point. The characteristics of the intersecting circles graphically depicted. The numerical solutions of their two intersections must be found.

Given two circles specified by their center points and radii Circle 1 Center point radius Circle 2 Center point radius their two points of intersection is obtained P 

Referring to and L is the Euclidean distance between two center points Pand P where L is computed as square root over square root over Intermediate Points of Intersection

Referring to and points Pand Pare mapped on to the x axis of the coordinate system as the two new points P 0 0 and P L 0 . Point P is found at the apex of the triangle with base length L and sides of length rand r the radii of the two circles . The coordinates of this point are denoted as P L h . Land h can be solved for because from the Law of Cosines it can be shown that

At this point the coordinates of one intersection have been found. The other intersection is P which is found by the reflecting P across the x axis and is given by P L h not shown in .

The two solutions P and P are based on the two center points P and P that were mapped on to the x axis. It remains to rotate and translate these two values to obtain the actual solutions for the intersections Pand P.

Circle center Pwas mapped specifically to point P at the origin to facilitate the rotation and translation operations. This must now be accounted for to find the actual points of intersection. Letting a denote the counterclockwise angle that Pmakes with Pwith respect to the x axis see . Then the sin and cosine of are computed as

Referring to and it is depicted how in the present invention each pair of WIDS sightings yields one relative distance estimate which yields one circle specified as a center point P and radius r . Each pair of these resulting circles specified as P rand P r yields a pair of intersections Pand P. A minimum of four non collinear WIDS sightings are required to obtain a unique solution.

N represents the number of WIDS receivers that have sighted a rogue transmitter and M represents the number of circles that result and I represents the number of intersections. Therefore since each pair of WIDS receivers create a circle the number of resulting locus circles is computed as

In practice the present invention will not generally yield fourth order or higher expressions for I since the number of receivers N is limited to those that simultaneously determine a RSSI for a given rogue transmitter.

Referring to the elements of the present invention comprising the plurality of wireless intrusion detection processors the enterprise security management ESM processor and the wireless intrusion detection concentrator processor are depicted deployed so as to detect intrusion by signal sources either standalone or those that are transmitting into wireless access points.

Referring to photographically shows the subcomponents of an exemplary wireless intrusion detection sensor embodiment.

Referring to a deployment of wireless intrusion detection processor of the present invention is shown in a building. Hewlett Packard OpenView software is utilized in the enterprise security management ESM processor to log all intrusion events by time location signal strength and severity.

Having described preferred embodiments of the invention with reference to the accompanying drawings it is to be understood that the invention is not limited to those precise embodiments and that various changes and modifications may be effected therein by ones skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

