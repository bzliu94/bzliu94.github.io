# Brian's perambulations
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


