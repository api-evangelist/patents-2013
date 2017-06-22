---

title: Controlled transitory or sustained gliding flight with dihedral angle and trailing flaps
abstract: A micro aerial vehicle capable of controlled transitory or sustained gliding flight. The vehicle includes a fuselage. A pair of articulated wings are forward of a center of gravity of the vehicle, the wings being articulated and having trailing edge flaps, and having actuators for controlling the dihedral angles of the wings and the flaps for effective yaw control across the flight envelope. The dihedral angles can be varied symmetrically on both wings to control the aircraft speed independently of the angle of attack and flight-path angle, while an asymmetric dihedral setting can be used to control yaw and the actuators control the dihedral settings of each wing independently. The aircraft lacks a vertical tail or other vertical stabilizer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09394050&OS=09394050&RS=09394050
owner: The Board of Trustees of the University of Illinois
number: 09394050
owner_city: Urbana
owner_country: US
publication_date: 20131031
---
The application claims priority under 35 U.S.C. 119 from prior provisional application Ser. No. 61 726 663 which was filed Nov. 15 2012 and which is incorporated by reference herein.

This invention was made with government support under contract number FA95500910089 awarded by the Air Force Office of Scientific Research. The government has certain rights in the invention.

A field of the invention is flight and flying devices and particularly articulated wing micro aerial vehicles. Example applications of the invention include bio inspired flight devices.

The dihedral angle is the upward angle measured from horizontal of the wings or tailplane of an aircraft. If there are multiple sections of a wing having different angles from horizontal then the wing can be referred to as polyhedral. Wing dihedral angle is known to play a role in lateral directional stability. In standard aircraft including almost all large commercial and private aircraft the wings are typically set at a fixed positive dihedral angle for stability. Aircraft such as the Lockheed Martin F 104 and AV 8B Harrier use a negative dihedral anhedral setting for improved agility. These basic aspects have been well studied and are covered in many textbooks related to flight. A flexible wing deforms in a way that the effective dihedral of the wing increases. This only adds to the stabilizing effect of the dihedral. The changes resulting from flexibility have also been documented.

Unlike fixed wing aircraft flapping wing aircraft possess the ability to change the dihedral angle on demand. An asymmetric wing setting naturally produces a yawing moment however. Others have investigated the use of articulated wings for roll and yaw control. The approach studied has focused on controllable winglets. An example of this type of control is found in various papers published by Friswell Bourdin et al. See e.g. Bourdin et al. Aircraft Control via Variable Cant Angle Winglets Journal of Aircraft Vol. 45 No. 2 March April 2008. In this approach the canted winglet in the inner wing is deflected upward to induce a turn. This reduces the net lift on the inner wing to induce the desired rolling moment while the upward deflected winglet acts like a vertical tail and produces a proverse yawing moment in response to the rolling moment. This approach requires a segmented wing and that only the winglet be deflected. With a monolithic wing this approach can impair turning because the side force from the deflected wing may adversely dominate the side force required for turn in a right turn the deflected winglet produces a leftward force whereas a rightward force is required to sustain aid the turn .

Prior work by the present inventors and colleagues has advanced the state of micro aerial craft with articulated wings. Paranjape A. A. Chung S. J. and Selig M. S. Flight Mechanics of a Tailless Articulated Wing Aircraft Bioinspiration Biomimetics Vol. 6 No. 2 12 Apr. 2011 discloses a micro aerial aircraft with articulated wings and a horizontal tail no vertical tail and thus the reference to tailless aircraft in the title . This paper discloses that the wing dihedral can be varied symmetrically along with the horizontal tail to control the flight path angle independently of the fight speed. The micro aerial aircraft in the paper used dihedral angles that could be set asymmetrically for executing rapid zero sideslip turns. This work showed that the sign of the yaw moment derivative with respect to anti symmetric dihedral depends strongly on the angle of attack and the angular rates. The primary demonstration of this work was to show that the yaw control effectiveness of the anti symmetric dihedral depends primarily on the angle of attack and also on the angular rates. When the angular rates are zero the sign of the effectiveness depends on the sign xC c C where x c is the non dimensional distance between the center of gravity and the quarter chord line. Furthermore C

An embodiment of the invention is a micro aerial vehicle capable of controlled transitory or sustained gliding flight. The vehicle includes a fuselage. A pair of articulated wings are forward of the center of gravity of the vehicle the wings being articulated and having trailing edge flaps and having actuators for controlling the dihedral angles of the wings and the flaps for effective yaw control across the flight envelope. The dihedral angles can be varied symmetrically on both wings to control the aircraft speed independently of the angle of attack and flight path angle while an asymmetric dihedral setting can be used to control yaw and the actuators control the dihedral settings of each wing independently. The aircraft lacks a vertical tail or other vertical stabilizers.

An embodiment of the invention is a vertical tailless micro aerial vehicle with a pair of articulated wings. The aircraft is controlled using wing articulation together with trailing edge flaps for effective yaw control across the flight envelope. The dihedral angles can be varied symmetrically on both wings to control the aircraft speed independently of the angle of attack and flight path angle while an asymmetric dihedral setting can be used to control yaw in the absence of a vertical tail. Actuators control the dihedral settings of each wing independently and according to the mathematical formulation of closed loop control in the attachments to achieve controlled sustained or transitory gliding flight. The wings are set ahead of the vehicle s center of gravity. Wing dihedral alone can be varied asymmetrically to perform rapid turns and regulate sideslip. The wings include trailing edge flaps. The trailing edge flaps are deflected downwards by a predetermined minimum amount.

Preferred embodiments of the invention will now be discussed with respect to the drawings. The drawings may include schematic representations which will be understood by artisans in view of the general knowledge in the art and the description that follows. Features may be exaggerated in the drawings for emphasis and features may not be to scale.

Other than the flapping wings and trailing flaps no additional yaw control mechanisms such as a vertical tail two degree of freedom horizontal tail or split flaps are required. The wings shown can be considered rigid but significantly flexible wings whose bending naturally creates a dihedral effect can be used with the invention while maintaining the control provided by the application of asymmetric and symmetric dihedral angles accompanied by independent deflection angles for the flaps . Methods and flight craft provide side force for yaw control in the same direction as that required for turning which is advantageous compared to the winglet approaches that can create counterproductive side forces. shows another exemplary micro aerial device that includes a propulsion mechanism. The device includes features of the devices of and these common features are labeled with like reference numerals. In addition the device includes a propeller and motor . The device accomplishes sustained flight.

Control in accordance with was used to control an experimental aircraft as shown in . Control was accomplished by a combination of feedforward and feedback controllers. The angle of attack was controlled by the elevator tail . The tail preferably includes a trailing edge flap to operate as an elevator but the entire tail can also deflect. In addition static tails are permitted. The flaps were deflected to a constant angle of 10 deg. The flight path angle was controlled by changing the symmetric component of the wing dihedral denoted by while the aircraft heading was controlled by anti symmetric deflection of the two wings denoted by asym . sin cos cos sin sin sin cos sin cos cos cos 1 sin cos cos cos cos sin sin sin sin sin cos cos sin cos cos sin sin sin cos 2 dot over sign dot over square root over 3 

In the above equations the flight path angle is the wind axis heading angle is and the turn rate is .

With a large horizontal tail and the CG located approximately c 3 behind the wing aerodynamic center the aircraft was sufficiently stable in pitch. Given the excellent open loop stability characteristics the angle of attack was not controlled by feedback laws. Rather the elevator deflection was set as a function of the commanded angle of attack. Specifically 

In an experimental controller the wind axis heading angle was used as feedback for a PI yaw controller. While adding yaw rate feedback would provide for more robust control the experiments demonstrated that the wind axis heading angle was sufficient for control. During test flight of experimental aircraft in as shown in the dihedral angles of the two wings are controlled independently of each other. A left right asymmetry in the wing dihedral angles and or the force distribution on the wings leads to a net side force which by the virtue of a non zero distance between the aircraft center of gravity and the line of action of the force translates into a yawing moment. Due to wing camber the sign of the yawing moment for a given dihedral configuration depends on the angle of attack and the angular rates of the aircraft. Deflecting the trailing edge flaps on the articulated segments of the wing removes this non uniformity.

Additional feedback control was also developed for the aerial vehicle of . The control theory to be discussed includes use of the wing dihedral angles for control use of the trailing edge flaps to mitigate control effectiveness problems stability control and closed loop control for perching. The relevant forces are discussed first.

The side force can be used for providing the centripetal force for turning and as a source of yawing moment. In particular if the CG center of gravity is located behind the line of action of the side force then a positive rightward side force produces a positive yawing moment and vice versa. It follows that a positive rolling moment wherein the lift on the left wing is higher than the right wing is accompanied by a positive yawing moment if the wings have a positive dihedral deflection. In aircraft which lack a vertical tail a positive rolling moment is accompanied by a negative yawing moment which leads to an increase in sideslip with the consequence that the aircraft faces an increased drag and potential reduction in lateral directional stability. This yawing moment which acts in a sense opposite to the rolling motion is called adverse yaw. Adverse yaw is one of the primary limiting factors for the lateral directional performance of a vertical tailless aircraft and a positive wing dihedral naturally suppresses adverse yaw produced due to rolling

The present inventors and colleagues have previously shown that that yaw control effectiveness of the anti symmetric dihedral depends not only on the angle of attack but also on the angular rates. See A. A. Paranjape S. J. Chung and M. S. Selig Flight mechanics of a tailless articulated wing aircraft Bioinspiration Biomimetics vol. 6 no. 2 2011 paper number 026005. The non dimensional control effectiveness is given by 8 where Cand Cthe coefficients of lift and quarter chord pitching moment introduced in 1 . The term xdenotes the non dimensional with respect to chord length distance between the center of gravity and the quarter chord line. Therefore sign sign 9 For positively cambered wings C

In the invention the problem of non uniform sign of control effectiveness is solved with trailing edge flaps. Trailing flap deflection leads to a greater increase in Cas compared to the reduction in C. Using the airfoil theory it can be shown that the change in Cand Cdue to a flap deflection is given by

The term is defined purely for mathematical convenience in thin airfoil theory. For the example experimental aircraft consistent with x 08.1 and x 0.25. Thus 2.2143 C 3.45 and C 0.14 .

Thus flap deflection of nearly 7 deg is required at 0 and no flap deflection is required beyond 10 deg. A static flap deflection is preferred to avoid incurring any adverse effects from a dynamically varying flap deflection. In real terms the flap deflection is preferably constant while the dynamics settle down. When the flap position is changed the dynamics are perturbed and they settle down after some time has elapsed. The duration that it takes for the dynamics to settle down is called the settling time of the system. Therefore instead of a statically fixed flap setting a piece wise constant flap deflection can also be used where the flap deflection is held fixed for at least the settling time of the dynamics with some factor of safety . However the minimum flap deflection angle is still decided by . A larger flap deflection can be used for low speed flight as needed.

The benefit of uniformly positive control effectiveness however comes with a trade off. The aircraft flies in a high lift it can be checked that C 0.64 high draft configuration across the flight envelope. This slows the aircraft. However the flight path angle can still be controlled effectively using symmetric dihedral deflection.

The rigid flight dynamics together with the aerodynamics and kinematics are highly nonlinear. The equations of motion ignoring terms that arise from the angular velocity of the wing motion due to flapping have essentially the following structure dot over 14 

where m is the total mass of the aircraft m is the mass of each wing J is the moment of inertia tensor for the aircraft S denotes the vector product and Fand Mrepresent the net external aerodynamic gravitational force and moment on the aircraft. Furthermore p q r is the vector representation of the aircraft angular velocity of the aircraft with components in the aircraft body axes. The net aerodynamic force depends on the wing orientation. The position of the aircraft center of gravity is denoted by r which is in turn approximated closely by

where and are the dihedral angles of the left and right wings and b is the total wing span so that each wing has length b 2 . The force and moment vectors and Fand M depend strongly on the dihedral angles of the wings. This is demonstrated by the yawing moment component of Mt which is given by sin sin 16 

where and are local angles of attack of the left and right wings which actually vary as a function of y the spanwise coordinate and Zand Zare the local z forces on the two wings. The terms and themselves depend on and respectively. For example at a spanwise coordinate y is given by

where xc is the distance between the center of gravity and the aerodynamic center of the wing. The sideslip is roll rate is p and yaw rate is r. A similar expression can be written for .

In the simplest case Zand Zare linear functions of and respectively. Even then the flight dynamics of aircraft with articulated wings are nonlinear and non affine in control. However recognition of and accounting for the following flight dynamics is used in the invention to simplify control design 

1 The pitch dynamics can be controlled entirely by the elevator and almost always independently of the lateral directional dynamics. This is true for most aircraft except those that lack a horizontal tail 

2 For the micro aerial vehicles of the invention the pitch dynamics q are stable. The only source instability is the lateral directionals dynamics involving the yaw rate r and sideslip 

3 The roll dynamics are stable and they are not controlled directly since the wing dihedral primarily controls yaw with very little roll control effectiveness.

With these factors in mind the control laws are determined as follows. Consider the problem of controlling the yaw and r dynamics. For the purpose of controlling the yaw dynamics can be cast into the following control non affine form dot over 18 dot over 19 

where t t r t represents the yaw dynamics while u is the control input viz. the asymmetric dihedral deflection . The term p t represents other control inputs namely the elevator deflection and symmetric dihedral deflection which are used for longitudinal flight control. Finally V p q represents the rolling and pitching motion as well as translation in the plane of symmetry. The flight dynamic modes corresponding to these six states are to be stable. One of the control objectives is to stabilize t t r t in Equation 19 and ensure that it track a desired trajectory.

In embodiments of the invention dynamic inversion laws are simplified to provide proportional integral PI or proportional integral derivative PID controllers. Specific example controls were based upon a class of dynamic inversion control laws defined in N. Hovakimyan E. Lavretsky and A. Sasane Dynamic inversion for nonaffine in control systems via time scale separation. Part I Journal of Dynamical and Control Systems vol. 13 no. 4 pp. 451 465 2007 . Our modification simplification yields exact gain tuning laws which allows the control gains to be linked explicitly to the convergence properties of the closed loop system as well as the tracking error bound.

Consider a general system described by equation 19 where is no longer the yaw dynamics but represents the state variables of interest for the purpose for control design. For now we impose the additional condition D where D is compact. The case is addressed later in the section. Let e t t r t be the tracking error signal. Then the open loop error dynamics are given by dot over dot over 0 dot over 0 20 

where the unperturbed additional dynamics dot over t 0 t 0 are assumed to be exponentially stabilized by to the control input p t see 19 . We construct the dynamic inversion controller 

The proof of this theorem is based on Tikhonov s theorem H. K. Khalil Nonlinear Systems 3rd ed. Pearson Education Upper Saddle N.J. 2000 Theorem 11.1 and is also reproduced in N. Hovakimyan E. Lavretsky and A. Sasane Dynamic inversion for nonaffine in control systems via time scale separation. Part I Journal of Dynamical and Control Systems vol. 13 no. 4 pp. 451 465 2007.

Remark 1. Although Lemma 1 guarantees that the tracking error it does not provide any guarantees on robustness. In particular using a high gain can be detrimental in the presence of time delays.

Theorem 1. The control law in Equation 31 is equivalent to a PI controller with proportional k and integral k gains tuned to satisfy k 1 and k ak where ais the desired time constant for the closed loop dynamics.

We may choose u 0 sign f u e 0 . If kand kdenote the proportional and integral gains of the PI controller the they should be chosen to satisfy and 1 25 

Consider a second order system umlaut over t f t dot over u . We can write it in the form dot over 26 

With as the output the equation for is affine in u t . The existence of f and g was shown in C. Cao and N. Hovakimyan L1 adaptive controller for a class of systems with unknown nonlinearities Part 1 in Proceedings of the American Control Conference Seattle Wash. 2008 pp. 4093 4098. Note that sign g sign f dot over .

where r t is the reference trajectory for t t and a 0. Define the error state for t as e t t t whose dynamics are given by 28 

ensures that tracks where the gains kand kare chosen as per the guidelines in Theorem 1. The controller still needs further simplification to the PID form. Note that e t t ae t dot over r t t . Substituting into 29 we get sign 30 Which is a PID controller.

Theorem 2. The second order system 26 can be stabilized using the PID controller 30 and it can be ensured that the tracking error between t and the reference signal r t is bounded.

Proof Theorem 1 guarantees that the control law 29 ensures that the tracking error e t of the bounded 28 is bounded. Thus 0. Recalling the first equation dot over t dot over t t since t e t t we can write dot over dot over dot over dot over 31 

Since the unperturbed edynamics obtained by setting e 0 are potentially stable it follows from the Comparison Lemma Lemma 9.1 in H. K. Khalil Nonlinear Systems 3rd ed. Pearson Education Upper Saddle N.J. 2000 that e t is bounded if eis bounded. Moreover the bound on e . This completes the proof. 

Remark 2. The following observations summarize the results for the closed loop controller that has been developed.

1 PI and PID controllers can be employed for nonlinear systems of the form 19 provided the additional dynamics are stable.

1 Apply a control law for the symmetric dihedral deflection 2 which ensures that the flight path ztracks the desired profile z x . The desired profile z x is a straight line connecting the initial point to the desired final point x z 

This is illustrated in which shows the guidance problem. The aircraft is guided in the x z plane along z x while the y coordinate is regulated separately. Note that the z axis points upwards. Consequently the x y z axes shown do not define a conventional right handed frame but are used as a reference purely as a matter of convenience.

2 Apply a control law for the anti symmetric dihedral deflection 2 which ensures that y x 0 as x xthe desired final point. This requires that the yaw r dynamics be stabilized.

Yaw control has been often neglected in the literature on perching. On the other hand lateral directional control is an important concern for aircraft which lack a roll control surface such as an aileron and use a highly unconventional yaw control mechanism.

With a large horizontal tail and the CG located approximately c 3 behind the wing aerodynamic center the aircraft was sufficiently stable in pitch. Given the excellent open loop stability characteristics the angle of attack was not controlled by feedback laws. Rather on the basis of open loop glide tests the elevator deflection was set as a function of the commanded angle of attack 

where and have been specified in degrees instead of the more conventional units of radians. Equation 34 is identical to equation 4 but is repeated here for clarity of explanation and ease of reference.

where m is the aircraft mass S us the wing area and is the symmetric dihedral deflection 2 . Note that

If we further assume that cos 1 then the equations of translational motion simplify to the following form 

The system in 37 is in the form 26 except that derivatives and functions are defined with respect to x not t. Hence by replacing t and dt in 30 with x and dx the following controller is designed see Theorem 2 

where e x z x z x and a is the desired rate of convergence of z x to the desired trajectory z x . The stability of the controller is guaranteed by Theorem 2. Note that the independent variable used in the controller is x and not t. This is consistent with the recasting of the equations of motion in the spatial domain.

We assume that the yaw rate r settles rapidly to the commanded yaw rate r so that r r dot over X cos cos . The inner loop yaw controller in ensures that r converges rapidly to r. This is an expression of the time scale separation between the fast yaw r dynamics and the slower heading y X dynamics. Thus we get

where is the bank angle of fuselage. Note that cos and cos and cos are all positive since they lie in very generally which implies that the control coefficient V cos cos cos is uniformly positive. The control problem is very similar to what is encountered for the flight path angle show in 37 and we derive a similar controller as 38 tan 41 

The stability of this controller is guaranteed by Theorem 2. Further as in the case of flight path control the use of dynamic inversion was considerably facilitated by rewriting the dynamical equations in the spatial domain which rendered them in a strict feedback form. Next we describe the design of the inner yaw control loop in .

Remark 3. The choice of y 0 as the desired path can be replaced by any suitable path y x such as a straight line connecting the initial point and the desired final point as for the flight path angle guidance law.

The objective of the inner yaw control loop in is to command the anti symmetric wing dihedral so that the rate r tracks the yaw rate commanded by the outer loop r. Yaw control is achieved using a PI controller motivated by Theorem 1 given by 42 

In practice the heading and flight path angles are computed and commanded preferably every 0 05 s. This prevents undesirable oscillatory behavior which arises due to continuous changes in the wing dihedral and the underlying coupling between the wing dihedral angle and the pitching dynamics of the aircraft.

The articulated portion was hinged and included the outboard 60 of the wing. It has five control surfaces 

1 An elevator which is a movable flap attached to the horizontal tail and whose deflection is denoted by .

2 The dihedral angles and of the outboard segments of the right and left wing can be changed independently of each other. The actuators for changing the wing dihedral angle were attached on the lower surface of the center non rotating wing section along with the radio receiver.

3 The outboard segments were equipped with flaps which are capable of being actuated independently. In the experiments both flaps were deflected by the same amount . Flaps are used for ensuring uniform yaw control effectiveness. These flaps when deflected in an anti symmetric manner can also act as the traditional ailerons.

Both wings in the experimental aircraft can rotate from a maximum 45 deg dihedral to minimum 15 deg for a total arc range of 60 deg. The actuators for wing dihedral are controlled independently on both wings. Digital actuators with a torque rating of 0.29 kg cm are used to maneuver the wings. The time required for the wings to rotate from the minimum 15 deg to maximum 45 deg is about 0.05 s and the actuators have a time delay of 200 ms.

While not bound by this theory and not needed to demonstrate patentability the experiments demonstrate that the invention provides what is believed to be the first perching demonstration on a laterally unstable aerial robot. In experiments the lateral directional motion of the aircraft was controlled actively for the entire duration of the maneuver. This complements and advances the state of the art experiments reported in the literature which were concerned almost exclusively with the longitudinal motion of stable aircraft.

The experimental aircraft used variable asymmetric wing dihedral effectively to control the flight path as well as the heading of the aerial robot. Trailing edge flaps ensure that the wing dihedral provided uniform yaw control effectiveness across the flight envelope. The closed loop guidance laws of the invention provide perching through control developed by rewriting the equations of motion in the spatial domain and applying dynamic inversion motivated PID control. Experiments demonstrate the ability for the aircraft to conduct controlled guided flight and perch on hand which is a significant advance in developing micro aerial vehicles capable of close operational interaction with humans.

The above example aircraft has been flight tested. During flight the dihedral angles of the two wings are controlled independently of each other. A left right asymmetry in the wing dihedral angles and or the force distribution on the wings leads to a net side force which by the virtue of a non zero distance between the aircraft center of gravity and the line of action of the force translates into a yawing moment. Due to wing camber the sign of the yawing moment for a given dihedral configuration depends on the angle of attack and the angular rates of the aircraft. Deflecting the trailing edge flaps on the articulated segments of the wing removes this non uniformity.

The deflection of trailing edge flaps symmetrically in methods and aerial vehicle of the invention achieves an increase in the sectional lift coefficient to the extent that the yaw control effectiveness is uniformly positive across the flight envelope. It is well known that trailing edge flaps increase the sectional lift coefficient and calculations from thin airfoil theory show that this increase in lift is much more than the increase in the magnitude quarter chord pitching moment coefficient. However this use of trailing edge flaps runs counter to intuition for improving the yaw control authority and would have been generally viewed flap deflection increases the wing camber which is in principle responsible for a non zero quarter chord pitching moment in the first place.

While specific embodiments of the present invention have been shown and described it should be understood that other modifications substitutions and alternatives are apparent to one of ordinary skill in the art. Such modifications substitutions and alternatives can be made without departing from the spirit and scope of the invention which should be determined from the appended claims.

