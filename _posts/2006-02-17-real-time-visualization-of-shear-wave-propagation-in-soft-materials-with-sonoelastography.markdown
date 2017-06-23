---

title: Real time visualization of shear wave propagation in soft materials with sonoelastography
abstract: An ultrasound system visualizes shear wave propagation in real time by slowing down the propagation of the shear wave as seen by the ultrasound probe. The shear wave source propagates shear waves into the medium at a frequency ω. The ultrasound probe is vibrated by a vibrator at the frequency ω−Δω, where Δω is much smaller than ω. The wave propagation as seen by the ultrasound probe is slowed down by a factor Δω/ω. An appropriate value of Δω allows real-time visualization of the wave propagation. Variations include electronically producing a virtual vibration and the use of multiple shear wave sources.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07444875&OS=07444875&RS=07444875
owner: University of Rochester
number: 07444875
owner_city: Rochester
owner_country: US
publication_date: 20060217
---
The present application claims the benefit of U.S. Provisional Patent Application No. 60 653 987 filed Feb. 18 2005 the disclosure of which is hereby incorporated by reference in its entirety into the present disclosure.

The work leading to the present invention was supported by the National Institutes of Health under Grant No. 2R01 AG16317 01A1. The government has certain rights in the invention.

The present invention is directed to a technique for sonoelastography and more particularly to such a technique in which shear waves are caused to interfere to produce a stationary or slowly moving wave from which the shear wave velocity can be determined.

It is widely accepted that the changes in elasticity of tissues are possible markers of certain diseases. In modern medicine digital palpation is a routine screening method in physical examinations. One approach to examine the tissues local elasticity is to visualize the local behavior of shear waves excited by internal or external sources.

A common approach to doing so is through an ultrasonic imaging modality called sonoelastography. Sonoelastography estimates the peak displacements of particle motion under audio frequency excitations by analyzing the power spectrum variance of the ultrasound echoes which is proportional to the local vibration amplitude. Vibration fields are then mapped to a commercial ultrasound scanner s screen.

However since the shear wave speed in soft tissues is on the order of a few meters per second few imaging modalities are able to follow the propagation on a scale of a centimeter or less. The existing techniques to follow the shear wave propagation either have a very high temporal sampling rate high frame rate or carefully subsample the propagation progressively also known as the strobe effect . Such available systems either require off line computing or prolonged data acquisition. Therefore those techniques are not real time.

It is still another object of the invention to develop such a technique which does not require a high frame rate or strobing. 

It is yet another object of the invention to develop such a technique in which the ultrasound scanner can run asynchronously from the vibration as a normal Doppler imaging sequence.

It is yet another object of the invention to develop such a technique which can be implemented with a single shear wave source.

It is yet another object of the invention to develop such a technique which does not assume any particular type of propagation of the shear wave in the medium.

To achieve the above and other objects the present invention is directed to a technique for visualizing the shear waves in soft tissues in real time in which wave propagations are virtually slowed down for observations. The spatial distribution of the shear wave speed can be reconstructed from the wave propagation video and therefore indicates the size and location of the stiff region in the tissue. The present invention provides many of the advantages of magnetic resonate elastography MRE but with the additional advantages of real time visualization of the vibration fields.

One shear wave source propagates shear waves into the medium at the frequency . An ultrasound US probe is held above the surface of the medium. The ultrasound probe is vibrated by a vibrator at the frequency where is much smaller than .

The total field estimated by the ultrasound scanner is the shear wave propagation relative to the probe vibration which is called the modulated field. The modulated field is a representation of the propagating shear wave field only at a different frequency and thus different velocity. By carefully selecting and the shear wave propagation can be virtually slowed down so that it can be visualized by sonoelastography.

The present invention is validated in both a homogeneous phantom experiment and an inhomogeneous phantom experiment. The present invention provides many of the advantages of magnetic resonate elastography MRE but with the additional advantages of real time visualization of the vibration fields.

Since the present invention can use the existing Doppler hardware on most modern US scanners the frame rate of sonoelastography is as high as other Doppler modalities. In one example regions where the vibration amplitude is low are displayed as dark green while regions with high vibration are displayed as bright green.

The present invention offers a further advantage in that it does not assume any particular type of wave propagation for example it does not assume a plane wave. The vibration of the probe is completely temporally dependent and does not interfere with the spatial variation of the propagation of the shear wave. The present invention offers yet another advantage in that only one shear wave source is needed.

Variations include electronically producing a virtual vibration of the probe and the use of multiple shear wave sources.

The following disclosures disclose aspects of the invention and are hereby incorporated by reference in their entireties into the present disclosure 

Zhe Wu et al Sonoelastographic imaging of interference patterns for estimation of the shear velocity of homogeneous biomaterials 49 2004 911 922 and

Zhe Wu Shear Wave Interferometry and Holography an Application of Sonoelastography submitted in partial fulfillment of the requirements for the degree of Doctor of Philosophy Department of Electrical and Computer Engineering University of Rochester Rochester N.Y. 2005.

A preferred embodiment of the invention will be set forth in detail with reference to the drawings in which like reference numerals refer to like elements or steps throughout.

where vis the shear wave phase velocity and s x is the first derivative of s x with respect to x. s x is the local wave number or the local spatial frequency. Thus if one can visualize s x and its movement over time then one can determine v which is directly linked to the stiffness of tissue 

While transmitting and receiving ultrasound signals the ultrasound probe is also externally vibrated. The ultrasound probe is carefully positioned above the soft material without touching it. A thick layer of ultrasound gel is applied to couple the acoustic energy into the soft material . The ultrasound probe is carefully positioned so that there is always an ultrasound gel filled gap between the probe and the surface of the medium to make sure the vibration of the US probe does not propagate shear waves into the phantom. Signals received by the US probe are processed in an image processing device in a manner to be described below to produce images that are displayed on a video display or output in any other suitable manner.

The particle motion relative to the ultrasound probe is estimated by the sonoelastography algorithm. The ultrasound probe is vibrated at a frequency where 

Since the shear wave is mechanically modulated by the ultrasound probe motion P x t is called the modulation wave. Similarly to equation 2 the phase velocity of the modulation wave is

Also notice that the mechanical modulation does not interfere with the spatial component of equation 1 i.e. s x . Therefore the exact shear wave appearance is preserved. Apart from a DC shift in the amplitude and a change in the velocity the shear wave propagation is exactly represented by the modulation wave. Since is an arbitrary and controllable factor the shear wave can thus be slowed by the mechanical modulation to be studied by ordinary ultrasound scanners with the sonoelastography modifications.

In the validating experiments a double channel signal generator Tektronix AFG320 produces two monochrome low frequency signals at slightly different frequencies. One channel of the signals 199.9 Hz drives a bending piezo elements known as Thunder Face International Corporation Norfolk Va. which is applied to vibrate the US transducer. The other channel of the signal 200 Hz drives a shear wave actuator Piezo System Massachusetts which propagates shear waves into a Zerdine CIRS Virginia ultrasound phantom. The phantom has a hard inclusion and is otherwise uniform. A GE Logiq 700 which has been specially modified to implement the sonoelastography functions is applied to visualize the modulation wave propagation. With the realtime visualization the shear waves are virtually slowed down so that the local and subtle behaviors of the waves can be examined closely. The different wave speeds within and outside of the lesion can be perceived by the human eye. One frame of the modulation wave propagation is shown in . The shear wave wavefronts are visibly distorted by the hard inclusion and thus the size and the location of the lesion is estimated.

There are a number of existing techniques from MRE and other methods for calculating vfrom s x t . Those can be optionally applied to the present invention as post processing to create images of local v. As an example the local frequency estimator LFE filter bank estimates the local spatial frequency which is inversely proportional to the local shear wave speed. Because of the low signal to noise ratio SNR nature of ultrasonic image acquisition a series of procedures are proposed to reduce the noise and to increase the SNR. First of all the local vibration phase at each pixel is estimated from the wave propagation video 

Because the phase estimation results are always between and a phase unwrapping procedure is necessary to create a smooth phase surface. A wrapped phase estimation is depicted in and depicts an unwrapped phase surface. The phase unwrapping procedure eliminates the sharp transitions in the original phase map to ensure that any subsequent noise reduction procedure does not blur the edges. After noise reduction the unwrapped phase map is converted to the wave patterns with artificially increased spatial density cos 11 

where N is an arbitrary constant which is typically chosen from 2 to 20. shows a reconstructed wave pattern with N 12. That operation virtually increases the number of wavefronts per unit area. That reconstruction enhances the visibility of the low spatial frequency area which corresponds to the location of the stiff inclusion. Furthermore the LFE filter bank is applied over the wave patterns to estimate the local spatial frequency. The local wave speed distribution which is inversely proportional to the local frequency is then displayed as shown in .

The phantom includes an area of high elasticity surrounded by an area of low elasticity. The area of high elasticity is shown in as an area of low spatial frequency and in as a bright area surrounded by a dark area. In an organ such as a prostate a lesion is imaged in the same manner by imaging the change in elasticity between the lesion and surrounding healthy tissues.

The estimator accuracy will now be considered. It will be seen from the above that final estimation results rely extensively on the phase estimation of lical vibration. The local vibration phase is estimated by tracking the brightness variation at each pixel as shown in . The lower bound of the wave velocity error will be formulated and an example with realistic values will be given.

Assuming that the signal includes white Gaussian noise the discrete pixel value over multiple observations multiple frames of the wave video can be written as cos 14 

where C x A D 2A x s x and w n 0 a zero mean Gaussian distribution with standard deviation . Therefore the likelihood function is

If an integer or half integer number of cycles is acquired in experiments by choosing N m m being an integer then the expected value of the cosine term is zero cos 2 2 0 19 

The local shear wave velocity estimation is equivalent to estimating the local slope of the phase function. At that stage the tradeoff of image resolution and estimation accuracy has to be considered. If the image resolution is set to be M pixels the accuracy of the slope estimation of bounded by a function of M. If the problem is modeled as a line fitting problem and the phase function is assumed to be in the form of 22 

where w m is a zero mean Gaussian distribution with variance determined by equation 21 with independent observations at those M pixels than the slope estimation G can be obtained with variance

Because stiff regions are generally more important than the normal background more attention is to be paid to the estimator accuracy in the stiff regions. The vibration amplitude is low in those regions because of the sonoelastography effect thus the signal to noise ratio SNR is also low. An empirical estimate of the SNR in the stiff regions is one. In the experiments a typical number of frames of the shear wave propagation video is 60. Thus in equation 21 the variance of the phase estimation is approximately 1 30.

M in equation 23 refers to the number of independent measurements. The ultrasound scanner determines that only one independent measurement can be made within the width of the point spread function. A point spread function is simulated with the Field II tool box. The imaging system parameters are selected from a typical experimental setting and are summarized in Table I below 

The simulation shows that the 6 dB width of the point spread function in the lateral direction is approximately 0.5 mm as shown in . Assuming a realistic shear wave speed of 4 m s and a driving frequency of 200 Hz the relation between the elasticity estimation resolution and the estimation relative error will be discussed.

If the resolution is chosen to be 2 mm there are four independent measurements within that length. According to equation 23 

Since the phase increase is 2 over one shear wave wavelength the phase slope may be estimated in terms of the wavelength by 

The tradeoff between the elasticity image resolution and the estimation relative error is plotted in . Equation 23 provides a lower bound of the estimation accuracy. In practice that lower bound may not be achievable and the error in practice may be higher.

Variations of the preferred embodiment are possible. For instance physical vibration of the ultrasound probe can be replaced with virtual probe motion in which the image processing device electronically processes the ultrasound signals from the ultrasound probe at an adjustable frequency to simulate the vibration of the ultrasound probe . Such processing can include complex rotation or temporal shifting on the ultrasound signals. In another variation in addition to or instead of the probe motion whether physical or virtual multiple shear wave sources are provided to introduce multiple shear waves at the same or different frequencies to create shear wave interference in the tissue.

While a preferred embodiment and variations thereof have been set forth in detail those skilled in the art who have reviewed the present disclosure will readily appreciate that other embodiments can be realized within the scope of the invention. For example numerical values are illustrative rather than limiting as are disclosures of specific equipment and technology. Therefore the present invention should be construed as limited only by the appended claims.

