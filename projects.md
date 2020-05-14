## 2020-03-10

### Projects

#### Sugar 3-D Printer

It's a plotter that solidifies powdered sugar via a moving soldering iron.

#### "TouchGraph" 2-D Tactile Display

We use 3-D-printed filter boards for discrete Fourier transform.

Let n be the side length of a display.

Instead of needing O(n ^ 2) solenoids (i.e. one for each cell in the display), we use O(n * log(n)) layers, each controlled by a servo-controlled air valve. With n equal to eight, n ^ 2 is 64 and n * log_2(n) is 24.

We use concept of tension to make sure air spreads evenly.

We used to consider spinning layers s.t. we use moving liquid O-rings.

Refresh rate will be quite good -- e.g. four seconds for a frame.

Using Moire-beat patterns for filter is not enough because there could be inaccuracy due to leakage.

Have parallel master valve for each layer via using a sliding plate with liquid O-rings (that involve ferrofluid and electromagnets).

What about coefficients for frequency domain being values other than zero or one?

How do we merge patterns for the layers?

Consider if we have one layer that is associated with a basis function. Then supplying air until taut is enough.

If we have two layers, then what? It may help if we assume output cells are zero or one.

Perhaps we consider complement signals to have subtraction. Then, a zero for output cell may correspond to a non-zero amount of air in a cell. Negative signal corresponds to some positive amount of air, possibly. Also, we can seal both ends of a valve so we can do subtraction with tautness.

How do we transition between patterns?

Attempt static picture first.

Air displacement filler, meta-cell (with buffer pair swapping not as luxury but required to get cells that resist force from user's fingers), number of pumps and layers required in O(n) and not in O(n * log(n)) if we decompose into 2-d patterns with 1-d variation and we repeat use of these patterns, we use manual "straining" to push air into interface at bottom and for each layer

symmetric tongue lattice, hydrophobic coating

instead of lattice, have rod-shaped dividers

problem is that if we have O(n) layers that we take O(n) electromagnets for each layer and thus overall we have O(n ^ 2) electromagnets, which is too much; is there a way to only use one electromagnet for each layer? maybe if we rotate each layer (i.e. not like spinning a CD, but like spinning a cam) instead of translate; this growth order is acceptable (in a sense) if we use printed electromagnets for each layer because then in a sense we have o(1) electromagnets for each layer

if we use moire beats in one dimension for 2-d, assuming output signal is binary for each cell then we have (via parseval's theorem for energy s.t. we calculate sum of coefficient magnitudes for frequency domain) O(n)-factor increase in time required to draw a signal, but (ignoring machining of holes for layers) we only require O(n) items (as opposed to O(n ^ 2)); we must take care to machine holes precisely and probably the signal is not perfect when we draw using this approach; we have three layers given that two are for achieving a beat and a third is for shutting all holes; actually, we need perhaps six layers given that one group of three is for x and one group of three is for y; then, we have x-signals and y-signals that are effectively 1-d; similar to with BMM, input signal (i.e. for time domain) is binary (i.e. zero or one)

dot product of two 1-d signals is dot product in frequency domain divided by some value (i.e. dimensionality of the signal?); this is different because while for drawing we also deal with binary signal in time domain, we are collapsing after going to frequency domain in a different way; still, we are able to upper-bound sum of coefficient magnitudes in frequency domain assuming time domain signal is binary by considering energy and parseval's theorem for drawing application s.t. magnitude sum is in O(n) (!)

we use displacement filler as a way of being able to handle negative frequency domain coefficients s.t. we always push (and do not pull)

--

peristalsis, discrete moire, rounding up, overpressure valve (e.g. as from a pressure cooker)

what is the correct discrete moire pattern?

have a pair of shifting pair of plates so that when one plate pair's throughput is <= 0.5 that we round down and with throughput > 0.5 we round up to recover symmetry (relative to e.g. only using one pair s.t. we always round up); note that the plate pairs approach center from opposite directions for effective discrete moire pattern

have "glial cells" s.t. if we connect cell and compartment(s) outside cells we get good behavior as long as we stop when we are taut

have plastic origami (similar to with plastic grocery bags) so that we can have zero volume up to some max. finite volume

we can have same complexity for time required to display an image as if we print piezo cells (i.e. in O(n ^ 2)) if we have O(n) detail (e.g. number of electromagnets) for each layer and if we have O(n) layers; this means we use O(n ^ 2) details total again and we have O(1) time for displaying an image; the advantage is that we have a different 3-d printing approach than if we have piezos and we possibly have less ideal details such as depth of the display

## 2020-05-11

Airways and mediating balls.

Inspired by Moire pattern and possibility of liquid o-ring via ferrofluid and electromagnets.

So far, we use neither Moire pattern nor liquid o-ring.

We have O(n) layers and continuous air pump. We have overflow valve (similar to with pressure cooker) tuned via spring and screw. Coefficients for each layer is in O(n). Since we do not have discrete chunks of air being pumped, we use calculus (i.e. integration) to predict when to twist a lid with rubber or felt cushion into position to stop collection of air for a cell. Each layer has a fixed pattern related to Fourier basis s.t. we have 2-d pattern with 1-d waves; this differs from Moire subtlely given that we do not have partial airway openings. We use servos or stepper motors to control airway lids. We use double buffering and displace a mediating sphere for each cell; we have two subcells for each cell. We may need to empty containers of their air quickly via second air pump.

We may wish to have trade-off s.t. depth for a given layer is lower in magnitude, possibly at expense of width or height of display. We may wish to take advantage of fact that target size tends to be constant, so tower size tends to be constant; rectangular prism of display s.t. depth is for tallness of a cell staying roughly same even as resolution increases (i.e. width times height is resolution). Using twisting of lids means less friction than sliding when our edges have e.g. rubber. Continuous motion is preferred for less vibration. We aim for one frame per two seconds at first and screen of size four by four. We use grease, possibly, as with a real automobile engine.

We are making more progress by assuming we do not use Moire and liquid o-rings.

We can make a proof of concept.

We can also eventually use output cells whose values are not just in {0, 1} but in [0, 1]; this may require continuous movement together with calculus for anticipatory lid twisting. We consider lid twists as with e.g. buttons on an instrument such as a clarinet. We assume we re-zero after each frame for each subcell machine, so some error may be acceptable.

We may be able to make a first prototype out of Lego.

Our goal is to make this more affordable than brute-forcing with O(n ^ 2) solenoids.

Syringes -- relating distance to volume. Use Walsh-Hadamard transform. Higher resolution for same width and height and depth means each cell has lower max. volume.

You would expect there to be a lot of friction in a real engine with pistons, but part of it is alleviated via engine oil; and, automobile engines tend to survive for a relatively long time.

We assume that to simplify the calculations (usually involving integration and air pump force and target frame rate) pressure is equalized as we pump air.

We ought to consider resistance against pushing. Also, consideration of displacement is necessary for us to always be dealing with pushing air for forward stroke instead of both pushing and pulling air for forward stroke.

Our goal is to eventually be able to force relative correctness s.t. we can push up frequency and still get correct signal in output display.

Nice thing about sphere for mediating sphere at tip of each cell is that has no best orientation.

We may wish to have airlocks (in some sense?), so we may need to multiply number of parts (even those that are expensive such as servos) by a constant factor again.

We note that e.g. a grandfather clock is able to turn a constant force (i.e. gravity) into discrete chunks of movement (i.e. for the arms of the clock via machinery). A pressure cooker has for the overflow valve the force of gravity pushing it so that when we do not have high pressures we do not have a gaping hole in the lid.

In principle we have a closed system when it comes to air used. In practice, we will be pushing out air to and pulling in air from the outside. Air pump may or may not be loud.

# 2020-05-13

No reason to use 2-D Fourier basis, even with Walsh-Hadamard transform. (Apparently JPEG-XR uses Walsh-Hadamard transform?) The only benefit of JPEG is that we can drop high frequencies when we are in frequency domain; we still require O(n ^ 2) time to display an image that is in frequency domain representation.

So, we decide to drop using frequency domain.

We have a spinning drum. The nozzles/valves are on the inner side of the drum. We have lubricant (to reduce wear and noise) and spring plates for purpose of having air-tightedness. Pursuing low radius helps make the energies required lower. We have both overflow and underflow valves. We have rest segments. We have a push row and a pull row.

We have funnel adaptor to lead to a small interface.

We use Hall effect sensor to track drum rotation so the machine can be used even as we crank by hand (assuming we do not crank too hard).


