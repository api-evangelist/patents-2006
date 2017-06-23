---

title: System and methodology for endurance training
abstract: A method and system for assisting a user in maintaining a predetermined pace along a track with a specific predetermined end goal. The preferred embodiment uses a PDA or similar device to allow a user set a specific course goal and to enter (or download) a previous profile pace target along with checkpoint data for a specified track, detecting start/stop and checkpoints along a course, normalizing the user time at each checkpoint and providing wireless speech ‘behind/ahead’ feedback (either time or energy) to a user at each checkpoint along a specified track. The present invention may provide the user with a variable pace along a track or course utilizing upcoming terrain, percentage of work completed and/or user power profiles and may normalize a user goal to other competitors having faster or slower track times.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07572205&OS=07572205&RS=07572205
owner: 
number: 07572205
owner_city: 
owner_country: 
publication_date: 20060824
---
This application is a non provisional application claiming the benefits of provisional application No. 60 596 056 filed Aug. 27 2005.

The present invention relates broadly to a Global Positioning System GPS type device to enhance physical training. More particularly the present invention concerns a physical training system and methodology utilizing target race history data concerning a race pace and comparing it to real time GPS data associated and optionally power meter data with checkpoints along a race track and communicating to the user a normalized pace audible and or visual checkpoint with respect to the time and or distance and or energy ahead or behind a goal time and or goal energy of the target race.

Athletes who train for competitive racing strive to improve their individual endurance and performance throughout their exercise program. Runners bikers skiers rowers etc. may elect to improve their time over a given course or they may elect to lengthen the distance at which they can perform at a fixed time. Goals can be arrived at by history data of an individual or by history data of other individuals who have also performed over a given track.

Prior art cycle devices have utilized a cyclocomputer type device mounted on a bicycle to calculates and display trip information similar to the instruments in the dashboard of a car. A basic cyclocomputer may display the current speed maximum speed trip distance trip time total distance traveled and the current time. More advanced models also may display altitude incline and temperature as well as offer additional functions such as average speed pedaling cadence and a stopwatch. They do not provide any user feedback with respect to checkpoint goals along a track.

Power meters exist to measure power output in watts typically by using a torque sensor in the bottom bracket or rear hub. User power curves can be calculated depending on terrain for predictions of pace along a track. Power meters can be used to calculate the amount of work a user does along a course but are not used in prior art.

U.S. Pat. No. 6 837 827 B1 issued to Wai C. Lee et al. presents a personal training device using GPS data to assist a user in reaching performance goals. The device allows goal and performance information to be loaded and assists a user with audible cues in beep form during a track.

What is needed is a system and methodology that will allow users to compete over a given track against a preset plurality of checkpoint goals. Preferably the system can give the user audible speech feedback using upcoming terrain and power predictions to normalize user pace and to determine user time behind or ahead of a pace goal for each checkpoint. or energy behind or ahead of an energy goal . Preferably the system can have a hands free operation and provide software running on an existing standard operating system and running on an existing hardware platform.

The primary aspect of the present invention is to provide normalized real time user feedback on a pace computer system throughout a track in which a user goal is predetermined for each of a plurality of checkpoints.

Another aspect of the present invention is to utilize upcoming terrain or currents and work completed in providing the user with pace feedback of pace along the set course for each of a plurality of checkpoints.

Another aspect of the present invention is to allow the user to race against a profiled target race and or a set goal for a given course.

Another aspect of the present invention is to provide wireless speech audio feedback to a user concerning the user pace with respect to time ahead or behind a predetermined goal.

Yet another aspect of the present invention is to utilize existing hardware platforms software applications and operating systems for user interfacing.

Still another aspect of the present invention is to provide the ability to normalize paces particularly against faster competitors.

Another aspect of the present invention is to provide for utilization of user power measurements and work completed when looking ahead at upcoming terrain or current for pace predictions.

Another aspect of the present invention is to allow a plurality of users to upload one or more track pace profiles into an internet web site for subsequent downloading to their pace computer system for sharing and competing.

Other aspects of this invention will appear from the following description and appended claims reference being made to the accompanying drawings forming a part of this specification wherein like reference characters designate corresponding parts in the several views.

This invention provides a novel method to create comparative and normalized feedback of user checkpoints along a track in assisting a user with endurance training. The system and methodology of the present invention utilizes a platform application to take into account upcoming terrain or currents which effect the user s athlete s speed. The present invention will provide the user with audio visual feedback at checkpoints by either a time and or distance ahead or behind at each checkpoint. The time ahead and or behind will be normalized with respect to a finishing goal or competitor s pace.

The present invention provides a system and methodology for endurance training with a platform application that will run on an existing operating system such as Windows Mobile and also run on existing hardware such as a personal digital assistant PDA palm pocket PC laptop or other existing handheld type device.

The term PDA will be used herein to describe the hardware platform. Various operating systems run on PDA s such as Palm OS Symbian OS Linux and Windows Mobile to name a few. The preferred embodiment of the present invention utilizes Windows Mobile as the operating system O S of choice. Typical PDA s include but are not limited to a HP iPAQ hw6515 or HP IPAQ hw6915 or other devices provided by various manufacturers such as Garmin i Que M5 etc. Various communication companies such as Verizon Cingular and T Mobile etc support these PDA s. These devices combine computing telephone fax Internet WiFi GPS and networking features and are continuously being updated with more and more features. A typical PDA can function as a cellular phone Global Positioning System GPS digital camera video recorder fax sender Web browser and personal organizer and more. Some PDAs can also react to voice input by using voice recognition technologies. Features and applications are continually added and updated. PDA s have evolved to contain user applications as with the present invention which can be installed on their O S such as Windows Mobile . PDAs are easily mounted to a user via an armband waistband jersey pocket etc. Hands free operation of the present invention is a significant advantage especially for runners and cross country skiers. Since the course is pre selected and the unit is attached to the body before the user lines up at the start there is no need to look at the wrist or push a button at the start during the race or at the finish. This is a significant improvement over prior art for example consider a gloved cross country skier who is using their arms to propel them and cannot stop to push a button or interact with a device. Hands free operation also is an aide to cyclists who find it distracting to push a button before or after an intense interval. Also accuracy is improved since it doesn t rely on human reaction time.

The present invention will also utilize Bluetooth wireless control for communication between a PDA and a hands free headset.

Each target race will be defined by a starting longitude and latitude and time a finish longitude and latitude and time a goal time for completion of the track course waypoints which define longitude latitude altitude and clock time and optionally wattage of the user along the track or course of the race.

Before explaining the disclosed embodiment of the present invention in detail it is to be understood that the invention is not limited in its application to the details of the particular arrangement shown since the invention is capable of other embodiments. Also the terminology used herein is for the purpose of description and not of limitation.

Assume the times at position p and at p are 0 and 1 hour respectively and that p is 10 miles away from p. Using linear interpolation it would be determined that a position five miles away from p would yield a time of one half hour. i.e. Delta time Delta distance d will give the time at distance d. Thus 1 hour 10 miles 5 miles hour.

In step the closest two positions are looked up from the target profile and those two target times are interpolated to give an interpolated target time at the current position. Next in step the difference Delta between the total goal time and target race time is calculated referred to as Delta . If the goal time is different than the target race time the delta will be distributed based on the percentage of work completed. In step the percentage of work completed is calculated. A simple way to calculate the percentage of work completed would be to divide the total distance of the course by the elapsed distance. However the algorithm of the present invention provides a more accurate way to calculate the percentage of work completed by taking the terrain of the course into account. For example if a course went up a hill and then came back down a hill the half way point based on distance would be the top of the hill but the half way point based on work would be somewhere between the start and the top of the hill. This is because more work is done going up the hill in the first half of the course versus going down the hill in the second half of the course. In step the percentage of work completed is multiplied by Delta ref. step and is referred to as Delta . Next in step Delta is added to the interpolated time at the current position to get a target time T. Next in step the target time Tis compared to the actual user time to determine the time the user is ahead or behind the final goal. Step completes the calculations of the algorithm.

Example 1 of algorithm calculations for a course with a user goal time set at 10 minutes 45 seconds and a target race time from previous profiles of 10 minutes 50 seconds is as follows 

As can be seen from the above example 1 the platform application of the present invention utilizes the percentage of work done over a given terrain to provide a much more accurate track in normalizing the user performance along a course. In the above example if the goal time were the same as the track time then Delta would be zero and the user time of 1 min 10 sec would be compared to the interpolated track time of 1 min 5 sec thus the user would receive an audible that would state 5 seconds behind .

Example 2 of algorithm calculations for a course with a user goal time of 29 minutes and a target race time of 29 minutes 30 seconds from previous profiles is as follows 

Power is calculated using strain gauges built into the crankarm of a bicycle pedal crankarm and uses magnetic induction transmitted to magnetic induction receiver which then transmits the data via a wire to a processing unit which could be attached to the bicycle handlebars.

Getting this data into PDA requires a magnetic induction receiver connected to a processing unit which converts the data into a wattage measurement and transmits the data to PDA via a standard Bluetooth transmitter .

Once the wattage data is read from the power measuring device it will be combined with the GPS data to form waypoints along the route which consist of longitude latitude altitude elapsed time and wattage. This data will then be used to notify the user of how far ahead or behind they are of a target power at specified intervals of time or distance.

These data points can be used to calculate the effective wind speed at every point on the course via the following formulas Power watts Drag RelativeVelocity Weight Gravity Velocity Grade Note is multiply symbol Drag 0.5 Coef friction Air density Relative Velocity Relative Velocity Frontal area

In the formula above RelativeVelocity is defined as the vector addition of the Velocity of the bike rider and the wind speed. A more accurate goal pace can be calculated once this data has been collected. Using this data and the current wind speed and direction one can calculate how much faster or slower the rider will be due to the difference in wind speed. This delta time can be distributed across the course based upon the percent power expended along the course as discussed below.

The formula for calculating the percentage of work done at waypoint number p along a course defined by a series of n number of waypoints w. .w. .wdefined by longitude latitude altitude and elapsed time is done in two steps as follows 

Further defined by this formula Grade 100 Where ais the altitude meters above sea level at waypoint wand ais the altitude at wand d is the distance meters between wand w Frontal area 0.44704 approximate number of square meters of bicycle and rider Air density 1.177 kg m at standard ambient temperature and pressure Coef friction 1.0 Gravity 9.8 meters sec Drag 0.5 Coef friction Air density RelativeVelocity RelativeVelocity Frontal area

Although the present invention has been described with reference to preferred embodiments numerous modifications and variations can be made and still the result will come within the scope of the invention. No limitation with respect to the specific embodiments disclosed herein is intended or should be inferred.

