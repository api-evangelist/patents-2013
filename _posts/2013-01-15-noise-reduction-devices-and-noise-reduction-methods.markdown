---

title: Noise reduction devices and noise reduction methods
abstract: A noise reduction device may be provided. The noise reduction device may include: an input configured to receive an input signal including a representation in a frequency domain of an audio signal, wherein the representation includes a plurality of time frames and a plurality of coefficients for each time frame; a noise detection circuit configured to determine a first indicator being indicative of a bandwidth of a coefficient over at least two time; a noise reduction circuit configured to reduce based on the first indicator a noise component in the audio signal; and an output configured to output an output signal including a representation in the frequency domain of the audio signal with the reduced noise component.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09318125&OS=09318125&RS=09318125
owner: INTEL DEUTSCHLAND GMBH
number: 09318125
owner_city: Neubiberg
owner_country: DE
publication_date: 20130115
---
In speech communication in a noisy environment it may be difficult to understand the communication party. This is especially true for communications taking place in places with heavy traffic where for example horns of cars may interfere with the spoken words. Thus there may be a desire for devices and methods that provide for improved communication in places suffering from traffic noise.

A noise reduction device may include an input configured to receive an input signal including a representation in a frequency domain of an audio signal wherein the representation includes a plurality of time frames and a plurality of coefficients for each time frame a noise detection circuit configured to determine a first indicator being indicative of a bandwidth of a coefficient over at least two time frames a noise reduction circuit configured to reduce based on the first indicator a noise component in the audio signal and an output configured to output an output signal including a representation in the frequency domain of the audio signal with the reduced noise component.

A noise reduction method may include receiving an input signal including a representation in a frequency domain of an audio signal wherein the representation includes a plurality of time frames and a plurality of coefficients for each time frame determining a first indicator being indicative of a bandwidth of a coefficient over at least two time frames reducing based on the first indicator a noise component in the audio signal and outputting an output signal including a representation in the frequency domain of the audio signal with the reduced noise component.

A noise reduction device may include an input configured to receive an input signal including a representation in a frequency domain of an audio signal wherein the representation includes a plurality of time frames and a plurality of coefficients for each time frame a noise reduction circuit configured to reduce based on a first indicator being indicative of a bandwidth of a coefficient over at least two time frames a noise component in the audio signal and an output configured to output an output signal including a representation in the frequency domain of the audio signal with the reduced noise component.

A noise reduction method may include receiving an input signal including a representation in a frequency domain of an audio signal wherein the representation includes a plurality of time frames and a plurality of coefficients for each time frame reducing based on a first indicator being indicative of a bandwidth of a coefficient over at least two time frames a noise component in the audio signal and outputting an output signal including a representation in the frequency domain of the audio signal with the reduced noise component.

The following detailed description refers to the accompanying drawings that show by way of illustration specific details and aspects of the disclosure in which the invention may be practiced. These aspects of the disclosure are described in sufficient detail to enable those skilled in the art to practice the invention. Other aspects of the disclosure may be utilized and structural logical and electrical changes may be made without departing from the scope of the invention. The various aspects of the disclosure are not necessarily mutually exclusive as some aspects of the disclosure may be combined with one or more other aspects of the disclosure to form new aspects of the disclosure.

The terms coupling or connection are intended to include a direct coupling or direct connection as well as an indirect coupling or indirect connection respectively.

The word exemplary or example is used herein to mean serving as an example instance or illustration . Any aspect of this disclosure or design described herein as exemplary is not necessarily to be construed as preferred or advantageous over other aspect of this disclosure or designs.

A noise reduction device may be provided in a radio communication device. A radio communication device may be an end user mobile device MD . A radio communication device may be any kind of radio communication terminal mobile radio communication device mobile telephone personal digital assistant mobile computer or any other mobile device configured for communication with another radio communication device a mobile communication base station BS or an access point AP and may be also referred to as a User Equipment UE a mobile station or an advanced mobile station for example in accordance with IEEE 802.16m.

The noise reduction device may include a memory which may for example be used in the processing carried out by the noise reduction device. A memory may be a volatile memory for example a DRAM Dynamic Random Access Memory or a non volatile memory for example a PROM Programmable Read Only Memory an EPROM Erasable PROM EEPROM Electrically Erasable PROM or a flash memory for example a floating gate memory a charge trapping memory an MRAM Magnetoresistive Random Access Memory or a PCRAM Phase Change Random Access Memory .

As used herein a circuit may be understood as any kind of a logic implementing entity which may be special purpose circuitry or a processor executing software stored in a memory firmware or any combination thereof. Furthermore a circuit may be a hard wired logic circuit or a programmable logic circuit such as a programmable processor for example a microprocessor for example a Complex Instruction Set Computer CISC processor or a Reduced Instruction Set Computer RISC processor . A circuit may also be a processor executing software for example any kind of computer program for example a computer program using a virtual machine code such as for example Java. Any other kind of implementation of the respective functions which will be described in more detail below may also be understood as a circuit . It may also be understood that any two or more of the described circuits may be combined into one circuit.

Description is provided for devices and description is provided for methods. It will be understood that basic properties of the devices also hold for the methods and vice versa. Therefore for sake of brevity duplicate description of such properties may be omitted.

It will be understood that any property described herein for a specific device may also hold for any device described herein. It will be understood that any property described herein for a specific method may also hold for any method described herein.

A Traffic Noise Reduction TNR technique for noisy speech captured by a single microphone may be provided for speech enhancement. The provided devices and methods may be particularly effective in noisy environments which contain tonal type noise sources such as vehicular horns and alarms. With the devices and methods these vehicular horn sounds may be reduced and any reference to traffic noise may for example imply this sound disturbance. Devices and methods may be provided for detecting the probability of the presence of these traffic noises which contaminate the target speech signals. These noises may then be attenuated using a devices and methods for estimating the signal and noise power for noise reduction which may be effective for noise sources with a harmonic spectral structure. The TNR system provided may maintain a balance between the level of noise reduction and speech distortion. Listening tests may confirm the results.

Up to now there is no specific solution to this problem rather generalized methods to single channel speech enhancement for any noise source may be used. Single channel speech enhancement systems in mobile communication devices may be used to reduce the level of noise from noisy speech signals. A common problem in such speech enhancement systems may be the reduction of traffic noise sources such as vehicular horn sounds which contaminate the target speech signal. Vehicular horns may be highly non stationary and they may have a tonal structure. The spectral characteristics of the horn source may vary with its device of origin. Therefore this may affect the performance of a noise reduction technique which may utilize a comb filter to notch predefined frequencies. In such highly non stationary environments the noise power may be desired to be tracked even during speech activity. Noise estimation techniques which operate in the short time Fourier transform STFT domain may be used including newer noise estimation systems such as the Minimum Statistics MS . These MS based techniques may estimate the noise spectrum based on the observation that the noisy signal power decays to values characteristic of the contaminating noise during speech pauses. The main challenge faced by these techniques may be tracking the noise power during speech segments. This may result in poor estimates during long speech segments with few pauses. This noise estimate may then be used to filter the measured signal to suppress the noise and enhance the output speech.

MS noise estimation may provide small MS windows and tuning of attenuation parameters may result in more noise reduction. However MS noise estimation does not provide a good balance between noise reduction and low speech distortion for non stationary noises. Subspace based noise estimation may provide low rank approximations for speech in the presence of tonal noises but may be computationally expensive and not suitable for real time applications. Amplitude modulation features may provide detection and classification of speech only noise only and speech in noise situations may be used to control the noise reduction performed however it may be sensitive to training and may require a priori knowledge of the signals being processed. Energy based noise detection may provide that detection of noise onsets may be used to trigger significant attenuation of the detected components however this technique may be not robust to low SNR conditions. Pause detection for noise spectrum estimation by tracking power envelope dynamics may provide that pauses may be detected when the interfering noise is present in either the low frequency or high frequency band however it may provide low performance in the presence of broadband noise sources. The approaches described in this paragraph are general methods for speech processing and are not specifically targeted to traffic noise reduction.

The TNR system may first perform Traffic Noise Detection TND which may also be referred to as a noise detection circuit in to extract underlying signal characteristics which may be used to detect the presence of traffic noise. The max min envelope delta k m which may be referred to as a first indicator and the Spectral Peak Profile Ratio SPPR m which may be referred to as a second indicator may be used in the Tonal Noise Reduction by Estimation TONREST which may also be referred to as a noise reduction circuit technique to attenuate the detected traffic noise components and to thus provide an enhanced signal k m in the frequency domain. The output enhanced signal n may then be reconstructed using inverse STFT . The TND and the TONREST stages of the TNR system from will be described in more detail below.

Devices and methods may be provided which may reduce the level of noise in traffic thereby improving the quality of voice conversations in mobile communication devices.

Devices and methods may be provided which may perform noise reduction on spectral components only associated with the traffic noise and may not impact any other type of encountered noises or speech. As a result the devices and methods may not introduce speech distortion that is commonly introduced in noise reduction techniques.

The devices and methods may provide an automatic analysis of the signal and thus may not require additional hardware or software for switching the technique on and off as they may only operate on the traffic noise components when present.

Devices and methods may be provided which may be used together with an existing noise reduction system by applying them as a separate step and as such the devices and methods may also be optimized and tuned separately.

The devices and methods may have a low complexity because of their modular architecture. The devices and methods may have both low computational requirements and low memory requirements. These may be important advantages for battery operated devices.

Moreover many other acoustic enhancement techniques typically in a communication link may operate also in the frequency domain for example echo cancelers. This may allow for computationally efficient implementations by combining the frequency to time transforms of various processing modules in the audio sub system.

Devices and methods may be provided which may automatically analyze the scene to prepare for the detection of traffic noise.

The devices and methods may perform a first stage of detection to identify and extract features which may be associated with traffic noise sources.

Devices and methods may be provided which may determine a speech presence probability from these extracted features which may be used for accurate speech and noise power estimation.

The devices and methods may estimate the speech signal s spectral magnitude from spectral information surrounding the detected traffic noise components.

Devices and methods may be provided which may reduce the level of the traffic noise using the estimated speech signal magnitude. This may reduce the noisy speech spectral magnitude to levels associated with the underlying speech estimate.

This may result in a more comfortable listening experience by reducing the level of traffic noises without the speech distortion that is commonly introduced in noise reduction techniques.

The TNR system may attenuate noise components while minimizing distortion to the desired speech signal. The TND system may extract characteristics of a noise components in the traffic noise which may then be used for performing detection and classification of the desired speech and noise components. The TND system may be particularly effective at detecting tonal noise components such vehicular horn sounds. The TND system shown in is illustrated in more detail in .

The top branch of is first described as follows in the bottom branch a spectral peak profile ratio determination module may be provided which will be described in more detail later . Vehicular traffic horns sounds may occur at different frequencies depending on their source of origin. However it was observed that the power levels of these sounds are either stationary for short time segments signal dependent or the power level decays with time. This characteristic may be not the same for speech signals as the power level fluctuates at a faster rate for example 4 to 6 syllables per second than the vehicular horn noises. Therefore in this branch of the TND system the minimum and maximum power envelopes of the noisy signal are tracked in and the magnitude of their difference may be used to classify either the desired speech or the target noise sources. The first iteration of this technique involves the smoothing of the noisy speech spectral components X k m which may be determined in . X k m may denote the Fourier coefficient related to a k th frequency wherein k may be an number between f which may be a design parameter and may represent a cut off frequency and N 2 1 and an m th point in time in other words the m th time frame . The smoothing may form the smoothed noisy signal spectrum P k m by first order recursive averaging in for example according to the following formula 1 1 3 where a may be the smoothing constant. The smoothing constant may be calculated using 1 4 where may be the specified time constant and fmay be the sampling frequency.

The two cases of increasing and decreasing power may be considered as described below to determine the smoothing constant to be used in 3 to obtain P k m 

For increasing power i.e. X k m P k m 1 the smoothing factor may be set as follows wherein may be a design variable for example 1 which may be called TNR SpecSmoothRise 

The minimum and maximum envelopes of P k m may be tracked to determine the corresponding envelope signals P k m and P k m . P k m and P k m may be initialized to P k m for the first M frames for example 200 ms to 300 ms initialization time duration . The maximum spectral envelope P k m may be tracked and smoothed such that it may be updated when the signal energy increases and the signal envelope decays otherwise for example for constant energy level or decrease in energy . The computation of P k m may be performed as follows 

The minimum spectral envelope P k m may be tracked and smoothed such that it may be updated when the signal energy decreases and the signal envelope may increase otherwise for example for constant energy level or an increase in energy . The computation of P k m may be performed as follows 

A final stage of the TND may involve the computation of the difference between P k m and P k m . This difference is denoted as k m which may also be referred to as bandwidth and may be determined as follows 9 where P k m and P k m may be given in dB in equation 9 .

During traffic noise occurrences such as vehicular horn sounds the second order statistics of these noises may either remain relatively stationary or may tend to decrease. From the above analysis of the TND technique it may be seen that during noise instances which exhibit such behavior the two spectral envelopes of P k m and P k m may converge resulting in a decrease in the value of k m . Therefore k m may be used in TONREST to classify the signal components as desired speech or noise before performing attenuation. An example of the underlying process may be demonstrated using the spectrograms in and .

For the demonstration of the effect of the TND system at detecting traffic noise after deriving a binary mask from the extracted values of k m in a diagram illustrating a clean speech signal is shown in a diagram illustrating a signal contaminated with traffic noise at 5 dB SNR is shown and in a diagram illustrating a reconstructed traffic noise signal after applying a binary mask to the noisy signal is shown.

The noisy signal from may be input to the TND system and the extracted values of k m may be compared against a fixed threshold r wherein r may be a design variable for example 13 to derive a binary mask which may be denoted by M. This mask may be applied to remove the speech components and retain the noise components such that 0 for and 1 for 

This mask M i m may be applied to the input noisy signal to demonstrate the effectiveness of the TND system at detecting traffic noise components. The reconstructed signal containing the detected noise components is shown in . It is to be noted that the value of f 1.5 kHz therefore only those components above fmay be processed.

The time constants may be set to determine the smoothing factors used in the recursive averaging in the top branch of the TND system from . These may be set to allow minimum time for the convergence of P k m and P k m to avoid misdetections of speech as noise components. There may be instances of short strong vehicular horn sounds. Therefore an additional detection stage to determine the Spectral Peak Profile Ratio SPPR module in the SPPR may also be referred to as a second indicator may be provided and may be included in the TND system for such cases as shown in the bottom branch of . Male and female speakers typically may have spectral profiles for speech where their pitch frequency exists below 500 Hz. As such speech may have strong energy content below 1 kHz the spectral characteristic of this low frequency region is most likely to be preserved in the presence of interfering noise where larger spectral peaks occurs between 0 and 500 Hz than between 500 Hz and 1 kHz. However this would not necessarily be observed in the presence of short strong vehicular horn sounds. A measure of the distortion of the spectral profile may be defined as SPPR m below in equation 11 and may be used as a cue for the detection of traffic noise presence SPPR 11 

where m may be defined as the magnitude of the largest spectral peak between the frequencies 0 to f where f may assume a value of 500 Hz based on experimental analysis of long term average speech spectrum. m may be defined as the magnitude of the largest spectral peak between the frequencies f 1 to f where fmay assume a value of 1 kHz.

The TONREST system may be designed to classify the input signal components of X k m as either speech or noise and perform noise reduction. The targeted traffic noise components may have a tonal spectral structure and may occupy the entire signal spectrum. Therefore the first stage of TONREST as shown in may involve the analysis of X k m to detect the spectral peaks X i m where i may be the peak index. The corresponding spectral troughs X j m may be detected which may surround the peaks where j may be the trough index in the signal spectrum.

The hypothesis Hmay be used to denote the presence of tonal noise. The differences of the maximum and minimum envelopes i m may correspond to the identified spectral peaks and may then be used to estimate in the tonal noise probability p i m p H i m corresponding to the detected spectral peaks. The computed i m may yield p i m as illustrated in and defined as below 

An alternative mapping for the speech presence probability shown in would be to use a non linear mapping such as a sigmoidal function between and .

In addition to the above described example for speech noise classification the SPPR m which may be computed according to equation 11 from the TND may be compared against a threshold value which may be a design variable for example 6 as described above this design variable may be a tuning parameter based on the system requirements for noise classification as described above to set a flag Attn Flag m to 1 for speech classification and 0 for noise classification. As described above this may be used to detect the presence of short low SNR noise instances and Attn Flag m may be obtained as follows 

As this measure may be used for classification of special noise occurrences the threshold may be selected to be large enough to avoid misclassification of speech as noise.

A final stage of TONREST may in involve the reduction of the detected tonal noises. For each spectral peak identified X i m a speech estimate i m may be obtained from the surrounding spectral troughs X j m which may be less affected by the tonal noise components. i m may be estimated as 1 14 where a design variable K may be set to control the amount of attenuation applied to the noisy signal. Therefore larger values of K may result in more signal attenuation. Unvoiced speech may have a relatively flat spectrum and for these frequencies a typical value of K 2 may be assumed. A noise estimate j j 1 m may hence be derived as 1 1 15 where j j 1 may denote the range of spectral troughs surrounding the examined peak i excluding the end points. The magnitude of the enhanced speech j j 1 m may then be recomputed by incorporating the estimated p i m as 1 1 1 . 16 

The speech estimate from equation 16 may be combined with the noise classification result Attn Flag m and may be embedded in the following speech estimate 1 1 17 wherein may be a design variable.

This may also be formulated into a gain which may be applied to the noisy spectral components to obtain the enhanced signal. The speech estimate from 14 may be combined with the noise classification result Attn Flag m and the tonal noise probability p i m and may be embedded in the following TNR gain function G equation 18 which may then be applied to this equation to obtain the gain for those frequency bins j j 1 1 1 1 1 18 

In the following a cut off frequency consideration will be described. Voiced speech components may have a harmonic structure which may be misclassified as the traffic noise components. Therefore the lower cut off frequency for operation of TONREST may be given by f.

The performance of the TNR technique for noise reduction and speech enhancement may be tested on speech utterances. The clean speech signals may be processed using tools using the MSIN mobile station in filter and the speech level may be set to 26 dB SPL sound pressure level . The speech signals may be corrupted with traffic noise which may be dominated by vehicular horn sounds and processed using the TNR system illustrated in . A sampling frequency of 8 kHz may be used. The signal may be split up into frames of length 20 ms.

In a first assessment the noisy speech signal presented in may be processed using TNR. The enhanced signal is shown in . The noisy signal from was then processed again with the same parameters except with f 800 Hz and K 100. These changes were done to illustrate the effect of performing TNR on the lower frequencies of the noisy signal in addition to the application of more noise attenuation by increasing the value of K. The results of this simulation are shown in . These results demonstrate the effectiveness of TNR at attenuating the tonal components present in traffic noise while preserving the underlying speech content to minimize speech distortion.

In order to assess the relative performance of the TNR system for speech enhancement the objective measures of segmental SNR segSNR segmental signal to noise ratio Perceputal Evaluation of Speech Quality PESQ and P8622 are used. These measures may be recorded to observe the amount of speech distortion introduced to clean speech signals which are processed using the TNR system. Both of the above simulation set ups may be used with the standard TNR parameters described in the text with f 1500 Hz and K 2 as in and also with the TNR parameters which may perform more noise attenuation i.e. setting f 800 Hz and K 100 as in . The results in Table 1 show that TNR may be effective at preserving speech quality with slightly more distortion being introduced when the parameters are set for more noise reduction and lower cut off frequency.

It will be understood that indicative of does not necessarily mean to give the precise value but a qualitative information on the size of a value.

The noise detection circuit may further determine a second indicator which may for example be the SPPR as described above . The second indicator may represent a ratio between a frequency component of the audio signal below a pre determined threshold frequency and a frequency component of the audio signal above the pre determined threshold frequency. The noise reduction circuit may reduce based on the first indicator and the second indicator the noise component in the audio signal.

The noise detection circuit may determine the first indicator based on a difference between a smoothed maximum value of a coefficient over at least two frames and a smoothed minimum value of a coefficient over at least to frames.

The bandwidth of a coefficient over at least two time frames may include or may be a bandwidth of a coefficient corresponding to a pre determined frequency at a first time frame and a coefficient corresponding to the pre determined frequency at a second time frame.

The frequency component of the audio signal below a pre determined threshold frequency may include or may be a spectral peak below the pre determined threshold frequency.

The frequency component of the audio signal above a pre determined threshold frequency may include or may be a large spectral peak between the pre determined threshold frequency and a further pre determined threshold frequency.

The noise reduction circuit may determine a flag indicating whether to classify the audio signal to a speech class or to a noise class based on the second indicator.

The noise reduction circuit may determine a speech estimate based on the determined spectral peak and a plurality of surrounding spectral troughs.

The noise reduction circuit may determine a noise estimate based on the speech estimate and at least one spatial trough surrounding the spectral peak.

The noise reduction circuit may determine an enhanced speed signal based on the tonal noise probability and the noise estimate.

The noise reduction circuit may determine an audio signal with the reduced noise component based on the flag and the speech estimate.

It will be understood that indicative of does not necessarily mean to give the precise value but a qualitative information on the size of a value.

The noise detection circuit of the noise reduction device may further determine a second indicator representing a ratio between a frequency component of the audio signal below a pre determined threshold frequency and a frequency component of the audio signal above the pre determined threshold frequency. The noise reduction circuit of the noise reduction device may based on the first indicator and the second indicator reduce a noise component in the audio signal.

The noise reduction method may further include determining the first indicator based on a difference between a smoothed maximum value of a coefficient over at least two frames and a smoothed minimum value of a coefficient over at least to frames.

The bandwidth of a coefficient over at least two time frames may include or may be a bandwidth of a coefficient corresponding to a pre determined frequency at a first time frame and a coefficient corresponding to the pre determined frequency at a second time frame.

The frequency component of the audio signal below a pre determined threshold frequency may include or may be a spectral peak below the pre determined threshold frequency.

The frequency component of the audio signal above a pre determined threshold frequency may include or may be a large spectral peak between the pre determined threshold frequency and a further pre determined threshold frequency.

The noise reduction method may further include determining a tonal noise probability based on the first indicator.

The noise reduction method may further include determining a flag indicating whether to classify the audio signal to a speech class or to a noise class based on the second indicator.

The noise reduction method may further include determining a spectral peak based on the input signal.

The noise reduction method may further include determining a speech estimate based on the determined spectral peak and a plurality of surrounding spectral troughs.

The noise reduction method may further include determining a noise estimate based on the speech estimate and at least one spatial trough surrounding the spectral peak.

The noise reduction method may further include determining an enhanced speed signal based on the tonal noise probability and the noise estimate.

The noise reduction method may further include determining an audio signal with the reduced noise component based on the flag and the speech estimate.

It will be understood that indicative of does not necessarily mean to give the precise value but a qualitative information on the size of a value.

The noise reduction circuit may reduce the noise component in the audio signal based on the first indicator and based on a second indicator. The second indicator may represent a ratio between a frequency component of the audio signal below a pre determined threshold frequency and a frequency component of the audio signal above the pre determined threshold frequency.

The bandwidth of a coefficient over at least two time frames may include or may be a bandwidth of a coefficient corresponding to a pre determined frequency at a first time frame and a coefficient corresponding to the pre determined frequency at a second time frame.

It will be understood that indicative of does not necessarily mean to give the precise value but a qualitative information on the size of a value.

The noise reduction circuit of the noise reduction device may reduce the noise component in the audio signal based on the first indicator and based on a second indicator. The second indicator may represent a ratio between a frequency component of the audio signal below a pre determined threshold frequency and a frequency component of the audio signal above the pre determined threshold frequency.

The bandwidth of a coefficient over at least two time frames may include or may be a bandwidth of a coefficient corresponding to a pre determined frequency at a first time frame and a coefficient corresponding to the pre determined frequency at a second time frame.

While the invention has been particularly shown and described with reference to specific aspects of this disclosure it should be understood by those skilled in the art that various changes in form and detail may be made therein without departing from the spirit and scope of the invention as defined by the appended claims. The scope of the invention is thus indicated by the appended claims and all changes which come within the meaning and range of equivalency of the claims are therefore intended to be embraced.

