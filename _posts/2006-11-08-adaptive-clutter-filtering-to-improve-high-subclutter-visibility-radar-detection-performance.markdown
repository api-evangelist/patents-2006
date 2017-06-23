---

title: Adaptive clutter filtering to improve high sub-clutter visibility radar detection performance
abstract: In an aircraft-mounted Doppler radar clutter rejection system, a flexible, sharp band pass filter uses Taylor weighting, an FFT and a module for selecting which of the Doppler cells are to be activated, thus to control the band pass characteristic and set the clutter line to the speed of the aircraft.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07548187&OS=07548187&RS=07548187
owner: BAE Systems Information and Electronic Systems Integration Inc.
number: 07548187
owner_city: Nashua
owner_country: US
publication_date: 20061108
---
This Application claims rights under 35 USC 119 e from U.S. Application Ser. No. 60 734 902 filed Nov. 9 2005 the contents of which are incorporated herein by reference.

This invention was made with United States Government support under Contract No. N00019 87 C 0138 with the Navy. The United States Government has certain rights in this invention.

This invention relates to electronic countermeasures and more particularly to a method and apparatus for filtering out Doppler ground clutter returns.

For a number of years active Doppler radars have been used to detect incoming missiles which are fired at a platform and to cue appropriate countermeasures. One of the major problems to eliminate false alarms on ground clutter is to be able to ignore the returns from objects on the ground that are reflecting back the radar pulses to the platform. The reflected signals from the ground clutter exhibit a Doppler shift reflecting the velocity or speed of the aircraft that is overflying the region. In the past this was accomplished by elimination or removal of signals having a Doppler shift equal to or lower than the maximum speed of the aircraft. This meant utilizing analog crystal filters having a fixed band pass.

If for instance the platform was flying at a maximum of 600 knots then it was the purpose of these filters to filter out anything that had a Doppler frequency shift indicative of movement equal to or less than the 600 knot ground speed of the aircraft. Normally since incoming missiles would approach the platform at speeds much higher than the maximum speed of the aircraft relative to the ground filtering out Doppler shifts indicating speeds equal to or less than the maximum speed of the aircraft was effective to eliminate the ground clutter from detection or contention in determination of the presence of a threat.

The problem with such fixed analog filters is that tailoring the response to reject ground clutter utilizing the maximum speed of the aircraft denied the flexibility required when the aircraft reduced its speed from its maximum value to some lower value.

For instance if the filters were designed to reject Doppler shifts equal to or lower than 400 knots when the aircraft was flying at 100 knots any Doppler returns indicating speeds between 100 knots and 400 knots would be rejected. Thus an incoming missile with a closing velocity between 100 and 400 knots would be ignored.

In short there was a necessity for providing an inexpensive system to be able to adaptively change what is referred to herein as the clutter line which refers to the Doppler shift associated with the actual ground speed of the aircraft rather than its maximum speed. This type of flexibility would result in the detection of incoming missiles or threats having a Doppler shift associated with a speed or velocity less than the maximum speed or velocity of the aircraft.

More particularly Doppler radar detection systems are located on moving platforms which are utilized to transmit pulses into a scanned area and to receive back reflected energy. The energy includes energy that may be reflected from a high speed missile but more often includes back clutter which is energy that bounces off the ground and is reflected back with a Doppler shift reflecting the relative motion of the aircraft to the ground.

The problem is to be able to detect incoming missiles approaching the platform and to be able to deploy countermeasures. It is noted that the incoming missile has a Doppler shift associated with its approaching velocity. If that velocity is above the velocity associated with the clutter then one can easily filter out the clutter. To do this analog filter crystals have been employed. However these filters are very expensive heavy and have fixed filter characteristics.

Note the analog crystal filters define a clutter region to be rejected such that the remaining energy if it is above the Doppler frequency of the clutter would then be detectable.

Active radar systems in the past also utilized a number of different range gates so as to be able to limit for consideration only specific ranges from the platform. Each of these range gates would then be assigned different clutter filters with the range gate basically defining where the platform thinks that the incoming missile is.

Thus in the past there were two types of filtration to eliminate false alarms. One was range gating such that the system would eliminate consideration of returns from objects at ranges other than a predetermined range and secondly to process the output of the range gate to eliminate consideration of any Doppler shifts that were less than or equal to the maximum ground speed of the aircraft. In short these filters would be high pass filters that would pass all the Doppler frequencies above the Doppler shifts associated with the clutter. Thus all energy below the clutter line would be rejected leaving all the frequencies above the clutter line to detect fast moving threats approaching the platform.

It is noted that ground clutter rather than having a single Doppler shift associated with it generally includes large structures that provide returns that indicate not a single Doppler shift but a range of Doppler shifts. This is due to the particular geometry between the platform and the ground clutter object as well as the different angles at which the reflected radar pulse is received at the platform.

It is noted that the closing speed of a missile is in a range on the order of hundreds to thousands of meters per second in which the highest Doppler shift is around 15 kilohertz given for instance a one gigahertz L band radar.

It is noted that the Doppler shift could be significantly lower namely for instance possibly between 3 kilohertz to 15 kilohertz depending on the particular type of missile.

In these early systems the analog crystal filters would simply eliminate Doppler shifts below some particular Doppler shift in general that associated with the maximum speed of the aircraft involved.

However such active radar protection could be deployed on such diverse aircraft as unmanned aerial vehicles fixed wing subsonic aircraft rotary wing aircraft or supersonic aircraft.

Choosing or designing the analog crystal filters for the maximum speed of multiple aircraft presented a problem in that they had to be redesigned for each aircraft into which they were to be installed.

Moreover in addition to the cost of the crystal filters they are relatively large in some instance being 3 by 5 inches and an inch thick. With a half a dozen of such filters they occupy a significant amount of rack space. This is a significant drawback when active radars are deployed on unmanned aerial vehicles. Moreover the filters themselves may be several thousands of dollars each and one is essentially stuck with a fixed velocity assuming that the filters are cut for the maximum velocity of the aircraft. Additionally these filters were of a sub octave type which limited the range Doppler combination. A sub octave filter is basically a filter where the ratio of the lowest frequency it passes to the highest frequency it passes is less than two. Thus they are relatively narrow banded and were not easily adapted to aircraft of differing maximum speeds.

Additionally inherent to the high pass band to transition band ratio of the crystal filters is long ring or settling time leading to an elevated false alarm rate. In order to deal with the long ring time designers typically had to raise the detection thresholds which would mean giving up some systems sensitivity. Note that when one increases the detection threshold one basically decreases the range at which one can detect an incoming missile.

For purposes of the subject invention clutter frequency is defined as the Doppler shift associated with fixed objects on the ground relative to the moving platform.

Also by way of definition the clutter spectrum is defined in a Doppler sense as the maximum plus or minus Doppler shift frequency associated returns from ground objects. The reason that there is a clutter spectrum is that one has scatterers behind the platform and scatterers in front of the platform. Thus one obtains a clutter spectrum that has both plus and minus Doppler shift. In one worst case scenario involving a supersonic platform one might have a clutter spectrum as wide as 4 kilohertz. The clutter spectrum is important because it defines the range of the Doppler frequency shifts one wants to reject.

By setting whatever filters are used to reject Doppler shifts below the speed of the aircraft one can set the filters to at least reject as much as 4 kilohertz of Doppler shift clutter.

Rather than utilizing fixed analog crystal filters with their inflexibility weight and cost in the subject invention one uses a Fourier transform windowing technique to create a sharp band pass filter with moveable edges. In one embodiment of the subject invention a Taylor weighting system windows the output of a range gate samples prior to performing an FFT to create a series of side by side Doppler cells or filters that constitute the band pass filter. The weights allow one to dial in the rejection that one would like. In this particular application the use of the Taylor weights enables one to dial in a Fourier transform filter response that has a minus 110 dB side lobe rejection. This means that one can provide a band pass filter with exceedingly high rejection characteristics.

Thus rather than having to design for the maximum speed of the aircraft one can sense the speed of the aircraft and automatically select which of the Doppler cells from the FFT to enable for target detection processing. Only the Doppler cells associated with Doppler shifts greater than Doppler shift associated with the forward speed of the air vehicle are enabled for target detection. This means that the system can be instantly reconfigured or tailored to the actual speed of the aircraft as opposed to the maximum speed of the aircraft. If the air vehicle speeds up the Doppler frequency of clutter line increases the Doppler cells that the clutter energy has moved into must now be deactivated for target detection processing. If the air vehicle slows down the Doppler frequency of the clutter line decrease the Doppler cells the clutter energy has vacated can now be activated for target processing.

What this allows one to do is to select the Doppler cells or filters that are just above the frequency from the clutter line so that if the aircraft speeds up one deactivates the Doppler cells corresponding to the Doppler frequency shifts to the left of the Doppler frequency associated with the increased speed. This moves up the left edge of the band pass filter to the right to match the actual aircraft speed. On the other hand if the aircraft slows down then one activates additional Doppler cells to move the left hand edge of the band pass filter to the left to match the reduced speed of the aircraft.

Thus with the utilization of analog crystal filters one always had to set the clutter line to be at the highest anticipated forward speed of the aircraft. This meant that if one was going slower than maximum speed one might have a missile approaching the aircraft below the maximum speed which was rejected as clutter.

With the subject invention one is able to select the number of usable Doppler cells or filters and thus define the left hand band pass filter edge.

Assuming a 128 point FFT then one might select 80 of the side by side Doppler cells or filters as being usable with the left most filter of the 80 filters defining the left hand edge of the pass band. Note the other Doppler filters define the bandwidth of the band pass filter.

However if the aircraft slows down the clutter line may move for instance 500 hertz. This means that one would activate additional Doppler filters to the left of the left most filter for instance for a total of 85 activated filters.

This essentially adds capacity to detect a closing missile regardless of the maximum speed at which the platform is capable of flying. Thus the filtering system is optimized to detect incoming objects that come up to the slowing platform.

In summary in an aircraft mounted Doppler radar clutter rejection system a flexible sharp band pass filter uses Taylor weighting an FFT and a module for selecting which of the Doppler cells are to be activated thus to control the band pass characteristic and set the left band pass edge that defines the clutter line to the speed of the aircraft.

Referring now to an aircraft serves as a platform for an active radar having an antenna that projects pulses towards the ground .

Various stationary structures on the ground such as for instance trees structures buildings or trees cause energy from radar antenna to be scattered back towards the aircraft.

Since the aircraft has a ground speed associated with its travel if one graphs Doppler frequency versus amplitude one can see that trees have a Doppler shift that is to the right of the zero Doppler shift frequency and is not a single line but rather is spread out indicating the different geometries associated with different elements of the tree relative to the aircraft. Likewise structure has a broadened profile for its returns as does building .

It is noted that aircraft is traveling towards each of these ground features such that the Doppler shift is positive with respect to the aircraft platform. However as can be seen by trees they are behind aircraft and therefore their Doppler shift is in a negative direction.

Also shown at is the ground scattering which results when the ground is irradiated with the radar pulses. It will be seen that the amplitude of the returns from structures on the ground exceeds that of the ground clutter relating to the ground itself.

The purpose of the subject invention is to be able to reject or eliminate the effects of detected Doppler shifts due to stationary structures on the ground or the ground itself.

In order to accomplish this in the past and referring now to an active radar antenna is used to receive returns from the scene of . These returns are heterodyned at and then low pass filtered at at which point they are heterodyned again at . This effectively heterodynes the incoming signal to base band where the signal is applied to a bank of analog crystal clutter filters .

These are relatively sharp fixed band pass filters that define band passes and with a clutter edge being set to the Doppler shift that is associated with the maximum ground speed of the aircraft.

The output of these filters is sampled by a switch to apply the output of the filters to a traditional Doppler processor that detects the presence of a incoming missile or target as illustrated at .

As mentioned hereinbefore the problem is that the crystal clutter filters aside from being expensive and heavy as well as occupying a relatively large amount of rack space are fixed as to the clutter line. The clutter line is factory pre set to correspond to the Doppler shift associated with the maximum ground speed of the particular aircraft involved.

As will be seen if the aircraft is not flying at its maximum ground speed but rather at some lower speed then the Doppler shift frequency clutter cutoff will be set too high and the signals of interest namely the returns from the missile may be cut off by the pre set band pass filter characteristic.

Thus for instance if clutter line determined by a fixed filter is set to for instance 400 knots and the aircraft slows to for instance 200 knots then for approaching missiles having a closing velocity of between 200 and 400 knots the Dopplers associated will be rejected by the filters.

It is for this reason that adaptability and flexibility needs to be designed in active radar systems so as not to arbitrarily leave voids in the Doppler frequency shifts that can be utilized to detect an incoming missile.

Referring now to in the subject system incoming reflected pulses are detected at antenna which are heterodyned at and then passed through a low pass filter whereupon they are analog to digital converted at and then further heterodyned at prior to being applied to a series of range gates . The base band data in each of the range gates is sequentially applied to a Taylor window which for each range bin weights the data with Taylor window weights W for each range gate. This weighted data is then coupled to a fast Fourier transform algorithm which in one embodiment is a 128 point fast Fourier transform.

It is the function of the Taylor window to provide weights to a particular range bin or gate. If each range bin or gate is designed to store 128 pulses making up the range gate measurement then one multiplies each of the values of the pulses by the 128 Taylor window coefficients so as to apply a weighting factor to each of the pulses. These pulses are then coupled to a 128 point FFT that is provided with the band pass characteristic by selecting which of the side by side Doppler cells or filters that are output from the FFT 66 are active to define the band pass.

It will be appreciated that the FFT produces a large number of Doppler cells that span a frequency range of between PRF 2 and PRF 2 where PRF is the pulse repetition frequency. Thus the FFT does a complete spectral analysis of the incoming signal and provides as its output the levels of the incoming signal at its various frequency bins.

However as can be seen in the Doppler forward speed of the aircraft is derived from the sensed aircraft speed over ground. The forward ground speed is converted to a Doppler shift. Doppler cell selector selects a number of Doppler cells to define the band pass characteristic of the band pass filter and especially the left hand edge which is a Doppler shift matching the aircraft ground speed Doppler shift. This Doppler shift is illustrated at arrow and it is this Doppler shift frequency that defines clutter line .

Below the clutter line the system de selects any Doppler cells or filters so that any Doppler shifts that come in below the Doppler shift indicated at will be rejected.

In this manner any incoming missile that has a speed relative to the aircraft that is above the Doppler shift associated with the ground speed will be detected by the selected Doppler cells . What this means is that a target will be detected in the region by double ended arrow .

Referring now to the effect of using the Taylor window weighting and FFT Doppler cell processing is to provide a band pass filter having a band pass characteristic . This band pass characteristic has a right edge and a left edge .

It is the purpose of the subject invention to be able to accurately select left edge and make it coincident with the sensed ground speed of the aircraft such that if the maximum speed of the aircraft is illustrated at then the band pass filter characteristic is as illustrated by dotted line .

However if the aircraft slows to a speed then left edge of the band pass filter edge is lowered in frequency.

Rather than utilizing fixed high Q narrow band crystal filters the subject system provides very sharp skirts for the band pass characteristic while at the same time being able to move the left hand side of the characteristic to correspond in frequency to the Doppler frequency shift associated with the actual speed of the aircraft.

How this is done is shown in . Here it can be seen that the band pass characteristic is achieved by selecting Doppler cells or filters to fill up the area between right edge and left edge so that signals within this frequency range will be passed by the band pass filter.

By de selecting Doppler cells one creates a Doppler shift rejection zone where ground clutter is rejected. Note that the aircraft speed determines the left most of the Doppler cells to be selected such that Doppler cell is that Doppler cell which is associated with the Doppler shift corresponding to the ground speed of the aircraft.

Referring to if the aircraft slows down one seeks to alter the band pass characteristic so that it corresponds to band pass characteristic of . Thus arrow is moved to the left of the aircraft speed illustrated by arrow in . Since aircraft Speed corresponding to arrow is slower than aircraft Speed corresponding to arrow one needs to add Doppler cells or filters .

By adding the Doppler cells or filters one can achieve band pass coverage from the maximum ground speed as illustrated in to the actual lower ground speed as illustrated in whereby target or missile returns having Doppler velocities in this region will be detected as opposed to being rejected as would be the case with fixed analog crystal filters.

What this filtering system does is to be able to ignore any Doppler shifts that are less than the sensed forward ground speed of the aircraft. Thus in the subject system the Doppler cells are selected to be only corresponding to those Doppler shifts above the instantaneous ground speed of the aircraft.

As can be seen from the output of the FFT includes Doppler cells with the energy in the Doppler cells being applied to a threshold circuit . Any outputs exceeding the threshold indicate an incoming missile or threat.

Note that by adjusting the weighting one determines the depth of the band pass edge rejection. Note also that the Taylor weighting results in monotonic uniform side lobes. If one pushes the side lobes down by setting the weights to a maximum rejection for instance of 110 dB the main lobe grows. Thus the weighting determines the frequency response for the Doppler bin.

Referring now to a curve that specifies the Taylor weights is shown at to be the weights for range gate samples . In one embodiment there are 128 range gate samples. Each one of the range gate samples represents a single returned pulse at a given range. Thus the 128 pulses are time domain representations of the radar return. Each of these samples is multiplied by a Taylor weighting coefficient that has the general shape of curve shown in . In actuality continuous curve is composed of 128 discrete weights with the pulses at the discrete time points multiplied by the appropriate weight. These weighted range gate samples are then input to the 128 point FFT which results in the frequency versus amplitude characteristic for each Doppler cell or filter shown at in . As will be seen this is a characteristic of a very narrow filter having steep skirts and . Note the Taylor filter characteristic does not have any ripples and the pass band is basically a single hump.

The result of weighting the time domain data with a Taylor window is a frequency versus time response for each of the individual Doppler cells or filters. One can characterize the output of the FFT as being a band pass filter whose filter characteristic is that composed of the side by side Doppler cells that resemble comb lines associated with a filter bank of evenly spaced filters.

The result for each of the Doppler cells or filters is that each has very steep edges or skirts and uniform monotonic side lobes deeply suppressed.

While the present invention has been described in connection with the preferred embodiments of the various figures it is to be understood that other similar embodiments may be used or modifications or additions may be made to the described embodiment for performing the same function of the present invention without deviating therefrom. Therefore the present invention should not be limited to any single embodiment but rather construed in breadth and scope in accordance with the recitation of the appended claims.

