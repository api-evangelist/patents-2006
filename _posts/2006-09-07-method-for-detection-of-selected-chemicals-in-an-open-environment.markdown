---

title: Method for detection of selected chemicals in an open environment
abstract: The present invention relates to a space-invariant independent component analysis and electronic nose for detection of selective chemicals in an unknown environment, and more specifically, an approach to analysis of sensor responses to mixtures of unknown chemicals by an electronic nose in an open and changing environment. It is intended to fill the gap between an alarm, which has little or no ability to distinguish among chemical compounds causing a response, and an analytical instrument, which can distinguish all compounds present but with no real-time or continuous event monitoring ability.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07640116&OS=07640116&RS=07640116
owner: California Institute of Technology
number: 07640116
owner_city: Pasadena
owner_country: US
publication_date: 20060907
---
The present application is a non provisional utility application claiming benefit of priority of U.S. Provisional Patent Application No. 60 715 353 filed Sep. 7 2005 titled Smart Enose for Chemical Detection in the Open Environment. 

The invention described herein was made in the performance of work under a NASA contract and is subject to the provisions of Public Law 96 517 35 USC 202 in which the Contractor has elected to retain title.

The present invention relates to a space invariant independent component analysis and electronic nose for detection of selective chemicals in an unknown environment and more specifically to an approach to analysis of sensor responses to mixtures of unknown chemicals by an electronic nose in an open and changing environment.

The need for low power miniature sensor devices that can monitor air quality in an enclosed space with multi compound capability and minimum human operation led to the development of a polymer carbon composite based electronic nose ENose at NASA s Jet Propulsion Laboratory JPL . The sensor array in the JPL ENose consists of 32 conductometric sensors made from insulating polymer films loaded with carbon. In its current design it has the capability to detect 10 common contaminants which may be released into the recirculated breathing air of a space shuttle or space station released from a spill or a leak target concentrations are based on the 1 hour Spacecraft Maximum Allowable Concentrations SMAC set by NASA depicted in and are in the parts per million ppm range. The ENose was intended to fill the gap between an alarm which has little or no ability to distinguish among chemical compounds causing a response and an analytical instrument which can distinguish all compounds present but with no real time or continuous event monitoring ability.

As in other array based sensor devices the individual sensor films of the ENose are not specific to any one analyte it is in the use of an array of different sensor films that gases or gas mixtures can be uniquely identified by the pattern of measured response. The response pattern requires software analysis to deconvolute gas compounds and their concentrations.

What is needed is a method of detection for selective chemicals as a result of leaks or spills of specific compounds. It has been shown in analysis of samples taken from space shuttle flights that in general air is kept clean by the air revitalization system and contaminants are present at levels significantly lower than the SMACs the ENose has been developed to detect target compounds released suddenly into the breathing environment. A leak or a spill of a solvent or other compound would be an unusual event.

What is needed is an approach to analysis of sensor responses to mixtures of chemical compounds so that use of the ENose may by extended to detect chemical compounds in an open and changing environment such as a building or a geographical area where air exchange is not controlled and limited. In an open environment the collected sensory data will be comprised of a mixing between unknown chemicals with unknown mixing levels coefficient between them. The identification of chemical compounds among these mixing chemicals is a challenge for real world applications.

To determine whether a chemical compound exists in the an environment one of the most well known techniques is to recover the original chemicals. When done the detection can be an easy step by determining the minimum phase between the predicted original reactants and the target chemicals. A more sophisticated method is to use a neural network approach which can be employed to capture the target chemicals in various conditions e.g. concentration levels through the parameterized weight set. Then the strongest correlation between parameterized weight and the predicted original can be used to identify the intended chemical.

Recently Independent Component Analysis ICA has proven effective to not only de correlate second order statistics of the signals but also reduce higher order statistical dependencies. ICA transforms an observed signal vector into a set of signals that are as statistically independent as possible. Theoretically ICA is an information theoretic approach which exploits concepts from information theory such as entropy and mutual information.

The ICA roots in the early work of Herault and Jutten who first introduced an adaptive algorithm in a simple feedback architecture that was able to separate several unknown independent sources. ICA was further developed and recent improvements used natural gradient descent based on the Riemannian metric tensor to optimize the curvature of a particular manifold in n dimensional space. This technique is employed to apply to the Infomax to simplify the learning rule used here. ICA has applications for feature extraction in speech recognition systems in communication systems in medical signal processing and in image processing.

Therefore what is needed is an ICA method for detection of selective chemicals in an unknown environment using an electronic nose.

The present invention relates to a space invariant independent component analysis and electronic nose for detection of selective chemicals in an unknown environment and more specifically to an approach to analysis of sensor responses to mixtures of unknown chemicals by an electronic nose in an open and changing environment.

In one aspect of the present invention a method for detection of chemicals in an open environment comprises the acts of obtaining sampled data by sampling data from a database containing air samples of an unknown open environment utilizing an electronic nose sensor array containing a plurality of sensors evaluating the sampled air over a plurality of time intervals partitioning the sampled data with respect to each time interval into a subset sampling a subset of the sampled data with respect to time for each sensor calculating operating points of the subset of the sampled data as the averaged value e.g. mean value of the subset of the sampled data linearizing the subset of the sampled data using the operating points determining a data distribution corresponding to the linearized subset of the sampled data performing an independent component analysis ICA on the linearized subset of the sampled data by using the data distribution wherein the ICA generates independent component vectors recovered sources representing the subset of the sampled data sampling known chemical elements representing spectral vectors from a database iteratively performing an act of projecting the independent component vectors recovered source representative of the subset of the sampled data onto the independent component vectors of the known chemical elements wherein the step of projecting further comprises the steps of finding a correlation between the independent component vector of a subset of the sampled data and the spectral vectors of the known chemical elements finding a maximum correlation point on the correlation and a known chemical element corresponding to the maximum correlation point creating a list of chemical elements detected on the subset of the sampled data wherein a known chemical element corresponding to the maximum correlation point is added to the list of chemical elements detected outputting the list of chemical elements detected on the subset of the sampled data.

The present invention relates to a space invariant independent component analysis and electronic nose for detection of selective chemicals in an unknown environment and more specifically to an approach to analysis of sensor responses to mixtures of unknown chemicals by an electronic nose in an open and changing environment.

The following description taken in conjunction with the referenced drawings is presented to enable one of ordinary skill in the art to make and use the invention and to incorporate it in the context of particular applications. Various modifications as well as a variety of uses in different applications will be readily apparent to those skilled in the art and the general principles defined herein may be applied to a wide range of embodiments. Thus the present invention is not intended to be limited to the embodiments presented but is to be accorded the widest scope consistent with the principles and novel features disclosed herein. Furthermore it should be noted that unless explicitly stated otherwise the figures included herein are illustrated diagrammatically and without any specific scale as they are provided as qualitative illustrations of the concept of the present invention.

In the following detailed description numerous specific details are set forth in order to provide a more thorough understanding of the present invention. However it will be apparent to one skilled in the art that the present invention may be practiced without necessarily being limited to these specific details. In other instances well known structures and devices are shown in block diagram form rather than in detail in order to avoid obscuring the present invention.

The reader s attention is directed to all papers and documents that are filed concurrently with this specification and are open to public inspection with this specification and the contents of all such papers and documents are incorporated herein by reference. All the features disclosed in this specification including any accompanying claims abstract and drawings may be replaced by alternative features serving the same equivalent or similar purpose unless expressly stated otherwise. Thus unless expressly stated otherwise each feature disclosed is one example only of a generic series of equivalent or similar features.

Furthermore any element in a claim that does not explicitly state means for performing a specified function or step for performing a specific function is not to be interpreted as a means or step clause as specified in 35 U.S.C. Section 112 Paragraph 6. In particular the use of step of or act of in the claims herein is not intended to invoke the provisions of 35 U.S.C. 112 Paragraph 6.

The present invention provides a space invariant topology to enable an Independent Component Analysis ICA to solve chemical detection from two unknown mixing chemical sources. The specific system architecture enables the space invariant ICA to achieve a robust independent signal source separation in an unknown open environment. Additionally the system architecture provides an optimal topology for hardware friendly implementation and an effective architecture for reduced data source requirements.

The space invariant topology along with the techniques of maximum entropy information and natural gradient descent demonstrates that it is effective to separate the two mixed unknown chemical sources with unknown mixing levels to the array of two original sources under insufficient sampled data. From separated sources they can be identified by projecting them on 11 known chemical sources to find the best match for detection.

Simulations have shown that 100 correct detection could be achieved under two cases a under completed case where the number of input mixtures is larger than number of original chemical sources and b regular case where the number of input mixtures is the same as the number of original chemical sources. The time invariant topology approach may face obstacles with an over complete case insufficient data and cumbersome topology.

Four sets of unknown paired mixture sources are collected via an electronic nose which in one non limiting example is a JPL 16 ENose sensor array made at the Jet Propulsion Laboratory Pasadena Calif. . The Enose collects the mixture sources in the unknown environment with at most 12 samples data collected. Per time invariant aspect this appears to be an over complete case in ICA where the number of outputs is larger than the number of inputs .

In one non limiting example the approximation of the set up topology of the electronic nose array is shown in . The collected sensing data x t consists of changes in electrical resistance corresponding to sensor response to the unknown mixture of chemical sources sand their densities or concentrations at the time t.

Due to the small separation between the sensors themselves the input of each sensor resistance is assumed to be uniquely distributed. The sensory data can be modeled as follows 

Where fis the unknown non linear activation is the unknown mixing coefficient of chemical source j and i is the index of sensor number and N as number of sensor and sis original source.

And sis an operating point of the source s. For each sampling data point in time for the same sensor i xfluctuates around its operating point and it can be considered as a common bias for x t with t t t k t . From this argument Equation 2 can be simplified to 

where g is a non linear function e.g the logistic function or hyperbolic tangent function. The update weight can be calculated as 6 

where Wis an inverse transport of the NXN weight matrix W xis a mixing input vector observed vector and

The most common ICA approach is that the number of variables and the number of sources are the same. However in this study there are two obstacles 1 there are 12 or less samples mixing chemical compounds from each sensor and the total number of sensor is 16 and they do not have sufficient data set at least 16 data samples required and 2 the number of variables is 16 as number of sensors while the number of compounds in a mixture is 2 and it is considered over complete case.

For the time invariant approach the data that will flow orthogonal with the time invariant direction as shown in and will require 32 outputs 16 channels for each chemical compound . The topology is 16 inputs 32 outputs and 12 or less sample data which may not be a solvable problem.

Instead of using a time invariant approach the space invariant approach allows for more data points and enables the square mapping matrix the dimension of mixing sources and sensors are the same . This approach is feasible due to the mathematical model based on equations 2 4 . The architectures are shown in . In the unbiased input Y t i 1 k is based on temporal mixture data and the sensory data are spatially invariant.

From laboratory set up a set of single spectra of 11 chemicals using 16 elements is collected in the ENose sensor array it is averaged and shown in . A database may also contain the sampled data of air samples from an unknown environment to be used in the calculations.

In this embodiment the number of sensors used is 16 and mixing chemical sources is 2 four sets of data will be examined as shown in table of .

In this case the four subsets of the sampled data in are studied and all data vectors available are used the maximum number of data vectors is 12 which is less than the number of sensors 16 .

Using the space invariant ICA approach the recovered signal sources chemical and sources are shown in and the average of the single chemical source and are shown in .

The spectrum of signal in is most closely matched to the signal in . Similarly the spectrum of signal in is most closely matched to the signal in .

To confirm its performance the separated sources and were projected by ICA technique on the known 11 chemical sources shown in the results are provided in the table in .

As can be inferred from the single source of chemical has the greatest overlap with the separated source labeled separated chemical . Similarly single source chemical has the greatest overlap with separated chemical from the mixture shown in .

For the mixture from data set 2 the performance of space invariant ICA has demonstrated its effective capability to separate the mixture of chemicals and as shown in as compared with the original sources in .

Table IV in clearly indicates that the maximum sensor value in the column for separated chemical was for chemical while the maximum sensor value in the separated chemical column was for chemical .

For the mixture of chemicals and space invariant ICA has demonstrated its capability to separate the mixture of chemical and as shown in as compared with the original sources in .

For mixture from data set 4 shown in space invariant ICA has confirmed its powerful capability to separate the mixture of chemicals and as shown in as compared with the original sources in .

In this experiment data set 16 12 is paired in columns to obtain the data set 96 2. From this conversion data values in a single row are the data from the same sensor with consecutive sampling times t i t and t i 1 t this new data set allows the same number of mixing sources and of original sources.

Using this new data set space invariant ICA has produced the results that were validated with the 11 known chemicals. Classification was 100 correct based on the projection on 11 classes shown in .

To simplify the results the mean and standard deviation of its projection were tabulated separated sources of chemical and chemical on each single chemical source and the results are summarized in the table in .

Appendix A incorporated herein by reference further includes a series of flow chart diagrams providing the order in which data is processed and analyzed in the space invariant independent component analysis.

To separate two 2 mixing sources from a sixteen 16 element sensory data array known as the over complete case poses a challenges for mathematical model and network topology. The non overlapped paire wise i.e. sensor i and sensor i 1 or overlapped pair wise i.e. sensor i and sensor i 1 and sensor i 1 and sensor i 2 so on may face cumbersome and ineffective techniques.

As shown above the mathematical model has demonstrated space invariant ICA to be an effective topology to overcome insufficient data samples and the over complete case. Moreover the chemical data itself is fuzzy and inconsistent. The simulation demonstrated that the chemical source separation problem can be solved effectively with complete time sampling data k 12 under complete case and two consecutive sampling data k 2 . Optimal topology may require a model of noise in order to determine the size of the sampling input. Moreover space invariant ICA governed by equation 4 is only valid when the sampling time is sufficiently small. Hence the sampling time also plays an important role to ensure that the model approach holds.

A successful mathematical model to enable the space invariant ICA topology from which Infomax and natural gradient descent technique can be applied has been demonstrated and simulation has confirmed that the modeling is effective and sufficient to perform chemical source separation to enable the smart ENose to detect mixtures of chemicals in an open environment.

