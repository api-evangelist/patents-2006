---

title: Guidance and control for an autonomous soaring UAV
abstract: The present invention provides a practical method for UAVs to take advantage of thermals in a manner similar to piloted aircrafts and soaring birds. In general, the invention is a method for a UAV to autonomously locate a thermal and be guided to the thermal to greatly improve range and endurance of the aircraft.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07431243&OS=07431243&RS=07431243
owner: The United States of America as represented by the Administrator of the National Aeronautics and Space Administration
number: 07431243
owner_city: Washington
owner_country: US
publication_date: 20060323
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without payment of any royalties thereon or therefor.

The present invention relates generally autonomous soaring for uninhabited air vehicles UAVs particularly to improved endurance for autonomous soaring UAVs and more particularly to using thermals or convective thermals to improve the performance of UAVs.

Glider pilots have been using buoyant plumes of air found in the lower atmosphere normally referred to as thermals in order to extend the distance that a glider may travel for many years.

Several systems have been developed to assist pilots of gliders or low powered aircraft to locate such thermals in order to provide improved range endurance or cross country speed. For example U.S. Pat. No. 6 012 675 describes a system that monitors air humidity to locate moist thermals and U.S. patent application 2004 0129071 describes a system that employs a database of places on the ground that are likely to generate thermals in conjunction with current weather projections to attempt to estimate positions of thermals for pilots.

Over the past several years it has also been suggested that UAVs could benefit from using thermals in the same manner as piloted aircraft to improve range endurance and speed. For instance Wharington et al. in Control of High Endurance Unmanned Air Vehicle proposes the concept of using thermals to improve the performance of UAVs and discloses a general control scheme that could be applied for the UAV to take advantage of thermals. However the paper states that a superior control scheme would be necessary for practical application of the concept. Further Michael J. Allen the inventor of the present invention in Autonomous Soaring for Improved Endurance of a Small Uninhabited Air Vehicle provides mathematical evidence that UAVs may dramatically improve range and endurance when employing thermals.

However until the present invention no known practical control and guidance system has been developed for UAVs to take advantage of the benefits of thermals. Therefore it is desired to provide a guidance and control system and method for UAVs to locate and use thermals to provide improved range and endurance.

The invention proposed herein comprises a system and method of guidance and control for autonomous UAVs that allow the UAVs to locate and use thermals in order to increase the range and endurance of the UAVs.

Accordingly it is an object of this invention to provide a system and method for an autonomous UAV to independently locate thermals in the lower atmosphere.

It is a further object of this invention to provide a system and method for guiding an autonomous UAV to the center or strongest portion of a located thermal in the lower atmosphere.

This invention meets these and other objectives related to improving guidance and control for an autonomous soaring UAV by providing a method for locating and using thermals to improve endurance of UAVs. The method includes the step of estimating energy rate and energy acceleration from total energy of the air vehicle. This is done by using values for static pressure around the UAV true air speed of the UAV and command to the motor. The method also includes the step of identifying the radius strength and position of a thermal. This is accomplished using the energy rate and location of the UAV. The UAV position error velocity error and steady state turn rate are then obtained using the location of the UAV and the thermal radius strength and position. The method also includes identifying the soaring turn rate command for the UAV using the UAV position error velocity error steady state turn rate and energy acceleration. Also a final turn rate or bank angle is identified for the UAV through mode switching using the soaring turn rate and a waypoint tracking turn rate. Finally the UAV is controlled to guide it to locate and stay within the thermal.

One relatively unexplored way to improve the range duration or cross country speed of an autonomous aircraft is to use buoyant plumes of air found in the lower atmosphere called thermals or convective thermals. Thermals occur when the air near the ground becomes less dense than the surrounding air because of heating or humidity changes at the Earth s surface. Piloted sailplanes rely solely on this free energy to stay aloft for hours at a time and to make cross country flights. Soaring birds such as hawks and vultures have been observed to circle for hours without flapping their wings and Frigatebirds are known to soar continuously day and night using thermals.

Many UAVs have similar sizes wing loadings and mission profiles to soaring birds and sailplanes. Mission profiles that could allow small UAVs to take advantage of thermals include remote sensing surveillance atmospheric research communications force protection and Earth science. A study using a simple UAV simulation with thermals calculated from measured surface and balloon data found that a 2 hour nominal endurance UAV can gain up to 12 hours of flight time using thermals.

The present invention provides a practical method for UAVs to take advantage of thermals in a manner similar to piloted aircrafts and soaring birds. In general the invention comprises a method for a UAV to locate a thermal and autonomously be guided to the thermal to greatly improve the range and endurance of the aircraft.

The top level autonomous soaring guidance and control method is shown in . Static and total pressure sensor input to obtain true air speed along with the aircraft throttle command were used to determine the rate first derivative and acceleration second derivative of aircraft total energy in the total energy estimation block . These energy rate and energy acceleration values are used as inputs to the mode switching block as described further below.

The energy rate from the total energy estimation block along with the position of the aircraft latitude and longitude are then used to identify a thermal that has been encountered by the aircraft . The thermal radius strength and position are calculated in block using these input values.

In the circle guidance block the thermal radius strength and position from block are used to obtain values for aircraft position error and aircraft velocity error in relation to the identified thermal position. The UAV steady state turn rate is also obtained in this step.

The aircraft position error aircraft velocity error aircraft steady state turn rate acquired in guidance block and the energy acceleration obtained from the total energy estimation block are used to provide a soaring turn rate command in the controller block . The soaring turn rate command is the turn rate that is given to the UAV by the controller to lead the aircraft within the thermal to maximize climb rate while the UAV is in soaring mode.

Finally the energy rate energy acceleration waypoint tracking turn command and soaring turn rate command are input into the mode switching block . In the mode switching block mode logic is used to determine when the UAV should be told to switch between searching flight looking for a thermal and soaring flight using a thermal . Energy rate and energy acceleration are used to determine when the aircraft should be in searching mode and follow the waypoint tracking turn command or if the aircraft should be in soaring mode and follow the soaring rate turn command. In this block when the amount of energy obtained from a thermal decreases to a certain level the UAV is commanded to switch from soaring flight to searching flight.

The total energy calculations are shown in blocks and . Total energy is filtered with filter before it is differentiated with filter . Filter is a 2order filter with a bandwidth of 1.2 rad s that is used to remove noise and measurement resolution errors from the estimated total energy before the signal is differentiated. Filter is the combination of a 2order filter and a differentiator. Filter both filters and calculates the rate of change of the input signal.

Energy rate is corrected to account for the energy added to the aircraft by the motor . The correction term was found by differentiating equation 1 and solving for motor terms only. The resulting relationship is given in equation 3 .

where T is the axial force from the motor and M is the aircraft mass. Thrust is calculated from the simple engine model given in equation 5 

where throtis the 1 second delayed throttle command and throtis the trim throttle needed for level flight. The term Tis the maximum thrust generated by the motor. Equation 5 is essentially a gain on the throttle command delta from trim with a one second time delay and a 2order filter with a 0.8 rad s cutoff frequency. Values for Tand throtwere initially taken from ground measurements but were later updated using flight data.

Preferably a limiter is employed in order to ensure that the data calculated falls within certain boundaries to assure that the data makes real world sense.

Filter is used to calculate energy acceleration . Energy acceleration is normalized to produce normalized energy acceleration using equation 6.

Normalized energy acceleration is used for soaring control because normalization reduces the sensitivity of the controller to variations in thermal strength.

The three filters used in the total energy calculations remove noise from the aircraft energy acceleration estimate but with a cost of approximately 2.5 seconds of time delay. This delay reduced the effectiveness of the feedback channel in the controller and is the primary reason for the development of a thermal state estimator described in blocks and of .

An estimation of the thermal location size and strength is made in order to provide the controller with a faster indication of the aircraft state with respect to the thermal. The aircraft position P is calculated in block from the latitude and longitude using equations 7 and 8. Lat Lat 7 Lon Lon cos Lat 8 

Equations 7 and 8 are solved using the equatorial radius of the Earth a the aircraft latitude and longitude Lat and Lon and the latitude and longitude of the chosen origin location Latand Lon. The origin location can be chosen to be the location of the UAV ground station.

A history of previous aircraft positions and energy rates was collected in a first in first out queue block given by equation 9.

Entries to the queue given in equation 9 are made once per second where k is the current measurement index. The length of the queue L used in equation 9 was chosen to be 45.

Estimation of the movement or drift of the thermal block is important for achieving a good estimate of thermal position and radius. Drift is primarily caused by wind but early flight tests showed that thermals do not always drift with the same velocity or direction as the prevailing winds. Thermal drift is calculated by comparing the position of the thermal given by the first 20 entries of the queue with the position of the thermal given by the last 20 entries of the queue. To begin the energy rate entries of the queue are shifted using equation 10 to prevent zero or negative values.

The drift velocity is limited to 10 m s and rate was limited to 0.1 m sto prevent measurement errors in qfrom causing large changes in D. The estimated drift velocity is then used to correct qfor drift to form a corrected queue q using equations 14 15. 1 2 1 1 2 14 3 3 15 

Again referring to the estimated thermal position P is calculated block using the corrected queue q as given in equation 16.

Equation 16 differs from equations 11 and 12 in that the terms of the queue are squared. This makes the resulting estimated thermal position move closer to areas of strong lift. Equation 16 represents the centroid of the aircraft energy rate during the previous Nseconds. This method for estimating thermal position is easy to implement does not require tuning can be used for any thermal size and does not have a high computational cost. Drawbacks associated with this method are that it is sensitive to the length of the queue and it usually biases the estimated thermal position toward the center of the measurement set.

Thermal velocity w is approximated block from the aircraft energy rate history found in q. The equation used to estimate wis given in equation 17. 1.1 max 3 17 

Equation 17 uses the assumption that the maximum thermal velocity is 10 greater than the maximum climb rate experienced by the vehicle during the previous Nseconds. The thermal velocity is rate limited to not increase faster than 0.025 m sand not to decrease faster than 0.015 m sas a way to retain old information about the thermal strength that has been passed from the queue. The estimated thermal strength is used in addition to qto estimate the thermal radius.

The radius of the thermal block is estimated using a gradient descent method to fit an assumed thermal shape to the data found in the queue. The estimation process starts with the calculation of the distance between each position in qto the estimated thermal center Pusing equation 18. square root over 1 1 2 2 square root over 1 1 2 2 square root over 1 1 2 2 square root over 1 1 2 2 18 

The vector S is used to calculate the predicted thermal velocity of each point in qusing the thermal velocity distribution shape given in equation 19.

Equation 19 is first solved using an initial value of 45 meters for the estimated thermal radius r and then estimated thermal radius thereafter. The shape of the thermal velocity distribution is plotted in .

A weighted error err is calculated by taking the difference between the predicted thermal velocity w and the energy rate of the aircraft given in the 3column of the queue q. The weighted error vector is calculated using equation 20. 3 20 

The influence vector H is used to weight the more recent values of qand whigher than the older values. Values for H are plotted in .

Equation 21 gives a measure of the fit between the assumed thermal shape given in equation 19 and the measured thermal velocity stored in the queue. The sum squared error for a perturbed radius ercircumflex over r is calculated in a similar way using equations 22 through 24.

The sum squared error for the current thermal radius and the sum squared error for the perturbed thermal radius are used to calculate a simple gradient as given in equation 26.

Circle guidance block of is described in more detail below. Guidance calculations are used to determine the steady state turn rate needed to fly in the estimated thermal and to produce position and velocity errors to the soaring controller. The aircraft is commanded to fly a circular flight path having a radius r determined by equation 28. r 0.65r 28 

The scale factor 0.65 is chosen because it defines a flight path radius that is usually small enough to be within the thermal core but large enough to avoid the high aircraft sink rate associated with high bank angle turns. The steady state turn rate dot over needed to fly at an airspeed of V along a circular path given by ris given in equation 29.

The negative sign found in equation 29 is used to ensure that the aircraft always circles to the left while soaring. This is done for simplicity and to give the aircraft ground personnel a quick visual indication of the aircraft mode during flight tests. For this embodiment of the invention flight plans were designed to command right turns when the aircraft is searching for thermals and left turns when the aircraft is in soaring mode. Position error err is generated using equation 30. 1 30 

Position error is differentiated and filtered to create velocity error errusing the transfer function given in equation 31.

The guidance calculations given in equations 28 31 calculate the position error velocity error and turn rate command information that is used by the soaring controller to maintain a circular flight path that was centered on the thermal.

Referring to the controller block from is described in further detail. The soaring controller architecture is loosely based on a thermal centering method given for glider pilots in Cross Country Soaring by Reichmann et al. Soaring Society of America Inc. Hobbs N. Mex. ISBN 10883813 01 8 1993 which is incorporated herein by reference. The method states three rules 

These rules are used as a guideline for the soaring controller design. Energy acceleration feedback is used to implement rules 1 and 2 because the rules given by Reichmann et al. are to be applied to the changes in rate of climb. Rule 3 is implemented with steady state turn rate. The soaring controller inputs consist of normalized energy acceleration position error err velocity error err and steady state turn rate dot over . The soaring controller output consists of a turn rate command dot over that is sent to the autopilot. The controller gains k k and k and respectively are tuned by first setting k and k equal to zero. The energy acceleration gain k is tuned to produce a simulated aircraft response that followed the rules outlined by Reichmann et al. when subjected to a variety of thermal strengths and sizes. The thermal model given in the reference is implemented into a hardware in the loop simulation for controller evaluation and gain tuning. The k and k gains are tuned to make the path of the aircraft more circular and to improve the damping of the controller during soaring flight in a variety of thermal sizes and strengths. The resulting control gains were chosen to be 50 0.4 and 0.165 for k k and krespectively. Limiters and are used to limit the inputs into the controller to ensure that one input does not dominate the aircraft s control. The output turn rate command is also limited by a turn rate limiter to ensure the aircraft doesn t turn too abruptly and a limiter to ensure the aircraft only turns left during soaring. Alternatively the turn rate command output of the soaring controller can be used as a bank angle command if desired.

In general mode logic is used to determine when to switch between searching flight and soaring flight. The mode logic described in this section is significant because it determines how a thermal is detected. The mode logic is broken into three components. Thermal detection logic mode switching uses aircraft response to detect thermals upon encountering thermals. An encounter with a thermal by the aircraft produces large changes in energy rate and energy acceleration because of the atmospheric energy imputed to the aircraft as it traverses the thermal. During flight through a thermal the energy acceleration changes sign and becomes negative when the energy rate peaks. The thermal detection logic is tuned to trigger when the thermal is imputing significant energy to the aircraft and the peak value has been reached. Thus the thermal detection logic provides a basic crest determination above a selected threshold for the thermal.

The thermal rejection logic provides a decision to switch from soaring flight to searching flight using energy rate. Thermal rejection is needed to switch from soaring flight to searching flight when the thermal is no longer providing sufficient energy to the aircraft. Two energy rate based criteria are used by the thermal rejection logic . First thermals are rejected if the smoothed output of filter is less than 0.5 m s. This criteria is met if the aircraft encountered light sink for a period of approximately 5 seconds. The second criteria based on the output of filter is triggered if the aircraft has not experienced sufficient energy rate for approximately 10 seconds. Additional criteria not shown may be used to disengage from soaring mode. The additional criteria for example are upper altitude limit exceeded lower altitude limit exceeded lost link and soaring mode disabled by ground station operator.

The third component is the latch mechanism . The latch mechanism receives inputs from the thermal detection logic and the thermal rejection logic and provides the actual switch command from soaring flight to searching flight and visa versa to the aircraft.

What is described are specific examples of many possible variations on the same invention and are not intended in a limiting sense. The claimed invention can be practiced using other variations not specifically described above.

