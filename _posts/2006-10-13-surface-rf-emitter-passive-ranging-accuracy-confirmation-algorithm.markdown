---

title: Surface RF emitter passive ranging accuracy confirmation algorithm
abstract: Kalman gain is used to calculate range accuracy for a passive angle-of-arrival determining systems, most notably for short-baseline interferometry, in which Kalman gain after arriving at a minimum proceeds to within a predetermined fraction or percent of zero gain, at which time the range estimate accuracy is known.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07764217&OS=07764217&RS=07764217
owner: BAE Systems Information and Electronic Systems Integration Inc.
number: 07764217
owner_city: Nashua
owner_country: US
publication_date: 20061013
---
This Application claims rights under 35 USC 119 e from U.S. Provisional Application Ser. No. 60 726 421 filed Oct. 13 2005 the contents of which are incorporated herein by reference.

The invention was made with United States Government support under Contract No. N00019 02 C 3002. The United States Government has certain rights in this invention.

This invention relates to electronic warfare and more particularly to algorithms for use in electronic warfare for validating range estimates.

For decades the defense business has been plagued by not having a reliable deterministic method to know when the Kalman filter solution for passive ranging application is reliable for use by the fighter pilot. This has made it hard to accurately assess when the ranging solution can be used for situation awareness and weapons use. To date ad hoc rules of thumb have been used to assess when the estimate of the Kalman filter standard deviation on range is thought to be reliable.

The use of passive sensor angle measurements to compute the location of surface and airborne radio frequency RF emitters or targets for low observable fighter aircraft is vital to ensure mission success and pilot survivability. The onboard electronic warfare sensor suite consists of multiple short baseline interferometers SBI that detect the radar emissions from the emitters in the battle space. The angle measurement accuracy is a function of emitter frequency emitter angle off array boresight SBI array length the signal to noise ratio the number of RF pulses processed by the EW system and overall array phase error. The SBI parameters consequently yield different 1 sigma values over time. Because the EW system has no control over the emitters the measurements can arrive either synchronously or asynchronously. The sensor may also be on unmanned aerial vehicles fast moving surface and sub surface vessels or helicopters.

By way of example a fighter aircraft flies straight and level with pre planned coordinated heading changes at waypoints in the mission. In the course of a mission the pilot will encounter unexpected pop up surface or airborne emitters that he needs to either avoid or respond to quickly. Pilot responses may include the use of defensive or offensive weapons or a simple change in aircraft orientation with respect to the emitter. In both cases the electronic warfare system processes SBI measurements. Sometimes the electronic warfare system will be able to regulate the measurement update rate and this can assist convergence in the passive ranging solution.

Thus for many years in passive ranging applications the location of an emitter be it an RF infrared or acoustic emitter has been determined with geolocation techniques utilized in an electronic warfare tracker in which the range and bearing to a particular emitter is ascertained. The perennial problem is that one cannot determine the reliability of the range estimate although various methods of predicting range error have been used.

Chief in these predictive methods is the use of sigma range derived from the updated state vector error covariance matrix associated with a Kalman filter. In general the sigma value is supposed to specify the reliability of the range measurement.

Whether it is a system using long baseline interferometry or other systems for ascertaining angle of arrival of radiation from a target the Kalman filter takes the noisy sensor angle measurements and in an iterative process refines or smoothes the noisy measurements and produces a derived range estimate. The result is a one over square root improvement in the angle measurement error and a consequent improvement in range estimate.

Over the many years investigators have used an updated state vector error covariance matrix derivable from the Kalman filter to estimate the range sigma value for the range estimates produced by the filter. The Kalman filter estimates the 3 state vector and converts to range by computing the square root of the sum of the squares of the state variables.

Using the latest state vector and the updated state vector error covariance matrix the Kalman filter generates an estimate of the quality of the range estimate in terms of the one sigma range value.

For instance assuming that one has a detectable target at 100 miles from a platform and further assuming a one sigma range uncertainty of 5 miles then at the platform at which the geolocation sensor is located one knows that the target is within plus or minus 5 miles around the 100 mile measured value. This gives an approximate 68 confidence level in the estimated range. If one uses a two sigma value then one is 95 confident of the range estimate falling between 90 and 110 miles about the range estimate.

The problem historically has been that over the years no one has come up with appropriate correction factors to multiply the value of sigma by so that range quality can be reliably ascertained. Many different rules of thumb have been tried without success.

In short when using the Kalman filter to passively estimate range to a stationary target there is no way of ascertaining the veracity of the tracking quality.

In the past in order to improve the sigma range value when a particular measurement has been made given known coordinates and parameters one can establish a tailored multiplier or weighting scheme for the one sigma value. However this weighting scheme is only valid for that particular scenario. Whether or not the particular weighting scheme is applicable to other scenario circumstances is never known. Unfortunately the weighting scheme can either be optimistic meaning that it gives a confidence level that is too high for the range measurement or it could be much too pessimistic. One never knows whether the weighting scheme for the one sigma range value is appropriately set by simply observing the noisy angle measurements that are processed.

One would very much like to be able to establish a confidence level that for instance for 95 of the time the range measurement is within 10 of the true range or truth. 

In summary even with the best weighting schemes for the one sigma range value this value is oftentimes too erroneous. The one sigma range value as weighted with tailored weights is oftentimes more predictable from a theoretical viewpoint when for instance the platform is an aircraft flying along a straight path over a surveilled area. Given such a scenario one can adapt the weighting scheme to make the sigma prediction correspond to reality.

On the other hand if the aircraft is executing high G turns or has a path that is non linear then the so called fudge factors that multiply the one sigma value can for instance indicate that a measured range is within 10 of truth when in fact it is only within 30 of truth.

Thus in the past and historically what investigators do is to generate a specially tailored multiplier for the sigma range value that comes out of the Kalman filter in the hope that the altered sigma metric corresponds to some sense of truth. However in the prior attempts at generating appropriate multipliers for sigma range values one does not know whether one has improved the situation. It has sometimes been said that anybody s guess for sigma is as good as anyone else s.

By way of further background the way that one traditionally computes the percent range error PRE is simply to multiply the absolute value of the difference between the true range and the range estimate by 100 then divided by the true range. One then wants to make sure that the percent range error reduces to an acceptable region for instance 10 or any intermediate value useful to the pilot and the onboard Mission Systems planning software. The reason that the sigma range value does not accurately indicate what the range error is is that the sigma value could either be too pessimistic i.e. higher than what it really should have been or it could be too pessimistic. Either way if one cannot trust one s range estimates to be accurate to say within 10 one cannot derive a particular battlefield advantage.

It will be appreciated that passively ranging against any kind of target of interest utilizes primarily azimuth only measurements. These azimuth only measurements are used to compute range with the range sensing equipment being located for instance on aircraft high speed boats patrolling a harbor or coastal region for instance for homeland security helicopters and surveillance aircraft such as E2C Hawkeye AWACS and UAVs or unmanned aerial vehicles. All of these platforms carry sensors that can measure angle to the different targets of interest which can be processed to estimate range. The key question is how does one trust the range estimate out of the angle of arrival algorithms used on such platforms.

If one can establish that the range error is for instance 10 one could accurately launch missiles drop air to ground bombs or in general deploy any type of countermeasure for which knowing the geolocation of the target is important. These geopositioning sensors which utilize angle of arrival are used not only to ascertain the geolocation of the target but also motion as well.

Rather than generating sigma range values in the subject invention one simply observes the Kalman filter gain in the X and Y directions and uses this to establish the range estimation quality.

It is noted that the Kalman filter uses an iterative process in which the filter generates weights that are applied to what is called the angle measurement residual which is the measurement value minus the filter s estimate. It is Kalman gain K which weights the difference between the measured value and the filter s estimate. The weights are iteratively applied so that this difference between the measurement and the filter s estimate is reduced. When the measured value minus the filter s estimate is zero then the range estimate is perfect. This is indicated when the Kalman gain K goes to zero.

In the subject application the angle residual is the Kalman filter s estimate of the expected new angle measurement minus the sensor s angle measurement.

Rather than using the updated state vector error covariance matrix and the companion updated state vector to compute sigma range one looks at the Kalman gain matrix which has three elements. It is a vector having an X component a Y component and a Z component. Because Z or the vertical direction does not vary and is more or less constant because the sensing platform altitude is known accurately and is small compared to the slant range to the target the z component s contribution can be ignored.

During the mission in which one wishes to establish the geolocation of an emitter the KKalman gain and the KKalman gain proceed to a minimum in which either the Kminimum or the Kminimum will be deeper i.e. larger in the absolute value sense.

In the subject system in one embodiment one selects the Kor Kthat exhibits the deeper minimum and then looks to see when that Kor Kreaches approximately zero or settles out. By settling out is meant that the value of the Kalman gain proceeds from a large minimum called a null corresponding to poor range accuracy to asymptotically approach zero when the Kalman filter is said to settle. 

If one had an extended period of time one could wait until the Kalman filter gains reached zero. However if one chooses to wait only until the minimum rises to within for instance one sixteenth of the depth of the minimum then one could rapidly establish the quality of the range measurement for instance that the range accuracy is 10 .

Using the measured value of the change in the gain matrix of the Kalman filter one can in a deterministic way reliably establish the accuracy of the range estimate without resorting to sigma range values and specifically tailored multipliers or unreliable fudge factors. 

Thus in one embodiment as a rule of thumb when the Kalman gain in either the X or Y direction settles out to between one twelfth and one sixteenth of the minimum then the range estimate is determined to be 90 accurate or has a range error less than 10 . What this means is that the system waits to see that the Kalman gain comes up from its minimum to close to zero. When one observes Kalman gain settle to one sixteenth of the minimum then one knows that the range estimate out of the Kalman filter is within about 10 of truth namely the true range.

One need no longer look at the sigma range calculation from the Kalman filter per se with its 30 years of fudge factors.

Thus by looking at Kalman gain elements alone one has a much better measure of the confidence of the measured range.

Observing the Kalman gain elements is simple as it is a direct output of the Kalman filter. Moreover it does not take an engineer to establish what the gain is merely that the gain is to be monitored. When the gain in either the X or Y direction is back to approximately zero then the range estimate is close to 100 accurate.

In short one determines the minima for both Kand Kand thereafter determines for the deeper of the minima when the gain in that particular direction settles out. When the gain settles out the smoothing associated with the Kalman filter is complete and the range estimate is within very tight tolerances.

It is interesting that this particular calculation completely eliminates the necessity of even considering sigma range the traditional way of quantifying a range accuracy. It also completely eliminates all of the fudge factor calculations that have been used to adjust the sigma range values. It completely eliminates using the update state vector error covariance matrix and its companion updated state vector to estimate range quality. In short the subject system eliminates the utilization of sigma range altogether which is a relatively inaccurate measure of the quality of the estimated range.

In summary Kalman gain is used to calculate range accuracy for a passive angle of arrival determining systems most notably for short baseline interferometry in which Kalman gain after arriving at a minimum proceeds to within a predetermined fraction or percent of zero gain at which time the range estimate accuracy is known.

Referring now to in a typical passive interferometric angle of arrival measurement system a receiver receives emissions from an emitter which may be a target. The receiver is connected to two spaced apart antennas and the spacing constituting the base leg BL.

The receiver is connected to a processor for calculating range to emitter . This processor includes a Kalman filter having as an output Kand K which are coupled to a Kalman gain determining processor that determines the Kalman gains associated with the Kalman filter processing. The Kalman gains are coupled to a unit that in essence makes a plot of Kalman gain versus time. The Kalman gains along with the timeline are coupled to a unit that determines which of the two Kalman gains Kor K has the deeper minimum. Having determined which of the two Kalman gains has the deeper minimum unit is utilized to determine when after a minimum the selected Kalman gain is within a predetermined fraction or percentage of zero.

When the selected Kalman gain Kor Kis within a predetermined fraction or percentage of zero a trigger is initiated to indicate that the range estimate from processor is valid to a predetermined accuracy in one embodiment 10 .

When the trigger is emitted from unit the percent range error of range R from processor is within the predetermined range error.

Note that processor computes the range R based on the transverse bearing spread TBS which is the absolute difference between the true range and the range estimate multiplied by 100 then divided by the true range.

The following equations indicate the range calculation that is made by processor noting that transverse bearing spread is used.

Here it can be seen that the measured sensor angles are AZand AZat times tand talong the flight path. The plane carrying antennas and travels a known distance via the onboard inertial navigation system called the Baseleg BL . The angle is the supplementary angle to AZand equals 180 AZ. The angle equals 180 minus the sum of the interior angles in the triangle and so 180 AZ . Applying the law of sines to include the desired parameter R one has the following expression.

Referring to what can be seen in this Kalman filter gain is that the Kalman gain reaches a minimum and then approaches zero such as indicated by double ended arrow . Assuming that the Kalman gain minimum is at 16 then the threshold set by unit of is set to be equal to 1 16of K. At this point the trigger signal emitted by unit of indicated by arrow establishes that the range estimate R from processor of is within a prescribed range error.

Referring to these figures show only one Extended Kalman Filter EKF gain matrix element to keep figure uncluttered. Both Kand Ktend to follow each other. shows by graphs that when the emitter is more down range and closer to the flight path the Kterm dominates over the Kterm . shows by graphs when the emitter is more cross range and closer to the right wing of the aircraft i.e. near the point of closest approach PCA the Kterm dominates over the Kterm . Here both Kand Kgo through a minimum and and then to a maximum and the amplitude being a function of the sensor measurement accuracy for azimuth.

While the present invention has been described in connection with the preferred embodiments of the various figures it is to be understood that other similar embodiments may be used or modifications or additions may be made to the described embodiment for performing the same function of the present invention without deviating therefrom. Therefore the present invention should not be limited to any single embodiment but rather construed in breadth and scope in accordance with the recitation of the appended claims.

