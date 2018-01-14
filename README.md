# Brian's perambulations
## 2018-01-12

Our goal is to find out time for NTT with support for full range of values describable by a word-packed floating-point number. We should remember that we also care about absolute upper bound on number of words to support such input floating-point numbers. We will assume the word size is interchangeably m' or w.

For the following, we are in general discussing FFT.

We assume that a is input coefficient max. magnitude and b is vector length.

### Time for our application

For forward FFT (via WHT, complex, NTT), output coefficient magnitude is bounded by b \* a. For convolution of two time-domain signals with same input coefficient max. magnitude and vector length, output time-domain signal coefficient magnitude is bounded by b \* a ^ 2 (for intermediate calculation, magnitude is bounded by (b \* a) ^ 2).

Next, we add a detail: a == 2 ^ m.

T_1 = log(b ^ 2 \* a ^ 2) / m' = (2 \* log(b) + 2 \* log(a)) / m' = (2 \* log(b) + 2 \* log(2 ^ m)) / m' = O((log(b) + m) / m')

Then, we make an assumption: m = O(m').

=> T\_1' = O(log(b) / m')

And we would stop here, except if we make a second assumption: b and m are related s.t. b = O(m).

=> T\_1'' = O((log(m) + m) / m') = O((2 \* m) / m') = O(m / m') = O(1)

This means that if we make the two previous assumptions, FFT time is:

T\_2'' = O(b \* log(b) \* T_1'') = O(b \* log(b))

We note that if, instead of b, we prefer the letter n, we have time of O(n \* log(n)).

### Pitfall from a particular thread

We deviate from what turned out to be an assumption made by someone else that at one point in time made us worry that the time for FFT is possibly O(n \* log(n) ^ 2). We don't have enough karma to post a comment directly to someone else, so we are recording our logic for posterity here. We should note that the assumption of significand size b = O(log(n)) is totally arbitrary. An equally plausible situation is b = O(w). Then, assuming we have floating-point numbers that fit in a word (of size w) and assuming that word operations generally take O(1) time each, time will be O(n \* log(n) ^ k) with k == 1, given that we want to support all numbers representable by such a floating-point number. Also, of course, Blaeser is being generous to Jeffε s.t. technically O(n \* log(n)) is in O(n * log(n) ^ 2).

Ultimately, the point is that they made a specific assumption that does not apply for our application; we should also note that they ascribe different meaning to the variable b; they have it as output significand size in bits and we say b is size of input vector.

### About conventions

A second source describes bound for each output coefficient for NTT-related convolution.

Nayuki adheres to convention that convolution is s.t. we take two time-domain vectors and return a time-domain vector.

Also, they say that if we have as input two vectors of length n s.t. each input coefficient is at most m, we have an upper bound on each output coefficient of m ^ 2 \* n.

They are talking about starting with pre-NTT vectors for the input and the output is after inverse NTT; we go from (n \* m) ^ 2 to m ^ 2 \* n because for inverse FFT, we divide coefficient upper bound by n.

### Next step

We can proceed with Zhang; we will need to justify the time and steps for it.

### Other

Also, due to Bertrand's postulate, we get good proximity to a prime for NTT.

Resources:

* Blaeser - Stack Exchange - Complexity of computing the discrete Fourier transform? - Comment (2011)

  https://cstheory.stackexchange.com/questions/8196/complexity-of-computing-the-discrete-fourier-transform

* Project Nayuki - Number-theoretic transform (integer DFT) (2017)

  https://www.nayuki.io/page/number-theoretic-transform-integer-dft

## 2018-01-10

We have to remember that we have two staircases for each point arrangement, of which we have two.

We realized that for a 2-D segment tree, we don't have overall O(n) leaves for lower-level trees unless we use fractional cascading. Then, we will do so and choose an arbitrary lower-level leaf for each of O(n) points and make sure that we do so consistently. This cuts down range-tree contribution polylog(n) = O(log(n) ^ 2) to O(log(n)), which keeps the bottleneck polylog(n) factor at O(log(n) ^ 3). We note that we had a factor of O(log(n) ^ 2) already due to inflation from multiple passes of FFT.

A big problem is to be able to encode into or decode from binary RLE form for each memoized (not path-related) signal for nodes. We don't want to cause for time to have another O(log(n))-factor. Instead, we can convert signals into binary RLE form in time linear (and not involving a factor of O(log(n))) in number of non-all-zero words in signal. For conversion, we perform "spotting" (in the sense of the word "identifying") by skipping across all-zero or all-one words and eating into the interior side of a boundary word to get all-one or all-zero repeats quickly, which can be done via "bit-finding" operations: (1) O(m / m')-time (which is constant if m = O(m')) right-most one bit for NOT'd signal determination; or (2) left-most zero bit determination. For the former, we don't use Anderson and we do use Shankar, which uses XOR and AND and subtraction. For the latter, we normally have to reverse tiles which takes O(m / m' \* log(m')) time and use right-most one bit for NOT'd version of this reversed signal. This means we incur a cost of log(n) at a bottleneck, leading overall polylog(n) to be in O(log(n) ^ 4); instead, we reverse tiles immediately after multiple FFT passes are altogether done and maintain them so that we don't incur this extra O(log(n))-factor cost for RLE overlay operations when we are doing sum-related memoizing for lower-level leaves in 2-D range tree. Then, we incur an extra O(log(n))-factor cost for after multiple FFT passes altogether (which had overall polylog(n) = O(log(n) ^ 2)), leading the time for immediately after multiple FFT passes altogether to be overall polylog(n) = O(log(n) ^ 3), which is tolerable. We don't use expensive logarithm for the "bit-finding" operations; we go from shifted one-bit, which we get from "bit-finding" operation and go to mask directly, without finding binary offset from right or left edge of word.

An important step towards having this suitable time is to be able to find right-most one bit for NOT'd signal or left-most zero bit in constant time (or, specifically, O(m / m') time) instead of O(log(w)) (where we are interchangeably using m' and w). This allows us to replace runs with code-words efficiently, assuming that we have a threshold for turning repeated zeroes (or ones) into runs s.t. we do so if the number of repeats is at least w. The binary RLE form can also be a list without incurring asymptotically more space or time cost because of this threshold.

When we have binary RLE forms of signals, we can avoid encoding/decoding steps by being able to perform addition via overlay directly for two operand binary-RLE-form signals and we get back another binary-RLE-form signal. We estimate that the time for this will be linear in twice the number of non-zero words in the modifying RLE associated signal via middle-man code-words (we note that this needs a more detailed proof), assuming runs have min. length of w.

We are essentially dealing with topology for RLE-related encoding, overlaying, and trie preparation in the sense that we do for e.g. higher-order Voronoi via Zavershynskyi/Papadopoulou and their detailed circle events.

We note that a maximally-large sequence of adjacent non-runs is technically a code-word (i.e. it is a "glial" code-word).

We are starting to get some hope that we will attain time complexity of O(m / m' \* n ^ 2 \* log(n) ^ 3).

How do we prepare binary RLE trie and use it during a query to quickly get a final (i.e. totally completed for an output cell) floating-point scalar? This question is an urgent one; we mistakenly assumed that trie query will give us the final answer, when in fact we still have union-intersection arithmetic, which can involve subtraction and thus catastrophic cancellation. However, perhaps we can instead push adding of row or column "source sizes" to lower-level-leaf memoizing phase s.t. signals have sign negated and have row or column "source size" (based on whether we have for a leaf a point for a row or for a column) signal added.

For including row and column sizes during memoizing time, we have for O(n) children an operation that costs O([(m \* n) + (m \* n)] / m') = O(m / m' \* n) time; this is due to having first subterm via summing components for a row or column and second subterm via size of a one-bit run. This way, trie query will give us final answer without more muddling about with floating-point exactness.

Important remaining questions:

* How exactly do we "spot" and convert to binary RLE form quickly? (We know that it is probably possible, but we have to be very clear.)
* When do we apply Parseval's theorem multiple times?
* When do we apply (false?) interleaving/de-interleaving?

Edit: As for how we apply interleaving/de-interleaving, we do the following.

We should remember that we have false de-interleaving in between FFT passes; this leads to overall polylog(n) = O(log(n) ^ 3). However, while space inflation affects de-interleaving time, de-interleaving does not affect space inflation, so we can proceed with O(log(n))-time reversing for each word and still have overall polylog(n) = O(log(n) ^ 3).

We merge inflation-related signals as part of summing-memoizing for 2-D range tree nodes; we already factored in the time increase needed (of a factor of O(log(n) ^ 2)) as part of later steps; different same-component-same-row-or-column contributors are shifted by single powers of two; we benefit from each such signal being of size O(m) s.t. we still can take advantage of word-level parallelism and divide m by m'.

In a sense, because we use false interleaving and we are lucky with sizes being O(m), we don't need re-interleaving and can just shift and add; what about shifted word boundaries, though? We respond by having word-parallel bit-shift for these inflation-related size-O(m) signals.

We may now, then, have as following the actionable step of implementing word-packed NTT FFT convolution with all-ones vector via Zhang.

Relevant resources:

* Anderson - Bit twiddling hacks - Finding position of highest bit set (2005)
* Shankar - Stack Overflow - How to get position of right-most set bit in C (2016)

## 2018-01-09

We have made quite a bit of progress.

We have figured out a way to have exact floating-point arithmetic tailored for our application. It does not use Kahan summation or Kahan-Babuska summation or Demmel-Hida.

The key is we use binary run-length encoding (RLE) for signals stored at each node. The concern is that when we add, we are allowed to spend time related to the size of the modifying signal, but cascading overflow can be very expensive. This is not the case with RLE. For the boundary of the modifying signal, we eat into code-words within a boundary word (or spanning a small number of boundary words) and each code-word is quite small and has size related to n and m; we can also opt to only consider repeated 0's or 1's a run if they are at least the size of a word (in terms of bits).

Binary RLE can be used for not only addition, but subtraction; in the latter case, we possibly have cascading underflow and possibly repeated ones, which can be marked by a flag.

We memoize path-related values for each lower-level leaf in "union tree". There are O(log(n)) paths involving a lower-level leaf bleeding into both layers (lower and upper) and involving a node that is some descendant (or identical to) the upper root. Our main concern here is that the operation be affordable enough; our tactic is to sum signals for whole path (from a leaf to upper root) and then subtract starting at upper root and moving down to the specific leaf. This is a way of making sure our overall polylog(n) factor is in O(log(n) ^ 3); this time also takes into account inflation of signal size by a factor of O(log(n) ^ 2) due to multiple passes of FFT.

Also, for FFT, we note that if we wanted to collapse signals earlier (which we don't), we can do so cleanly if we require that vector sizes are powers of two (because then we reduce size of signal in a kind of application of inverse FFT via Parseval's theorem by bit-shifting right and we have satisfactory, i.e. unchanged, number of words or tiles involved after collapsing); this repeated rounding to nearest larger or identical power of two between logarithm applications affects binary iterated logarithm s.t. we have identical behavior as binary iterated logarithm because the right bound for each interval for a given output value in [0, 5] is itself a power of two. At any rate, we drop this aspect because we have a way of making determination of path-related memoized values for each lower-level leaf cheap enough already (as described in previous paragraph).

This trick that saves us time for path-related memoized values mentioned two paragraphs ago is our third instance of "inverting a universe", so to speak.

We have a way of pre-processing to speed up subtraction s.t. we can use it to combine two (possibly differently-signed) memoized values via addition (resp. subtraction) quickly enough for query time; for this, we use a compressed trie with edges corresponding to words (and not code-words from previous binary RLE). We have to return to this later.

Also, as we previously hinted, we want to avoid depending on having vectors have lengths that are powers of two. This is why we chose to have the path-related memoized values for each lower-level leaf determined using full sum and gradually subtracting as we move in a second pass from upper root to the leaf.

We don't use super-accumulator; we have no fear of overflow due to having binary RLE (though the details we need to go into again - addition-related cascading overflow never proceeds to the left past a zero and subtraction-related cascading underflow never proceeds to the right past a one and we can have repeating one bits for subtraction case, for which we can have a flag). However, we had widened bins so that we could temporarily avoid cascading overflow for a canonical number and this is similar to having super-accumulator; also, we figured out that larger offsets s.t. we have two bins for each power of two instead of O(log(n)) can be easier to work with. At any rate, we no longer pursue super-accumulator (because, again, we have binary RLE). And, of course, we are assuming that wherever necessary, we have word-level parallelism s.t. we divide time by w (or as we have taken a liking to saying instead - m').

An advantage of the fully-specified approach is that we have two values to combine for any given query; this way, we can straightforwardly use trie to find sum of the two values if the two values have opposite sign or some more straightforward way for if the two values have the same sign (i.e. in this case, there is no catastrophic cancellation).

We still have to figure out how to deal with repeating-one suffix flag that we may encounter for trie for query-time subtraction.

A problem that remains is how to convert to binary RLE form and back in bit-wise parallel.

## 2018-01-07

We currently have compressed trie with LCA with widened bins to avoid cascading overflow and tiles.

We thought we could replace this with sort-less Kahan summation with meta-floats and tiles, but we did not notice that the error is acceptable only if condition number is small. In practice, condition number can be huge. This is even if we carefully choose allowed relative error and machine epsilon, which both are based on significand size in terms of bits.

We believe we can make do with generalized Kahan-Babuska summation because while we do some sorting, it is very local; there is only one loop even with order equal to two. This means that the algorithm, even for higher orders, is embarrassingly parallelizable. This in turn means that it is more straightforward to divide work between nodes and later combine.

Edit: It turns out that Kahan-Babuska has accuracy not independent of condition number, as well. So, we are stuck.

Articles of interest:

* Klein - A generalized Kahan-Babuska-summation-algorithm (2005)
* Zhu et al. - A new distillation algorithm for floating-point summation (2005)

## 2018-01-05

We need to revise f.p. MM article and come up with diagrams. Unfortunately, I don't have access to a drawing tablet currently; so, we will have to draw on paper and then scan the pictures. Through this process, we will hopefully get a better picture of the details for the algorithm (e.g. in what manner do we apply FFT, take advantage of packing, and use bit de-interleaving and use tiles).

It snowed quite a bit yesterday and it is quite windy outside today.

## 2018-01-02

We had a small moment of doubt when it comes to Nuetzi hybrid de-interleave, but it turned out that we were double-counting a log(n) factor.

Zhang NTT FFT describes word-packed convolution; we can, if necessary or if only to make appropriating of the technique mentioned in the article easier, view Fourier transform as a special case of acyclic (or padded cyclic) convolution s.t. one vector is all ones.

Also, we note that Nuetzi hybrid approach that we mention requires that the vector size be a power of two; we can use zero-padding for this.

Also, we found copies of Anna Karenina and The Count of Monte Cristo.

## 2017-12-30

We believe we have an approach for floating-point MM that takes time O(m / m' \* n ^ 2 \* log(n) ^ 3).

We had to add a lot of details for having exact floating-point summation.

The result is that the cross-over point relative to brute-force MM is approximately c \* 981 for small c; c could be, say, 15.

## 2017-12-18

It turns out that we need to modify both our floating-point MM article and details previously added to this blog.

We wish to have p-way q-bit interleaving and de-interleaving and with history; as it turns out, our standard p-way q-bit approach does not have history. Also, false p-way q-bit interleaving (i.e. without any interleaving at all) supports history in a fairly straightforward way. Also, we have reason we like false approach irrespective of history support - it is free, as opposed to introducing a factor of log(n) ^ 2 to one of our bottlenecks, which prevents overall factor from becoming log(n) ^ 5, and keeps it at log(n) ^ 3.

Also, polylog(n) factor for repeated FFT passes and iterated logarithm is in O(log(n) ^ 2), not O(log(n)); this is a result of having at most around five FFT passes.

Also, we still have Demmel-Hida-related log(n) factor.

If we are still interested in showing time for standard p-way q-bit interleaving, we should assume (if we assume at all) that p = O(n) and q = O(m \* log(n) ^ 2), not that q is just in O(m \* log(n)).

Also, of relatively great importance is to note that narrowing of downward filter makes finding complements for a node affordable enough; this is not just for rational case; it is for floating-point case, as well. The concern is that in the worst case, we cannot just pre-maturely truncate, as finding complement (i.e. by subtracting union) means the result significand could move quite far to the right before we get a result one bit for later use for a query.

A current goal is to implement standard p-way q-bit bit interleaving and de-interleaving (s.t. we use magic bits) anyway.

## 2017-12-15

We can have p-way q-bit bit interleaving (i.e. n-d Morton code) via three possible ways:

* Brute-force - time is O(m / m' \* p \* q)

  We spend O(1) time per bit, of which there are p \* q. We are fairly fine-grained and we even generously assume we have blocking. This is too expensive.

* Nuetzi original - time is O(m / m' \* p ^ 2 \* log(p) \* log(q))

  This is good for d = 2 s.t. p == 2. We use pre-computed magic numbers, but we are too coarse by having expanded signals. This is too expensive.

* Nuetzi hybrid - O(m / m' \* p \* log(p) \* log(q))

  Presumably, we pre-determine calculate magic numbers for each unique level in the n-d Morton code call tree. This is cheap enough.

m is essentially q and m' is word size.

Nuetzi approach is 2-way q-bit bit interleaving.

The two Nuetzi approaches use divide and conquer.

These approaches have been for forward Morton code transform, but we can also have the same times for reverse Morton code transform as long as we replace 2-way q-bit bit interleaving with 2-way q-bit bit de-interleaving. The latter we have not come across a general approach for, though we can deduce what we would need by extrapolating existing approaches for certain fixed bit-sizes that we have come across.

Also, we don't quite understand how Zhang packed FFT works, but it is likely better than un-packed FFT or else they would not have published it.

Current resources of interest:

* Anderson - Bit twiddling hacks - Interleaving bits (2005)
* Giesen - Decoding Morton codes (2009)
* Nuetzi - How to compute a 3-d Morton number (interleave the bits of 3 ints) (2013)
* Nuetzi - Produce interleaving bit patterns (Morton keys) for 32-bit, 64-bit, and 128-bit (2013)

## 2017-12-10
Working on a number of projects.

The idea behind this is that, presumably, we have a tighter feedback loop s.t. we make changes more (even if just in sentences) and lower the threshold to making forward progress. On the other side, however, our changes are visible for all to see. At some level, though, this downside may be something that would have cropped up anyway by the time we came up with a more robust solution (with a history).

Projects

* Hoedt/Arndt/Giesen - p-way q-bit interleaving (i.e. n-d Morton code)
* Zhang - packed NTT
* Voronoi - sweep-line approach with numerical robustness, overlay, polygon pointers, point location
* order-k Voronoi - sweep-line approach by Zavershynskyi and Papadopoulou
* fast floating-point MM - with certain assumptions, we can have sub-cubic time
* portfolio - possibly use Flex with prism theme and state-transition diagrams	
* CS 61A (Fall 2007) - go through exercises and projects
* Close-prime-finding algorithm and time guarantee?
* edX - software engineering (i.e. CS 169) for SaaS and with agile and RoR - basics, advanced, certificate?
* coursera - func. prog. principles in scala
* collect documents about Addteq
* brush up on par. programming with intrinsics?
* follow up by contacting headhunters?
* ship sold book
* donate unsellable items (e.g. music cds, dated books)
* organize emails more
* update resume and job profile
* play piano
* watch bleach? (there are 16 seasons and four movies)
* organize photos
* finish assigned reading from senior year (Fall 2006 to Spring 2007) AP English Literature
* find classwork for high school junior/senior years and preserve/bundle (e.g. for AP Biology for junior year and Lit. 12 for senior year)

Papers

* Zhang - Fast convolutions of packed strings and pattern matching with wildcards (2017)
* Zavershynskyi and Papadopoulou - A sweepline algorithm for higher order Voronoi diagrams (2013)
* Fortune - A sweepline algorithm for Voronoi diagrams (1987)

There are, of course, many more papers for fast MM.

Questions

* Should we add more personal details - e.g. course history, apartment buildings lived at, books read?
* Should we attempt Project Euler?
* Which projects and for which classes should we go over again?
* Should we add past project details - e.g. fixing laptops, tactile interface, etc.?
* Should we add more projects - e.g. IoT kit, mirror interface, 3-d printing device?
* Should we write more about past internships - e.g. Alzatex, LTT, Cohorti?
* Should we write about certain company-specific HackerRank competition problems and our solutions for them?
* Should we write about job interviews and technical questions?
* Should we write about high school projects - e.g. for robotics, invention program, student government?
* Should we write about how we spend our leisure time - e.g. television, movies, music, sports, traveling, family?
* Should I keep a list of movies watched?

Miscellaneous

* BU book club (Fall 2017) - have read The Nightingale, In Cold Blood, Before the Fall, Persuasion, part of Boston Noir
* AP English Lit. reading - Brave New World, Pride and Prejudice (halfway through), Oedipus, Heart of Darkness, The Return of the Native, Hamlet (done), Mythology (done), Uncle Vanya, Great Expectations (done), My Antonia, Macbeth (done), The Importance of Being Ernest, Crime and Punishment, Madam Bovary
* have not obtained - An Introduction to Fiction (Kennedy/Gioia, 9/10), Sound and Sense (Perrine, 9/10/11)

Private matters

* medication - clozapine (200mg nightly, dispensed at clinic), glycopyrrolate (2mg nightly), oxybutynin (5mg nightly), docusate (50mg occasionally), senna (8.6mg occasionally)
* phlebology - once every two weeks
* psychologist - once every two weeks
* family appointment for psychologist coming up (jan. 22, 2018 at 11am)
* make appointment to see endodentist for root canal and crown for tooth #15 (upper molar); attempt to compare prices given that current dental insurance does not cover these two operations at all

Addendum

We thought that we would need Rader FFT (which is noted to be compatible with NTT) given that we have unusual-size signals (i.e. not power of two). Instead, we can just zero-pad and take advantage of concavity and say that our time is worse by a factor of slightly more than two. The idea is that Fourier transform is defined even if signal size is not a power of two and if for some reason we want a non-padded post-Fourier-transform signal, this would imply that we ought to use Rader or Bluestein. Again, we are content with zero-padding the time-domain signals. 

The papers associated with Nevin that were of interest to us were:

* Rader - Discrete Fourier transforms when the number of data samples is prime (1968)
* Nevin - Application of the Rader-Brenner FFT algorithm to number-theoretic transforms (1977)

It occurred to us that we mistakenly took two articles about n-dimensional Hilbert transform as for n-dimensional Morton code. However, while we have encountered a setback, it also occurs to us that we might be able to define n-d Morton code via recursive application of 2-d Morton code transform, the implementation of which is more often mentioned. Also, we should note that the point is to use word-parallel approaches (i.e. those that use "magic numbers"). By using repeated 2-d Morton code transform, we may need to zero-pad, with an extra cost of around a factor of slightly more than two.

The papers associated with n-dimensional Hilbert transform that we were interested in were:

* Lawder - Calculation of mappings between one and n-dimensional values using the Hilbert space-filling curve (2000)
* Skilling - Programming the Hilbert curve (2004)

A final pressing concern is: is Zhang packed FFT really enough, given that the factor u is related to max. component magnitude and alphabet size, even if we are word-parallel?


