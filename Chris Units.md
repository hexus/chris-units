---


---

<p>Time: millisecond (<code>ms</code>, 1/1000 of a second)</p>
<p>Length: pixel (<code>px</code>, quantum of virtual space)</p>
<p>Force: Moonbat (<code>mb</code>, who the fuck knows)</p>
<p>Mass: shit-tonne (<code>st</code>, mass of an object such that if a constant one Moonbat force is applied to it for one millisecond, it has a speed of one pixel per millisecond)</p>
<p>Engine uses time units of frames (<code>fr</code>, 1/60 of a second). When converting from frames to ms, then:<br>
1ms = 1/1000 s</p>
<p>= 1/1000 * 60 * 1/60 s</p>
<p>= 60/1000 * 1/60 s</p>
<p>= 60/1000 fr</p>
<p>And so, when converting the bastard verlet formula from fr to ms:</p>
<p>v’ = v + F/m * dt<sup>2</sup> (bastard verlet formula)</p>
<p>v’ = v + F/m * (dt’ * 1000/60)<sup>2</sup></p>
<p>v’ = v + F/m * (1000/60)<sup>2</sup> * dt’<sup>2</sup></p>
<p>v’ = v + F/(m * (60/1000)<sup>2</sup>) * dt’<sup>2</sup></p>
<p>v’ = v + F/(m * (0.06)<sup>2</sup>) * dt’<sup>2</sup></p>
<p>v’ = v + F/(m * 0.0036) * dt’<sup>2</sup></p>
<p>So for the bastard Verlet formula without drag or time-step correction, a mass correction of 0.0036 will convert from frames to ms. This is a coincidence and should not be relied on.</p>

