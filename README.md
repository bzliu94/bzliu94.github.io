[Taken courses](taken-courses) · [Class repair](class-repair) · [Undergraduate freshman year dorm floor layout](freshman-year-dorm-floor-layout) · [Projects](projects) · [High school details](high-school-details) · [Big personal problems](big-personal-problems) · [Gambles](gambles)

<img title="A gem" src="shape1 - cropped, resized, and cleaned.png">

# Brian's perambulations
## 2021-01-19

We also want to upload our work on Thorup/Zwick 2005 and Thorup/Zwick 2006 first spanner and emulator. We do not see a way of using them for our lax BMM application, but given that we spent quite a bit of time going through aforementioned two articles and identifying typos and mistakes, figuring out ways to fill in missing proofs, and understanding the important bits of reasoning, we believe we should make implementations for them more widely available. Much of the content of the articles is in proving theoretical bounds (e.g. by showing existence of certain relatively short paths).

## 2021-01-18

As much as we would like to highlight the tasks we have regarding AP English Literature, we also would like to get back to the benefit of having a blog -- being able to update and feel as if we're making progress every day.

Much has happened in our quest to get competitive lax BMM algorithms. We have an O(n ^ 2.4)-time approach based on Durocher et al. 2011 range mode query and reduction via Wilkinson 2012. Then, we have an O(n ^ 2.18 * log(n))-time approach based on bootstrapping/boosting using Berman/Kasiviswanathan 2007 (1 + epsilon, 2) approximate distance oracle for directed weighted input graphs with three-layer graph. Finally, we believe we may be able to get an O(n ^ 2 * log(n) ^ 5)-time algorithm based on Gutenberg et al. 2020 approximate weighted incremental SSSP via Roditty/Zwick 2004 reduction by extending to have number of substructures not in O(log(n)) but in O(n * polylog(n)), storing pre-emptive distance estimate minimums and argmax-related structures, changing base and thresholds so that we support epsilon >> 1, and using exponent-based implicit numbers. The actual time, assuming the approach works, we estimate may be larger or less by at most a factor of up to O(log(n) ^ 2).

## 2020-08-29

We have eight links that we ought to skim through to find out about miscellaneous writing activities for AP English Literature.

### Blogs or course information pages

Ms. Minor
* 2008-2009 (blog)  
https://wviewaplitminor.blogspot.com/

Mr. Duncan
* 2008-2009 (blog)  
http://wviewaplitduncan.blogspot.com/
* 2009-2010 (blog)  
http://duncanwildcatap.blogspot.com/
* 2010-2011 (blog)  
http://mrduncanaplit.blogspot.com/

Mr. Hardin
* 2008-2009 (blog)  
http://wviewaplithardin.blogspot.com/
* 2009-2010 (blog)  
http://hardinwildcatap.blogspot.com/
* 2010-2011 (blog and course information page)  
http://hardinwildcatap2.blogspot.com/  
https://sites.google.com/a/beaverton.k12.or.us/ryanhardin/

## 2020-08-28

I had been hoping to avoid adding blog entries until I am ready to directly tackle conversations for class repair endeavor. However, avoiding use of blog is in this situation beginning to have a non-trivial negative effect on my productivity. While now the gap between when we were once freely considering matrix-multiplication-related algorithms (from November 2019) and when we will be ready to work directly on writing an article on that subject will not be as clean, the alternative is that we push the date when we are ready to write the article back. The more we push dates back, the more there is risk that we may get front-run. Of course, we are also excited by the idea of writing said article and so being able to return to writing blog entries also has a separate good effect on morale. We are overly fetishizing the nadir to the extent that we are trapping ourselves in it. Also, the straw that breaks the camel's back is a conversation we are having with a teacher for purpose of re-constructing details for an AP English Language class from senior year in high school that we believe we can end earlier and with better outcomes if we first relieve some of the stress on our mind that results from having a large backlog of ideas and details that we have not yet committed to paper or electronic documents.

I talked to a psychiatrist today and they suggested that I perhaps do not have to force myself to not multi-task for some definition of multi-tasking, even if it seems to me that currently I have to be quite careful with certain tasks facing me currently (e.g. the conversation with a high school teacher).

Where do we begin? Our backlog is so large. Even though we have breadcrumbs spread across many dated notes, doing justice to our thought process will take some effort.

Our birthday is coming soon -- we will be turning thirty-one.

I have an idea of a page for our GitHub website that covers scientific details that we find quite meaningful. For example, that power lines may look covered but may just be coated with material for purpose of being resistant to weather and may not be covered s.t. they are non-conductive. That the explanation of how electric energy or signals can travel at close to speed of light because it's better to consider electic behavior using idea of fields instead of primarily electron movement; the changing fields lead movement in electrons. That chemical bonds release or absorb energy based on trapping energy -- if energy cannot be trapped, then energy escapes. That this touches on how nuclear fission bombs work -- we have a favorable nuclear fission isotope trend s.t. nucleon binding energy decreases; if we know how much of each isotope we end up with, we can then estimate energy released and because the energy released tends to be quite large it also becomes reasonable to re-describe that energy using mass -- such overall mass change can be called mass defect. Microwave ovens heat because field gets consumed. Special relativity results from assuming speed of light is constant and what happens when one considers non-accelerating reference frames; general relativity results from assuming the same thing but when one considers possibly accelerating reference frames; clearly, non-accelerating is a subset of possibly accelerating. One wonders whether if a person who is accelerated to close to the speed of light that not only do they age more slowly but also that they via their interactions with any surrounding structure moving at the same speed (i.e. things stationary in the reference frame of the fast person) still perceive time to be moving at an unimpeded rate (of course for some definition of "unimpeded"); this seems to be assumed to be the case by many who consider twin paradox for special relativity. We still do not quite grasp resolution of twin paradox for SR. Christmas lights that are roughly wired in series still can work if many bulbs sequentially fail because short-circuits form that allow current to flow past each broken bulb (though this makes each bulb a little bit more expensive). Also, we believe we can think about quantum computing as being about preserving a pre-collapse world, choosing worlds, and making sure the environment is sterile. Correspondence principle when applied to double-slit experiment says that with enough particles we get classical physics; also, Feynman uses difference in outcomes for after-slit-and-before-screen-collapse and the experiment with after-slit-and-at-screen-collapse as being partially explainable using path integrals -- the different paths we can take are related to selection of worlds. Also, it makes sense that once we select a world, that it is internally consistent; this is related to how entanglement does not transmit information -- presumably it is occasionally hard for us to consistently select a world over another.

I have an idea for a n x n binary touch interface that is considerably more affordable than if one constructs it via a straightforward way (i.e. using a solenoid for each pixel). The straightforward way has cost with a non-trivial coefficient for O(n ^ 2). Our way has cost with lower coefficient for O(n ^ 2) and the main cost for it comes from coefficient for O(n). We have a rotating drum with O(n) electromagnets in a row spaced suitably far apart from each other so that they roughly do not interfere with each other. For each pixel, we have a piece of iron that is attracted when an electromagnet from the drum is placed near it and turned on. Alternatively, a pixel will get repelled via a spring dedicated to it; this of course means attraction s.t. it is meaningful must be strong enough to overcome the spring force. Presumably the cost of a spring is relatively low. As the drum spins, we keep updating a row of a screen. We allow a row to be updated by unlocking it using a multi-toothed rod that we momentarily move out of place. Once a row has been locked, an associated z-level pattern survives being pushed by a human hand. We have three buffers -- each buffer is associated with a screen. When a frame for a buffer is completed, we move the buffer into place by raising it. The buffers can be felt because they may lift up a ball for each pixel. We have smooth transition between buffers s.t. we cannot tell there is more than one buffer because we may raise a buffer and lower a buffer at the same rate and at the same time. Also, a third middle buffer is used to make sure unchanged raised pixels stay in place. An issue remains as to how rotating can push pixels up and down. We can make sure each pixel has a leg that is curved and have a sleeve for the leg s.t. general one-directional force gets redirected to have a different one-directional force that causes movement that eventually pushes a pixel up. (We haven't thought through exactly what would be an adequate approach, but we believe there ought to be one.) Many of the legs and sleeves we expect to be able to 3-D print (or at least we can 3-D print whatever actually ends up mediating the force so as to push pixels up if not by using sleeves). We also need to be able to move the buffers up and down at fixed speeds; whether we can do better for this than by using stepper motors and have the motion be more smooth is an open issue. We also have to consider specifically how to unlock a row. At any rate, we expect to be able to have quite a large frame rate. Also, if we have high resolution, we have to figure out a better way to space drum-head electromagnets out sufficiently.

We have to repair our most recent laptop. We need to open it up to get the right part number or possibly FRU for the lid. We need to purchase an upper lid, keyboard.

We have to purchase books for AP Literature. The books are Kennedy/Gioia 8th edition, Macbeth, Brave New World.

We have to contact the teacher for AP Literature -- Ms. Minor -- from senior year in high school (i.e. academic year 2006-2007). We also have to contact Robert regarding design analysis for Art Practice 98 DeCal from Spring 2008. We also need to finish schedules for certain semesters that require repair for undergraduate years. We need to -- once we are dealing with conversation phase for class repair -- finish the conversation portion of class repair document; this entails emailing people to say thank you to them and possibly asking parting questions, depending on the target person. This will require diagramming out conversations.

After finishing conversations for class repair, then we tackle article. After article, we tackle finishing certain classes -- e.g. CS 61A, CS 169, networking EE class.

We have found scrapbook add-on and add-ons for scrapbook add-on useful.

We have to finish imageboard back-ups via Internet Archive. Also, we need to investigate forum software.

We need to email a person from high school asking about Mythology book for AP Literature. We need to ask them if they are willing to share vBulletin 3.0.0 beta 5 software (so we can restore forum data without resetting style templates), which they may either have already or they can download via vBulletin member section; we lack member login information and we may not have paid. Presumably, the cost is $160 for forever license (for this one version and not for updates). We may wish to offer $80 for being able to log in member section for vBulletin website, if we have not paid in the past. (They may wish to be nice and give a copy of the software anyway.) It would be nice to be able to take a scrapbook snapshot or screenshot of the member's section. We would have to provide license number or customer ID or ask them to give their own email address. Finally, we can offer to give them unlocked versions of later versions (e.g. 3.8.4 and 5.4.3). For some of these other versions, we have done custom work towards unlocking them completely. We are interested in vanilla to-upload files and not-to-upload utility files. Our to-upload files for 3.0.0 beta 5 seem to have issues. Also, we have had issues with corrupted binaries (given they were transferred via ASCII mode) -- even binaries stored in MySQL database. Also, we should recover suitable environment for non-version-five vBulletin software using older machine and take scrapbook snapshots or screenshots of back-up screen for administrator control panel.

We need to donate books and music CD's.

We need to unlock a hard drive with a password (possibly via an external service); we need to make an effort to check if the hard drive model is supported or send it in and have the service check manually if the model is not explicitly listed on said service's list of hard drive models supported. Some expected payoff from unlocking the hard drive is seeing our Arch Linux distribution, whether we have college application or college admission essays backed-up or scrapbooked, whether we have bSpace documents downloaded that we no longer have access to. (There are also some risks.) An estimate (excluding a certain super-exotic option) is $100, with some give or take for shipping. Apparently the $100 fee does not apply if they cannot fix it, though in some sense shipping fees may still be incurred.

We have to ask what "AC" means to an AP English Literature teacher; it was mentioned by Mr. Hardin in a 2010-2011 academic year AP English Literature syllabus.

We need to ask Tang Center CPS therapist (possibly Dr. Chan) what "AVC" means.

We need to follow up with counselor at College of Engineering to see if they have records of non-medical withdrawals and re-admissions to see if e.g. we were granted a second withdrawal before we had finished certain forms or that certain fax dates can be corroborated. This may be delayed via coronavirus.

Some things we may not resolve in a short amount of time -- e.g. where our Timbuk2 messenger bag went. A bunch of clothes submitted via hospitalization from May 2008 we can assume we essentially have no way of retrieving.

We need to collect websites and blogs for AP Literature for Ms. Minor, Mr. Duncan, Mr. Hardin from Westview High School.

We would like to finish up search for an Angela from floor eight at Cunningham Hall for freshman year (i.e. 2007-2008); in particular, this involves at least contacting an Angela Jew (via Cal alumni search or Facebook) to ask them if they were there.

We may wish to back-up copies of Minecraft maps for Blockeley and Westview. The former is interesting because of possible re-construction of Unit 2 Cunningham hall floor eight.

We need to pay fees to middle-man pharmacy (e.g. Pelham or eventually even Genoa).

We need to update our LinkedIn and have a portfolio.

We need to get a job or at least do some volunteer work before doing so.

We need to clean our room.

We should mention to Ms. Minor that we have more questions regarding Mythology because it seems to be somewhat close to being a textbook (s.t. we have already asked a lot of questions about the two other actual textbooks assigned).

We need to keep attending blood draw clinic, therapist appointments, social worker appointments; we need to continue to pick up main medications and side-effect medications.

We would like to create pages for Math 1A and Physics 7A and more generally for Math 1A/1B/53/54/55 and Physics 7A/7B/7C. For Math 1A, for example, we would like to make notes about the custom edition textbooks used for part of the past. For Physics 7B, for example, we would like to make notes about worksheet/lab workbook used. For aforementioned Math series, we would like to explain why Borcherds says a certain edition is not useable -- this has to do with textbook section that temporarily was not required and was omitted; to remember the exact details, we refer to our scrapbook pages for math department webpages that deal with undergraduate math course outlines. Possibly the section is section 9.6? Borcherds himself has told us via email that he does not remember why a certain edition is not suitable; to know for sure (and we knew essentially for sure at one point!) we must compare multiple undergraduate math course outlines and how they changed over the years. Also, it's worth noting we also depend on the name of a section as detailed via a slide on a professor's webpage at some point to know what edition of a math textbook was used for that professor for some semester.

(Yes, some of this is repeated from the previous blog post; we will need to consolidate eventually.)

Some teachers or TA's we asked for help from we need to follow-up with or send our plans to (given that they asked for them).

We should note our T440s has a fan that needs oiling.

We have to remember to pay certain medical-insurance-related (Quest-lab-related?) fees.

We need to implement the algorithm we mention in our matrix multiplication algorithm article. We need to include diagrams and show that the approach is better for at least some parameter values. We may wish to eventually publish to either arXiv and/or beyond.

We need to update our resume.

We need to acknowledge that writing a blog also helps our lizard brain as we can make sure we show activity on our profile page.

When we get back to Oregon, we ought to make an effort to group documents for classes at or before junior year into binders (e.g. we may need to purchase binders and example classes are AP Biology and Anatomy and Physiology and AP Language). It may help to bring a copy of my high school transcript.

We may wish to message Zhenhuan L. or Ioana L. or Kristin M. about science ambassador program at ONPRC for purpose of getting photos (e.g. via PDF files distributed by the coordinator that I now lack) involving myself or my mentee or both. I may have to ask them and/or check documents in Oregon in a filing cabinet to remember their name or if I have a photo printed out.

I will need to make a diagram of the TouchGraph device mentioned above and we may wish to construct a prototype and publish an engineering article about it; an emphasis may be on price.

We may later wish to revise our blog posts.

We will need to remember to think about parents, sister, nephews/nieces, relatives, cats. For example, when their birthdays are.

Also, we may wish to give some thought occasionally to whether to interact with people from high school or college.

As we mentioned in the previous blog entry, we also may find it useful to create a document filled with "stickies".

We may wish to scrapbook our conversations (e.g. via Cal alumni network or Facebook).

Do we have old conversations for main Facebook account fairly-extensively backed up (i.e. possibly before they got deleted due to our choosing to deactivate that account)?

We may wish to ask relatives (i.e. parents or sister) as to whether they have accounts that we borrowed to make certain purchases so that we can scrapbook purchase details. An example reason this may have occurred is that we may have wished to use someone else's Prime subscription.

There may be countless other small details we have left out that are roughly related to the details we have included.

We may wish also to donate our copy of Battlefield 2.

For backing up imageboard pages, we will make use of e.g. copy-urls XUL add-on together with Scrapbook X add-on for Pale Moon.

## 2020-04-22

I'm still getting my ducks in a row before focusing on writing an article.

I am backing up documents for five more Math 1A course offerings -- Stankova Spring 2009, Ogus Spring 2010, Olsson Fall 2008, Sethian Fall 2010, Haiman Spring 2014. This is for our class repair document. Then, I can proceed with conversation portion of class repair document. We need to finish adding five Borcherds semesters for Math 1A as well. We know that we are no longer adding Math 1A course offerings after these ten courses, given that we have a stated strategy of selecting certain classes as seeds (though not all seeds are chosen to be a seed for the same reason -- e.g. they may be a seed because they have quizzes we like or because they have exams we like) and of expanding our offering list only if we can find a TA page that also mentions another Math 1A offering we have not seen yet. So, while we have a lot of work left, we at least can be reasonably confident that we have a finite known amount of work left for backing up courses. Of course, we need to wrap up by messaging students, TA's, and professors (after we devise a strategy that takes into account possibility of irritating people given what we have already said to people). We will need to print our post-repair documents.

We should also mention that we are making use of many extension for Firefox, including: Simple mass downloader, Copy All Tabs, Easy Youtube Video Downloader Express, Vimeo Experience. Also, we are using the online service at vimeo-download.com. We are also using Pale Moon, a fork of Firefox browser that stays with providing XUL capabiliites. Then, we are able to use an extension called ScrapBook X. This means we are going back to using a scrapbook-like extension after a hiatus beginning in around late 2007. It allows us to be arguably much more productive in our task of becoming less exposed to risk of disappearing webpages. (For example, we can bookmark messages sent through Cal alumni network given they have no built-in way to back up messages or we can back up course-related documents that may or may not be on Internet Archive currently.) Also, using it is convenient given that we can automatically record certain details (e.g. when we backed up and original address), we can use folder hierarchies, we can e.g. rename titles while keeping old titles alive in a sense as well.

Also, we need to make sure to back up TA lists for classes we back up (e.g. via NinjaCourses while it is still up). We need to back up old physics textbook announcements (i.e. before Fall 2000 and possibly at and after 1997 -- we note that early on the records may be a bit spotty). We may need to purchase a hard copy of fourth edition of Giancoli.

Coronavirus is making news.

We also plan on adding pages regarding personal projects and regarding assorted topics that cross my mind (e.g. how to explain the fact that electricity that ends up at your power outlet travels so quickly, for some definitions of "explain" and "travels").

We will need to combine and condense our to-do lists and e.g. contact people from high school about Science Ambassadors activity for photo-filled PDF files (because while we used to have them, we ended up losing them as part of mistakenly losing around two years of emails in general for our personal email collection). We will need to collect our "stickies" (i.e. things we wish to do but have no direct way of resolving in the short-term) and possibly re-print them. We will need to e.g. donate some items when we get back to Oregon. We need to remove watermarks from documents we have backed up that were at coursehero.com. We need to print schedules using rules mentioned in our class repair document. We need to scan some documents we currently only have in physical form.

We need to email some people from high school about which edition (ninth?) was used for "Introduction to Fiction" textbook for AP Literature. We would like to add a projects page talking (e.g. for sugar printer, moire-and-air-based touch graph interface). We are waiting for a check to be mailed back from Tang Center so that we can shred it after checking that it was not cashed in. We ought to remember that we have staggered phone appointments for Freedom Trail Clinic and yet-to-be-made appointments for blood draw at some Quest Diagnostics location. We ought to not forget to attend those appointments and to make follow-up appointments s.t. they remain in some sense staggered (until we start going back to in-person appointments). We are waiting for a response about possibly having two dates for second withdrawal from Ms. Samson, who is an advisor at College of Engineering. We are waiting for a response from Quest Diagnostics regarding a mistake for billing from 2018. We are waiting for a response from social worker regarding time of day for next appointment; alternatively, we can call front desk at FTC at some point. We need to make sure we are okay with having Amazon be missing details for certain purchases from a long time ago -- possibly by backing up as many orders as we can s.t. we lack emails for them but haven't yet lost details for via Amazon's website directly using a scrapbook extension. We need to call Dr. Chan from Tang Center about what the abbreviation "AVC" means. We have to remember to repeatedly order refills for secondary medications via CVS (and to take advantage of free shipping while it is still an option).

We want to finish conversations (as we have said), we wish to take a couple of classes.

We also (obviously) wish to get a job.

Our sense is that typing up blog posts will help us get through this work faster.

We would like to create pages for Math 1A and Physics 7B. For Math 1A, for example, we would like to make notes about the custom edition textbooks used for part of the past. For Physics 7B, for example, we would like to make notes about worksheet/lab workbook used.

We also would like to re-ask a specific person whose name is Angela J. via Cal alumni network whether they lived on eighth floor in Unit 2 for freshman year. We only know that the right person probably has a first name of Angela. Yes, this part is awkward.

Finally, we would like to transfer all our tabs from our secondary laptop and tabs and notes from our phone.

In the future, we would like to be more specific about which additional classes we would like to take.

## 2019-11-13

It turns out that range mode query (in the way that we think of using it) is not enough even for a stepping stone approach for BMM. Still, it helps to consider it. We have a different lead now that it it is best for us not to go into too much detail into here for now.

## 2019-10-21

We are now focusing on pursuing range mode query.

## 2019-10-20

About half a week ago, we decided to stop working on using partially-in exact range closest-pair query.

We are working on range mode query and higher-dimensional approximate range diameter query.

Relevant resources:

* Petersen - Improved bounds for range mode and range median queries (2008)
* Oh and Ahn - Approximate range queries for clustering (2018)
* Lovisolo and da Silva - Uniform distribution of points on a hyper-sphere with applications to vector bit-plane encoding (2001)

## 2019-10-14

We are working on considering Xue et al. 2018 partially-in exact range closest-pair query.

Relevant resources:

* Xue et al. - Approximate range closest-pair search (2018)

## 2019-10-13

We were working on de Berg and Haverkort 2003 significant-presence query 1-d structure. We made 1-d exact and approximate test box sets in time linear in n, where n is number of points, correctly.

We're following another lead now -- it is to do with Durocher et al. 2013.

Relevant resources:

* de Berg and Haverkort - Significant-presence range queries in categorical data (2003)
* Durocher et al. - Range majority in constant time and linear space (2013)

## 2019-10-08

We are working on creating test boxes.

## 2019-10-07

We are working on implementing 2-d range tree.

## 2019-09-08

We are halting our work on fast matrix multiplication.

## 2019-08-27

We've experienced some turmoil over the past two weeks; the machine we have been using became unusable and I got a second-hand machine as a replacement. Also, we have a new lead for signed f.p. matrix multiplication.

## 2019-08-06

We are working on HW #10 for CS 61A. Specifically, we are conducting experiments on parallel-execute for two ways that it is implemented in the version of UCB Scheme (i.e. version 1.3.6) that we have.

## 2019-08-04

Gomory-Hu-like cut-tree for strict Boolean MM did not work out for us.

We are planning on going back to re-visiting CS 61A material.

## 2019-08-01

We finished 2VCB oracle. Unfortunately, there is a flaw with our application of it to lax Boolean MM. We can wrap around and get results that bias towards true for 2-vertex-connectivity; we call this "pollution". If we start at an R node, if the result should be that we cannot reach an L node, we can visit a different L node and then visit a different R node that is then able to reach the target L node. This is why we are able to get correct answer if we randomly generate Boolean input matrices if n is small; the larger the value of n, the more opportunities we likely have to pollute using. At the very least, we now have 2ECB and 2VCB in our toolbox, should we need to use them later.

Now, we are moving on to an approach for strict Boolean MM via custom construction of a Gomory-Hu-like cut-tree for specific application directed graphs. There is a portion which we assumed we could reduce to efficient lax Boolean MM, but that assumption does not hold anymore and so that portion will need to be re-worked.

## 2019-07-29

In the course of working on oracles for 2ECB, VRB, 2VCB, we found bugs in GD1 and FastVRB. For the former, we have issues with not setting edge types correctly and we are too strict about adding edges for step zero of transform; if parent of source edge's destination doesn't exist, we just do not add associated new edge. For the latter, we forgot that we need to choose a specific node to be start vertex for second layer (i.e. reverse layer); if we do not, the blocks we get as output may be incorrect. Because we refrain from explicit O(n \* log(n))-time sorts, a lot the orders are not well-defined (particularly when we use sets and dictionaries); we used to arbitrarily choose the first vertex in input vertex collection for reverse layer calls to be start vertex. These two details explain why sometimes we would get a correct answer and sometimes get a wrong answer. We fixed our implementations for these two algorithms.

## 2019-07-25

We have Gabow-Tarjan DSU structure and block forest working.

## 2019-07-22 (again)

Last big detail addressed for Gabow-Tarjan; it was a bug in the pseudocode from the article.

## 2019-07-22

We have concluded that for us our specific lax Boolean MM approach we will not use to help implement strict Boolean MM approach; it is a dead end. We have an idea for strict Boolean MM, but we do not use that particular reduction. This is good in a sense, however, because then we have less obligation to make our lax Boolean MM approach be inordinately extensible.

We are almost done implementing Gabow-Tarjan DSU structure. After that, we will tune for Gabow-Tarjan b, implement 2VCB-related VRB block forest, implement creation of our application graph, perform experiments, write an article.

## 2019-07-20

Got back from a trip to Belgium for a week. At the place we stayed at, there were two masks of characters from Five Nights at Freddy's horror video game. We had waffles, twice-fried fries, and seafood among other things (which the place is supposed to be known for). Watched two movies on the international legs for trip forward and for trip back -- Fantastic Beasts: TCOG and Lego Movie 2. Went to music instrument and train museums, architect-related historical sites. Apparently, sometimes trains receive power from wires from above and the connection is sustained by tension.

We thought we had a bug with retrieving results from answer table due to mark signal issue. The problem really was that we are using number (i.e. intra-microset number) instead of the correct value that is name. Once we cleared this up, the pre-processing appears to be successful. Now, we just need to implement find in terms of microfind and initialize macrosets as singletons using microset roots (i.e. by using union tree structure).

## 2019-07-08

We are constructing micro, number, node, parent, marked mappings correctly. Parent and marked signals are word-packed. We are working on answer table, which involves re-constructing a forest (or a tree with dummy root) with all possible marked 0/1 patterns. We know parent tables are valid without performing two suggested checks (i.e. one for boundedness and one for acyclicity) by only considering parent patterns for actual microsets we see from cutting up the input union tree. Then, we spend time in O(b) for a linear-time check for pre-order traversal of a microset tree to correctly retrieve answer for 3-d answer table because we consider all possible starting nodes at same time and size of a microset is in O(b); parent and marked signals are assumed to be fixed for each of these linear-time traversals. Our biggest issue is figuring out how to via pre-computation answer zero for answer (which microfind uses) if parent signal is invalid or all ancestors seen are non-marked OR non-zero and the internal-to-microset number of a node if it is the closest ancestor that is marked (assuming all nodes are inside the microset and we ignore "root" of a microset); we wish to know how to do this via a linear-time traversal for pre-computation.

In short: each node wishes to know lowest non-proper ancestor that is marked; if it has no non-proper ancestors in the microset that are marked or parent signal is invalid (which will not happen with our current approach and application), we also would like to know. The output has no need for word-packing. A dummy node should not be considered a prospective ancestor. The result for each parent-signal/mark-signal/start-node permutation we use to add a value for a 3-d hash table (i.e. we have three keys that are associated with nestedness). We note that after we create them, we mostly do not unpack parent signal and mark signal; after we create them, we mostly use them in packed form; we do sometimes unpack mark signal -- we do so as we compute answer table.

## 2019-07-07

We are working on Gabow-Tarjan DSU. We are correctly determining node groups and roots for each microset we plan to make. Now we need to fill out tables.

## 2019-07-02

Got back yesterday from a three-day vacation where we visited a theme park and a water park. Finished Heart of Darkness today.

## 2019-06-27 (again)

We have correct and fast implementation of FastVRB.

## 2019-06-27

We have a bug with FastVRB -- shortcut case a we have not implemented correctly; we are basing this assessment on example from figure five in Georgiadis et al. 2015. Also, we ought to remove self-edges.

## 2019-06-26

All we have left for FastVRB is to transfer our implementation for constructing auxiliary graphs from forward direction to reverse direction. Of course, we technically still have to implement Gabow-Tarjan DSU structure to make the whole 2VCB algorithm faster. We need to construct block forest. Also, we thought that we would need to fix step 3.5.3 to be fast enough, but it turns out that our implementation for it (and for its analogues for 2ECB in form of step 3.2) already take time linear in N and K, where N is sum of sizes of active blocks and K is number of vertices for current subproblem.

## 2019-06-21

As part of attempting to implement fast FastVRB, we found a bug with Fast2ECB and Rec2ECB that do not affect correctness of results but that affect speed. The bug affects speed of bucket-sort-related step for shortcut case b for 2ECB-related algorithms and shortcut case a for VRB-related algorithms. The key is that we need to merge across lists for different output auxiliary graphs, bucket sort using pre-order numbers, and then unmerge to figure out separate lists for each different output auxiliary graph. Sorting within bucket is unnecessary. This means figuring out shortcut case b edges takes time linear in size in terms of nodes of current auxiliary graph instead of our repeatedly requiring for output auxiliary graphs time linear in size of source dominator tree. This is exciting because the perceived time required from running our implementations will be even better. We also have made progress because we have in a sense finished base edges and shortcut case a edge (except for bucket sort issue) for FastVRB implementation.

## 2019-06-17

We tested our attempt at FastVRB and got correct answer for two inputs from Georgiadis et al. 2015 (i.e. figures two and three). Now, we work on getting it to be efficient. (It's also important to note that we have yet to implement block forest given vertex-resilient blocks.)

## 2019-06-15 (again)

We note that step 3.3 for FastVRB pseudocode is s.t. we execute split and implicit is the idea that we replace a block with the result of the split. This is partly supported by the fact that for step 3.5.3 we use refine by "executing" it, as well. Also, common sense tells us that given that we have no other state modified by the split operation, for the replacing to not occur would mean that step 3.3 effectively does nothing.

## 2019-06-15

We're still working on FastVRB -- we are working on getting it to be correct. Later, we will work on making it efficient. Currently, we are creating FastVRB auxiliary graphs correctly, though not necessarily efficiently. Now, we are working on performing splits, though the notation in the pseudocode is a little ambiguous as to what C(r) means in step 3.2. We assume it refers to forward dominator tree and that if we are referring to C group for reverse dominator tree that we will see T as a subscript as in definition of split(B, T). Also, we are planning on replacing blocks quickly by using sets that contain block objects that wrap lists (given that lists are not hashable in Python) and by using set addition and set subtraction.

## 2019-06-01

We fix refine operations by requiring at least one family out of two to have groups that are pair-wise disjoint. We name groups. Time becomes linear instead of quadratic in number of nodes. For modified refine (for vertex-resilient blocks), if current B block has node x, then replacements for block B all have node x. For regular refine, both blocks and SCC-related partition are families that are internally broken into groups that are pair-wise disjoint. For modified refine, only SCC-related partition are s.t. it consists of groups that are pair-wise disjoint. We take advantage of fact that if we break into separate parts that an element from one part and an element from another never can be merged into same group again (except in sense that we may clone and two nodes with same name are in different groups).

## 2019-05-31

We made a mistake with Simple2ECB and subsequently Fast2ECB s.t. they are slower than they should be. We note first of all that refine(B\_set, S\_set, x) from 2-vertex-connectivity article is step 3.2 from Simple2ECB with x being undefined. We implement step 3.2 s.t. it takes time in O(m \* n), when it should take time in O(m). This is doable via implementing it using bucket sort, which Georgiadis et al. go into relatively more detail in their 2-vertex-connectivity article in a sense.

## 2019-05-30

It turns out that algorithms for 2-vertex-connectivity from Georgiadis et al. 2015 tend to re-use algorithms for 2-edge-connectivity from Georgiadis et al. 2014 together with concept of vertex-resilience. So, we're not throwing away as many details as we previously believed we would need to; on the contrary, we're getting quite a bit of bang for our spent-time buck and 2-edge-connectivity together with strong bridge and interval/bridge algorithms are not just warm-up and corrections to the articles that present their pseudocode are fair game for content for our article.

## 2019-05-25 (again)

We recently implemented Fast2ECB from Georgiadis et al. 2014; its time is O((m + n) \* alpha). An important detail is that more than one strong bridge may appear to remain for third layer, but that at most one of them we care about (though, this is possibly linked to idea that some strong bridges are separating nodes that are not both overall ordinary. Now, we will work on SimpleVRB from Georgiadis et al. 2015.

## 2019-05-25

We recently implemented Rec2ECB from Georgiadis et al. 2014; its time is O(m \* n \* alpha). Now, we will work on Fast2ECB.

## 2019-05-23

We recently fixed Simple2ECB from Georgiadis et al. 2014. We are working on Rec2ECB with emphasis on correctness; time also is still not yet O(m \* n \* alpha). We need to determine five cases (two bridge-related and three shortcut-related) in lower time. The first two cases are for auxiliary nodes and auxiliary edges. The last three cases are for auxiliary edges only. After we complete Rec2ECB, we will be relatively close to finishing Fast2ECB efficiently, as well. A key is that we need to distinguish between overall ordinary nodes/edges and locally ordinary nodes/edges.

## 2019-04-27

Turns out there's a bug with our approach of using 2-edge-connectivity to answer lax Boolean MM -- it is possible to contaminate whether we have enough paths by looping around back to right side using behind node.

Briefly, we considered whether 1-edge-connectivity (i.e. strongly connected components) is enough. Those ideas did not pan out.

Thankfully, we have a new idea and it uses 2-vertex-connectivity. Somewhat reassuringly, 2-vertex-connectivity queries can be done in O(1) time as well, pre-processing takes time linear in number of nodes and edges, the algorithms are slightly more difficult to implement w.r.t. 2-edge-connectivity, we can maximally take advantage of sparsity. Also, there is a simple version as well that we can use for proof of concept and testing cases that we fail for 2-edge-connectivity-based approach. Also, we don't have to throw all our previous algorithm implementations away and pieces we don't need anymore can be laid to rest by testing them for correctness by comparing to results for simple versions of those algorithms (i.e. simple versions for them generally do seem to exist, which is also good).

## 2019-04-25

It's a little bit crazy to think that I've been working on some version of fast MM since end of 2017.

Anyhow, we are working on summarizing the Georgiadis et al. 2014 article and especially the part of it that centers on how to construct auxiliary graphs.

## 2019-04-17

We have finished implementing the seven Fraczak et al. 2013 dominator tree algorithms s.t. they are as efficient as promised from original article with exception that we do not use Gabow-Tarjan 1985 off-line DSU algorithm. As such, a few of them have time nearly linear in \|E\|; i.e. the time is in O(\|E\| \* alpha(\|V\|, \|E\|). We choose to focus on algorithm GD #2. Now, we plan to work on Rec2ECB and Fast2ECB from Georgiadis et al. 2014. Later, we will make use of Gabow-Tarjan DSU to speed up GD #2 to take time linear in \|E\| under certain model of computation.

## 2019-04-13

We have figured out almost all of the seven Fraczak et al. 2013 dominator tree algorithms. Now, we are planning on polishing our implementations. This means we can move on to Georgiadis et al. 2014 Rec2ECB and Fast2ECB soon or Gabow/Tarjan 1985 off-line DSU. DFS tree is the union tree we use for off-line DSU. We also have to figure out auxiliary graph for Georgaidis et al. 2014.

## 2019-03-30 (again)

Splendid success! We implemented reduction of lax Boolean MM to Simple2ECB and SCC algorithms. We appear to be getting the same answer as brute-force. This approach is slower than brute-force in terms of asymptotic complexity. It is a proof of concept. Now, we work on Georgiadis et al. 2014 Rec2ECB and Fast2ECB, Gabow/Tarjan 1985 off-line DSU, Fraczak et al. 2013 vertex dominator tree.

## 2019-03-30

We've implemented Tarjan 1976 INTERVALS and BRIDGES, Italiano et al. strong bridges. Our implementation of INTERVALS and BRIDGES is ready for swapping out of standard DSU structure for Gabow/Tarjan 1985 off-line DSU structure that uses links instead of standard unions; however, we have not implemented that Gabow/Tarjan structure yet, though we believe we understand how to. We are working on Georgiadis et al. 2014 Simple2ECB. The algorithm ought to be O(n ^ 3 * alpha(n, n ^ 2))-time.

## 2019-03-17

We've figured out Gabow/Tarjan 1985 macroset/microset-based off-line DSU, Tarjan 1976 flow-graph INTERVALS and BRIDGES; we have gone through the articles for them and we believe we have filled in gaps in the descriptions. Now, we will attempt to implement Simple2ECB and judge correctness based on if we get the right answers for our application (i.e. we run a gauntlet). First, we do what it takes to get correct answers and then we will swap out parts for faster versions. Ultimately, the algorithm ought to be O(n ^ 3 * alpha(n, n ^ 2))-time.

To get whether two nodes are 2-edge-connected, we take advantage of 2-edge-connected blocks partitioning the vertex set and check if the two nodes are in same 2-edge-connected block in constant time.

## 2019-02-19

<img title="Incredible!" src="incredible - cropped and resized.png">

We're working on implementing Simple2ECB from Georgiadis et al. 2016. As we partially mentioned, this in a sense requires Gabow/Tarjan 1985 off-line DSU, Kosaraju 1978 SCC, Bender/Farach-Colton 2000 LCA, Tarjan 1976 flow-graph bridges, Italiano et al. 2012 strong bridges. Also, Fraczak et al. 2013 dominator tree is required for Rec2ECB.

Thankfully, the Fraczak article seems quite detailed and it happens to also use Gabow/Tarjan 1985 off-line DSU, which allows time linear in number of items and find/union queries. If we were more clever, we might be able to reduce vertex-dominator to edge-dominator case, though it's not clear how to then construct a terse vertex dominator tree from a collection of vertex dominators. So, we don't do that reduction and instead defer to Fraczak.

## 2019-02-08

To get to edge dominator set, we need intervals (via Tarjan's "INTERVALS") and flow-graph bridge set (via Tarjan's "BRIDGES"); before that, we need to use DFS to explicitly create a tree, using which we can get subtree size, pre-order numbering, edge classification, pretty printing. Then, using edge dominator set, we can get strong bridges.

## 2019-02-06

We have at our disposal certain algorithms whose implementations we have generally borrowed from other people in the interest of expediency. These are disjoint set union-find data structure with union-by-size and path compression, LCA from Bender and Farach-Colton 2000, SCC algorithm from Kosaraju 1978.

Now, we need flow-graph-bridge set finding, which serves to give us edge dominator set for a directed graph. Then, we use edge dominators to get strong bridges for a directed graph. Then, we use strong bridges to get 2-edge-connected blocks. We use 2-edge-connected blocks to answer 2-edge-connected queries for pairs of vertices. The first 2ECB algorithm we implement will be Simple2ECB from Georgiadis et al. 2014.

## 2019-02-02

Not writing about our progress and keeping secrets is eating us up inside and leading us to be less productive.

We have a way for lax Boolean MM that takes time in O(n ^ 2). We have a partial approach for strict Boolean MM -- we have pushed it to backburner in order that we may be able to buy time by solving a weaker problem -- i.e. lax Boolean MM. The partial strict approach happens to -- as an aside -- make use of our lax flavor problem. The article for lax flavor we have written up partially and we are working on implementing it, currently.

Pretty incredible that the time can be strictly quadratic, no? That's a highlight -- hopefully we will implement successfully and publish to pre-print before we get front-run, though.

We went to a magic show on Feb. 1st. It's pretty fun to see what one can do with sleight of hand.

We have a bunch of loose strings to tie up regarding Oregon. I have some things on Amazon that are not selling and that we should probably donate to some brick and mortar store. I have some material from high school classes (e.g. AP Biology) in a filing cabinet to pull out and group into folders.

## 2019-01-09

Hope is still alive for a reasonably fast approach for strict Boolean MM.

Meanwhile, here are some bits of art.

<img title="Whirlpool 1a" src="whirlpool1a - cropped, resized, cropped.png"> <img title="Whirlpool 1b" src="whirlpool1b - cropped, resized, cropped.png">

## 2018-12-17

We have figured out a way to solve strict Boolean MM in O(n ^ 2 * polylog(n)) time, but it will take a while to implement and test. For our sanity's sake, though, we leave this message in case it does indeed take a long time to follow through on.

## 2018-12-09

It turns out our alternate approach for (min, plus) semiring MM approach is not valid because there is a coefficient of d (i.e. our dimension) that we leave out. This d for matrix multiplication is n and so is not small and fixed (e.g. it is not two); so, the approach we are thinking of takes time that is actually n-factor larger and thus takes time at least cubic in n.

## 2018-12-07

We are waffling -- we have another idea for lax Boolean semiring and (min, plus) semiring MM approaches. In 2016, we described a possible way to solve APSP that involves first solving (min, plus) MM via Chan 2008 red-blue dominance queries. We can reduce APSP to lax Boolean MM, which reduces to (min, plus) MM. The idea is that (min, plus) MM takes time in O(n ^ 2 \* log(n) ^ 2), though there is a chance that the reductions may introduce extra polylogarithmic factors. It would be great if this works as then we have something to show for our time. We note that these ideas do not necessarily imply good times for strict Boolean semiring and standard (plus, times) ring flavors of MM.

## 2018-12-06

We have dropped lax Boolean, strict Boolean, f.p. (plus, times), (min, {plus, max}) (i.e. tropical) MM approaches. We posted a postmortem in our FMM repository. We believe that if we are to come back to this problem later, that we will need a good understanding of tensors.

Perhaps it is telling that we regret not being able to make a worthwhile article (currently) given that the typesetting we arrived at is so pleasant.

## 2018-11-11

We will be heading back to China for from November 12th to November 23rd.

We have another detail to address that is important -- we must acknowledge that we don't always have a one bit at the right staircase. Somewhat fortuitously, as long as we occasionally omit rectangles at right, the modifier memoized values are made in the same way and are used in the same way. This is the case not because the modifier e.g. gives across-the-board zero values in some sense. Our remedy involves two details -- (1) We omit rectangles that are weighted at right if we have a zero bit for some B column; and (2) it's okay if we have a zero bit at right if we have a handful of one bits at left as the modifier continues to work correctly in this case (i.e. without requiring a change in how we determine it and use it).

## 2018-11-10 (for fourth time)

We will address what are and how to use the modifier memoized array values.

First, we consider relative behavior. If we have full A row prefix w.r.t. a B column, our modifier pair should give zero. Note that by full A row prefix w.r.t. a B column, we mean lowest A row up to same level as B column. To get this zero, we have x\_1 - x\_2 == 0. The x\_2 is shortening of modifier based on B column level and x\_1 is based on how non-full A row prefix is; both these values are based on modifier memoized values. If A prefix is full w.r.t. B column, x\_1 equals x\_2. How do we choose an x\_2? It is the value for the level associated with that for chosen B column.

Secondly, we consider absolute behavior. We wish to avoid off-by-one error. The correct behavior is we have value describe for a level contributions strictly above that level. In other words, we do not have "at or above" behavior; we have "above" behavior. Okay, then -- what are we counting? We are counting number of zeroes in left staircase -- and we care about this amount s.t. they are strictly above our level.

## 2018-11-10 (for third time)

Well, how do we get prefix that we use by subtracting to get suffix when it comes to B column rectangle reactionary weights for modifier pre-processing? We note that individual values in modifier memoization array may be larger than one and they are nondescending as we go from high z to low z. We don't blame ourselves for neglecting to go into this issue in detail yet; the other details are just as important; how do we memoize? To get prefix, we consider number of zero bits either (1) above us only or (2) above us or at same level; choosing between those two ways of memoizing just affects how we use the memoized values. Then, we subtract so we don't have unnecessary B column rectangle reactionaries that protrude; this may sound vague, but we make sense of this description by resorting to considering fixed-z subproblems for correctness. The modifier memoized array has n entries and they are for different z value targets.

We flit between being confident and uncertain about the approach we have described, but currently we feel optimistic, because we have some agreement in that when we eyeball what our modifiers give for certain small examples we do get numbers to subtract that seem appropriate or numbers that are memoized that can be used correctly later.

Our next task is to work out some examples by hand.

P.S. -- One might have thought we would have gone through examples by hand earlier -- and we have in a sense -- at the same time, it has been important to not be too invested in a single approach because it can be difficult to know we are in a dead-end or whether it is worth the (significant) effort to e.g. devise the necessary notation to keep the work simultaneously terse and understandable.

## 2018-11-10 (again)

Three things are helping us stay confident in the correctness of the approach:

1. We don't need a literal rectangle train for suffix.
2. We want suffix because we are dealing with A row prefix -- suffix is poorly named and is for B column rectangle reactionaries what prefix is for A row collections. In a sense, the former suffix and the latter prefix are the same thing -- they are truncated version of a sequence where only one end differs and no gaps are allowed in the result sequence w.r.t. original sequence.
3. A way to prove correctness (e.g. because it may seem confusing to want a suffix for dealing with modifier) is to consider isolating fixed-z subproblems and considering them separately.

## 2018-11-10

This is about Boolean MM.

So, we're building on Kaplan's approach. They say that four-sided query in plane takes too much time. We agree, except that we argue that we can cope by using three-sided query pairs in plane; i.e. we use telescoping to get the same effect.

They use color carpentry, which means specifically that we start of by making use of a particular pair of descending staircases where left has points that are associated with A rows and right has points that are associated with B columns. Eventually, we will need a pair of that arrangement to correctly determine all of the matrix for the product result. A target B column can only be considered in combination with a target A row if that A row point is at same level vertically or lower. For second pair of staircases, we reverse the order of A rows, which lets us consider all combinations of A row and B column. Color refers to each offset for a dot product of an A row and B column. With color carpentry, many colors can be considered to be superimposed on each other. Eventually, we will see that it is okay for us to consider each color in isolation initially. The term color carpentry refers to the idea that we can flatten rectangles for the same color so that we don't double-count ones when we have a pair of ones interacting. We care about this "saturating" behavior because of Kaplan's argument that we can use it to determine a union (i.e. bit-wise OR) and then turn that into an intersection (i.e. bit-wise AND), the latter of which is in a sense what Boolean MM product asks for. It is not entirely, because we add the detail of the idea that we need to add the results of bit-wise AND for each color.

While we start with points associated with A row or B column and a color, we will want to turn them into rectangles. We will get rectangles as a result of color carpentry, which we then store and access via using a segment tree. Segment trees are good for counting queries (as opposed to reporting, which requires at least unit time for each satisfying rectangle for point enclosure), which is in a sense what we would like. However, we will need to cope with three-sided queries. We have an idea that instead of four-sided query that selects via a rectangular query region that includes an A row and a B column and that we assume is well-formed, we can instead of isolating a specific A row, we consider point enclosure query that selects for a B column and a contiguous sequence (i.e. "prefix") of A rows. Then, we consider another such query except that deals with a prefix that is one smaller in terms of number of A rows. The idea then is that we subtract the result and if our rectangles are valid and that they have adequate weights then we are using telescoping to get a correct answer for an output cell. We specify prefixes by using a third dimension (i.e. an extra one on top of the plane) that we say is for z-level. For left staircase, A row rectangles have z value that starts at zero at right and repeatedly grows by one as we move left. For right staircase, all B column rectangles have z equal to zero. Given that we use a 3-d segment tree, we know that subtrees we visit will have for the current component sorted items; we can accumulate from one side moving to other to get correct memoized values for nodes in the tree which we use for determining the answer to one of a pair of queries we need for an output cell. This is not enough, however.

If we attempt implementing what we have described so far, we will only get the correct answer when our two prefixes are size one and size zero. This is because if done improperly, we are double-counting or under-counting as we start to combine subproblems for individual z values. Or, if we wish to introduce more rectangles with various z values to combat the inaccurate counting which is due to not adequately addressing the issue of saturation, we may be able to get the correct answer but do so in too much time (i.e. cubic in n). There is another way, however. We first ought to say that so far, we assume that for each A row at left (except right-most one) we have a z value that no other rectangle shares. We can see that if we unpack and look at the required rectangles when we consider individual z values and a fixed color, we will see that there are repeated shapes on the right staircase (for each time we have a zero for an A row at left); each z value is associated with a single left A row for a fixed color. Then, if we give ourselves permission to have weights for rectangles that are not solely either one or zero, but possibly larger than one, we can share work by not duplicating those rectangles at right that appear when we have a zero at left, as long as we give larger weights which assume that we are dealing with maximal-size A row prefixes s.t. those prefixes are valid for the current B column choice. It may not seem like we are making progress yet, but we note that so far we are avoiding time cubic in n, again; particularly, we would like to point out that the combining of rectangles for fixed color and when we have a zero at left for an A row is affordable enough. We are not getting a correct answer, yet.

We have dealt with telescoping via z that reins in A rows at left. It turns out that we will benefit by considering telescoping for A row interactions with fixed B column; we rein them in by introducing a non-geometric detail s.t. for each query we will need a modifier value that we subtract in O(1) time as long as we perform pre-processing, which we argue is doable. With the shared rectangles at right, we are getting results s.t. we have singled out a particular B column, but too many reactionary contributions resulting from A rows at left that interact with the B column. We undo the contributions from unnecessary right rectangles.

B columns at right are affected by A rows at left at or below our level defined by B column chosen. Not all A rows we want to interact with a B column; this affects killing A rows and also affects killing B rectangles that are reactionary to A row. B column is chosen via query point. A row is chosen via z. Compatible A row can be at or below our B column level. We are counting too many reactionary rectangles. We have three key values: B column "z", z-level for chosen A row, highest z. As part of memoization, we keep an array for a fixed color. Later, we merge across colors. This array for a fixed color describes w.r.t. highest z (i.e. upper-most) how much to remove to get to B column. In general, the weights can be s.t. their sum is much larger than n -- this is a roundabout way of saying individual weights can also be much larger than one. This is not enough, however. We need to remove not starting at highest z, but starting at z value for chosen A row. We take advantage of telescoping or non-scrambledness -- whatever one wishes to call it -- again and remove the effect of values from z values in between highest z and chosen A row z by subtracting a "prefix" (again). Then, we merge across colors to get good time for query -- i.e. not proportional to number of colors, but in O(1). The pre-processing for this merging takes time overall in O(n ^ 2). The arithmetic is tricky, we admit. But, it can be done affordably.

We have a main query for each output cell. For each main query, we have two primary queries. For each primary query, we have a rough query and a pair of modifier queries. Rough query is for a prefix of A rows. Modifier query pair is to get the correct value to subtract from result of a rough query because we over-counted B rectangles that are reactionary towards chosen A row. Then, we take difference of results for pair of primary queries. Then, for main query, we use union-intersection arithmetic.

Then, we have a correct answer. We appeal to considering each z value in isolation. We have two-layered telescoping -- that for A row prefix and that for B columns that are reactionary towards our chosen A row.

We have neglected to consider optimization -- time is O(n ^ 2 \* log(n) ^ 3) if we do not use fractional cascading and interval tree for lowest level; otherwise, we could remove a factor of log(n). Of course, also, we can consider floating-point MM that uses ideas from the Boolean MM approach we have just described.

## 2018-10-31

Came back from China yesterday.

The Boolean MM things are not working out. We have one last hunch to see through and after that we will come up with a post-mortem article to show what we tried as a sort of way of making sure we do not have totally nothing to show for our time.

We finished My Antonia on October 30th, 2018. We'll be working on reading Oedipus.

After this, we will be focusing on class work.

We might like to update our class history with semesters spent at community colleges for completion.

## 2018-10-13

Nope, ignoring colors gives a similar approach -- expiries bias towards adding detail, ignoring colors bias towards removing detail; both may require knowing a lot about a certain B column's one-bit pattern s.t. we require O(n ^ 3) time, again.

Needless to say, if this were all there was to the story, we would come to the conclusion that our attempt at Boolean MM is incomplete.

We currently are pursuing an approach that is based on flattening for each color across A rows and then getting closer to the intention of having telescoping -- i.e. we have progressively more contributions (i.e. along z direction) in an efficient manner via base post-flatten shape and pair of modulating post-flatten shapes, the former of which consists of many rectangles, each of which have weight we update in O(1) time instead of in O(p) time, where p is number of rectangles that makes that base shape up via indirection (i.e. we associate each with a symbol, which we later look up weight for via a hash table). The reason we have a pair of modulating rectangles is that one is to repair a prefix and the other is for neutralizing effect of that repair for a later z. The idea is that this leads to an O(n)-factor time improvement.

We even believe there is a chance that there is a quadratic-time algorithm for Boolean MM, currently, but we ought to have learned our lesson by now that quadrarithmic-time is good enough for now. We ought to implement and know that this first approach actually works.

## 2018-10-12

I must admit that the core idea for out previous claim that we figured Boolean MM out -- collapsing colors -- was not enough. Easy come, easy go, I suppose. The reason we did not realize this was that we actually must have multiple expiry rectangles when a B column for some color has a one bit. If we only needed one, then we can customize expiries for the B column cross-color one bit pattern, which would take O(n ^ 2) time overall. If we have O(n) expiry rectangles instead of one for each B-column-color combination, then instead we have O(n ^ 3) time overall -- the idea is that each B column could have a relatively unique cross-color one-bit pattern, which aids in making this more-correct pre-processing too expensive. We remember that the point of expiry is to avoid double-counting one bits and so we would from a certain perspective need them every time we alternate from zero to one or vice versa -- not just once for each B-column-color combination.

However, we have actually figured the problem out in that we can take more advantage of problem structure. We have no need for expiry rectangles at all -- given that they only are relevant when B column has a one bit for some color, we can make an additional observation (after a certain amount of floundering and consternation) that we can avoid cut-out and expiry altogether when we have a one bit for a B-column-color combination because the contribution for a prefix difference for that combination is highly predictable -- it is always one.

Then, the structure construction is even cheaper than before (though not necessarily asymptotically -- i.e. in big-oh notation). We then ought to an early moment pre-process to count the number of one bits for each B column so that we can use that value and add to the result from a query (i.e. via a prefix difference).

Voila!

We are attempting to write this approach up in an article and attempting to implement this. Somehow, it feels that we should (as mentioned in last blog entry) be a bit secretive. Wish us luck!

Of course, we should mention that in the future, we may wish to swap out the tree structure; how practical or difficult this would be is currently up in the air to us.

## 2018-10-10

We figured Boolean MM case out! I feel almost that I ought to keep it a secret until I can finish the article, but alas. We ended up dropping so many aspects. Also, I am feeling a bit paranoid right now.

This comes at the heels of a disappointment as to the actual distance for a max-weight MST for n points in n dimensions; it turns out it (in l1-norm) is in O(n), not O(1) adjusted with protrusion-related factors. This appears to be the case when we have a hypercube in n dimensions with either hypercube primitive or hypersphere primitive in n - 1 dimensions. An offset that we mindlessly introduced to bound a particular expression turned out to be too costly.

The important idea is criss-crossing as an extra early pre-processing phase to merge color contributions for expiry rectangles that appear later.

The result is Boolean MM in O(n ^ 2 \* log(n) ^ 2) time. The polylog factor can presumably be improved with a different tree in the future.

Now, we can focus on finishing the implementation (yes -- we have not finished it completely yet) and the article. We can also mention ideas that we ended up dropping. (In the end, of course, fewer required details is better.)

We also have floating-point version to consider, next.

We can talk about (i) approximate NNS, use of JL lemma, turning it into a Las Vegas approach; (ii) appropriateness conditions; (iii) an Indyk paper analysis.

The best part is that this addition does not require very much change to a partly-finished implementation that we already have; we need to have more expiry rectangles with different weights based on pre-processing criss-cross phase.

## 2018-10-07

### Tooth fixed
I got a tooth fixed on October 1st (i.e. this past month). Last time we visited China (in around April of this past year), I got a root canal. This time, instead of a crown, I got a silicone-based filling/reconstruction. The root canal was ~900Y and the filling was ~360Y. That makes ~$150 for the former and ~$60 for the latter. Altogether, that's $210. This tooth -- a left molar -- was cut up considerably as part of an attempt to fix a metal filling that had fallen out. What's good is that with the reconstruction, the tooth is essentially whole again and the material looks like tooth material. It's a good deal!

### Funds
Reminiscing -- for freshman year, the meal plan we went for was likely non-upgraded and included as part of rent for the dorm. Based on 2018-2019 rates, a triple at unit two was likely around $14,600 for an academic year (i.e. ten months). This means each month was about $1,460.

### Legitimacy of a prediction for n\_p points on a n\_d-dimensional hypersphere s.t. n\_p > n\_d + 1

We are considering upper bound on distance associated with an edge for a max-weight MST for n\_p points on the surface of a hypersphere in n\_d dimensions s.t. n\_p > n\_d + 1. Typically, the maximum number of mutually equidistant points in n\_d dimensions is n\_d + 1.

Why do we care about Hamiltonian paths associated with polytopes? The candidate edges are purely those relating vertices to "neighbor" vertices, which we associate with predictably-low lengths via "densifying" a net by considering n-dimensional hypercube surface area and (n - 1)-dimensional primitive hypercube volumes.

We made a mistake for FMM s.t. we thought that d-simplex is a Platonic solid, but Platonic solids are three-dimensional; we care because Platonic solids are associated with Hamiltonian paths.

Instead, we can show that a d-simplex is associated with a Hamiltonian path as it is a simple d-polytope and via Barnette, for d >= 4, simple d-polytopes are associated with Hamiltonian path. For d == 3, d-simplex is associated with a Hamiltonian path via Platonic solid via Gardner. Trivially, for d in {1, 2}, d-simplex is also associated with a Hamiltonian path.

### Prediction for n\_p points on a n\_d-dimensional hypersphere s.t. n\_p << n\_d = m \* n\_p

We get a prediction that if n\_d = m * n\_p that distance is not bounded by twenty, but by log\_2(m) \* 20.

We can confirm this by performing a ratio test (i.e. use a limit).

### Postscript

The above concerns are associated with predictions that are wrong -- distances for l1-norm for first case and second case are not twenty and log\_2(m) \* 20, but 20 \* n and log\_2(m) \* 20 \* n.

## 2018-09-21

We are going to drop Chan's ANN approach for our Boolean MM. It is hard for us to adequately tile d-dimensional space (where d is large) using spherical cones with a point arbitrarily chosen as center s.t. the cones emanate from it. Also, presumably some overlap is allowable. Supposedly, we can get (1 + epsilon)-approximate nearest neighbor via Chan, which then uses Arya and Mount's BBD-tree for each cone and then possibly an additional optimization. We wish to be able to tune s.t. we have a "branching factor" of between one and two for each dimension. But, while it is in principle plausible that we can tune to get a target number of cones, the details are unclear to us s.t. we do not end up with far too few or far too many. The difficulty of this task is related to why we ended up using hypercubes for primitives that we tile instead of using hyperspheres for primitives for Boolean MM; if packing constant is not one, then of course our tiling can be quite elaborate and we would have to justify why some packing constant is achievable.

We found out that Indyk described a deterministic version of LSH (DLSH). We also had Las-Vegas-style LSH (LVLSH) planned for word-packed version of ANN -- i.e. for f.p. case of MM. The reason for this is that it supports word-packing, ostensibly. Why then would we want to pursue either DLSH or LVLSH for both Boolean or f.p. flavors of MM? DLSH is described somewhat vaguely, is older (from 2000), is for (3 + epsilon)-approximate NN, has deterministic time. LVLSH is more detailed, is newer (from 2016), is for (1 + epsilon)-approximate NN, has expected time.

TO put having 2-factor vs. 4-factor in perspective, log_2(1024) = 10; 10 * 2 = 20 and 10 * 4 = 40 are both much lower than 1024. On the other hand, a peace of mind from having deterministic time instead of expected time has value, as well.

We still must see if both DLSH and LVLSH work with word-packing. We will have to look into hash function families for Hamming distances (i.e. l1-norm) and possibly the same but s.t. we have no false negatives. It seems that bit sampling (for Hamming distance hash) can be done not on a bit-by-bit basis necessarily, but with a whole word at a time, by sampling uniformly from integers in \[0, 2 ^ m' - 1\], where words are m' bits large.

## 2018-09-15

Making progress with an idea called "protrusion ratio".

<img title="Protrusion of diagonal vs. that of radius" src="protrusion1 - cropped, cleaned, and resized.png"> <img title="A close-up of protrusion" src="protrusion2 - cropped, cleaned, and resized.png">

## 2018-09-02

Still procrastinating.

We are using n-dimensional cube and tiling using (n - 1)-dimensional spheres and then going from Euclidean distance to Manhattan distance upper bound via added sqrt(n) factor. We expect to still have decay. We may be interested in stripping out constant factors to make plotting easier. We still need to incorporate average l1-norm distance, even if (thinking into the future) we eventually are able to exploit sparsity and are dealing with not n equidistant points but perhaps with only two equidistant points; a current motto of ours is that truncated decay is still decay, but over a smaller domain. We may wish to subtract from this average a one because we need (and can afford) an entry point.

To be truly confident, we would like to know if average over n terms in n-dimensional space minus one gives same order as average over two terms in n-dimensional space minus one.

If due to sparsity we have only two points in n-dimensional space (e.g. if we have two non-zero A rows), we can look beyond discrete aspect and have integral s.t. we also have coarse sampling.

Here is a useful result -- integral of 1 / x shifted left so that there is no singularity at x == 0 (and instead there is one at a negative x) is logarithm; this implies that we don't have to do much that is special to properly take advantage of sparsity. For our geometric approach, either an item for an A row or B column appears or it does not.

So, unlike we just said on September 1st, surprisingly, it looks like logarithms for equidistant aspect may appear as long as we integrate. It's unclear at the moment whether the l1-norm distances for equidistant codes will lead to polylog(n) terms; that is power of log that may be larger than one.

We can handle rectangular input matrices trivially; it is as if we just have more or fewer A rows or B columns.

A more difficult thing to handle is running time in terms of number of non-zeroes; all we can do at the moment is hand-wave and say that if we have lots of zeroes, we are tending towards localizing for the codes on Hamming hypercube. Imbalance -- e.g. having much more zeroes than ones -- leads to localizing, which reduces time for pre-processing. This will have to be a future issue to consider, if we want to get desirable behavior, to get specific time bounds, and to do it justice.

Based on recent news, it looks like there's competition from a school in Massachusetts.

## 2018-09-01

We're interested in seeing how distance to closest neighbor decreases at worst as we increase the number of points on a hypersphere or hypercube. Intuitively, the biggest distances occur with small number of points; as we continue to add points with requirement that we have equal spacing, the distances decrease relatively less than they do earlier on. Further, say we have n points on an n-dimensional cube or sphere. One might think that by increasing the dimension at the same time that it could be the case that average distance does not approach zero as n approaches infinity. Surprisingly, we do observe decay as n approaches infinity. An important issue is to find out after scaling (to account for differences between l1 norm and l2 norm) and solving for ideal packing whether the decay implies time in O(n ^ 2 \* polylog(n)). It seems unlikely for us to actually have logarithms explicitly involved for this step, so we are hoping that this step is in O(n ^ 2) and other steps will act as bottlenecks and have logarithms involved.

We are planning on using (1 + epsilon)-factor approximate NN with epsilon at most one; also, we use bichromatic approximate closest pairs and Prim's for finding approximate MST. These should be able to work even though our dimension is n (i.e. it is high). Chan 1998 has information on such tasks and his approaches do not have chance of failure as would be the case with locality-sensitive hashing. Also, it seems a lot easier to implement ANN rather than exact NN and for our application we can accept at most a constant epsilon for error ratio. This is true even though relation between l1 and l2 norms is non-trivial and we must assume that we have only the n input points (and then argue that with 2 \* n points we are strictly better; these 2 \* n points include n input points and n points resulting from XOR).

These distances are important because they tell us about how XOR one-bits decreases; intuitively, since the sphere or cube has finite surface area, there must be decay in min. distances. Also, intuitively, concentrated points give good XOR for nearest neighbor; this is essentially why we consider evenly spaced out; this latter case is the opposite of the former case qualitatively.

We will need to find out surface area of higher-dimensional hypercube. We can use XOR s.t. input vectors are replaced with representation vectors with at most two non-zeroes and dictionary vectors we memoize cut-out/expiry rectangles for based on neighbors. We first create MST. We're happy with 2-approximation because this just means XOR distances are multiplied by two overall, which does not affect decay order. We could later find a trade-off that reduces epsilon s.t. we can afford it. Then, we choose an entry point for the tree. Then, all other nodes are based on some node we previously memoized for.

We use many upper bounds; e.g. for Euclidean vs. Manhattan distances, for sphere vs. cube, NN for islands vs. MST for tree, dimension for n-dimensional cube vs. dimension for primitive on its surface (i.e. the primitive's dimension is n - 1), adding more (i.e. O(n)) XOR-related points is at least as good as having only input points (i.e. we have n input points and possibly 2 \* n points that each ar either from input or related to result from XOR).

Intermediate coefficients that are not in {0, 1}, i.e. that are possibly greater than one or that are negative (possibly counterintuitively) or that are fractional are fine as long as result coefficients for each query end up being in {0, 1} for Boolean MM. Fractional case is not desirable for Boolean MM because we would like to later for floating-point case be able to take advantage of word packing. If Boolean case does not have intermediate coefficients that take O(1) bits in a sense, having word packing would seem quite expensive for floating-point case. Thankfully, Boolean MM does appear to support only ever having handful of bits (i.e. O(1)) for intermediate coefficients.

Average time is useful because it captures concept of decay and we can rewrite a certain sum of terms assuming (affordably enough) the dynamic structure for ANN always has O(n) points, even if it may have significantly less at certain moments in time.

Our goal is to find the time for cut-out/expiry memoization based on decay and surface area for n-dimensional hypercube and volume for (n - 1)-dimensional hypercube. These values will involve gamma function.

For n equidistant points in n dimensions, distinction between NN-island-based and MST disappears because both are associated with same weight. NN-island-based overall weight for n points bounds the same for n - 1 points in n dimensions. MST overall weight for n points bounds the same for n - 1 points in n dimensions.

Other tasks include Applecare before December, crown, CS 61A and CS 169, certain math subjects, group appointment, trip overseas at close to end of September, paying Pelham pharmacy over the phone, picking up certain side-effect medications early enough, gathering old songs for piano and practicing, getting gym perks card punched, exercise (e.g. basketball), gathering certain materials for classes in high school (e.g. for AP Biology), read books for AP Literature, fixing wrong name for bill for insurance, selling certain odds and ends (e.g. music CDs, high school study aids, graphics book pair), tactile display project, refine portfolio/resume, possibly contact headhunters, retrieve Philos. 138 notebook.

Time is of the essence; we've seen quite a bit of new articles talking about MM. It seems that people may be smelling blood. We will want to implement our approach and post on arxiv.

Relevant resources:

* Chan - Approximate nearest neighbor queries revisited (1998)

* Scott - StackExchange - Manhattan distance vs. Euclidean distance - Answer (2015)

  https://math.stackexchange.com/questions/1168759/manhattan-distance-vs-euclidean-distance

* EuYu - StackExchange - Hypercube maximum distance, graph theory - Answer (2012)

  https://math.stackexchange.com/questions/232713/hypercube-maximum-distance-graph-theory

## 2018-08-27

We tried out other people's implementations for FJLT and figured out that there was an assumption for dot product preservation additive error bound of epsilon which is that norms of input vectors are at most one. This means that for Boolean matrix multiplication that for exact approach the bound we want is epsilon\_old / n. Then, with target dimensionality proportional to 1 / (epsilon ^ 2) = O(n ^ 2 / epsilon\_old), which is much larger than polylogarithmic in n. On the positive side, though, forcing the case that we have unit norm does seem to make the algorithm (for dimensionality reduction) give reliability as good as predicted by many papers in the sense that we often have dot product (s.t. we are less than or equal to one) that stays within small additive error.

It's fun to go after transformations, but probably advisable to hold back on it given that to solve a problem it is often the case that one needs to go after a strength reduction, which is arguable diametrically opposed to finding a reframing of the problem.

## 2018-08-26

We are going to attempt implementing fast Johnson-Lindenstrauss transform with random projections. Then, we will attempt version with Toeplitz and circulant matrices. This is to get a sense of whether distance or inner product invariants with bounded small additive error hold reasonably not just on paper but in practice.

## 2018-08-11

We should note that we finished, for all intents and purposes, remedial work for Physics 24 from freshman year first semester on Wednesday 7/25 afternoon.

Came back from vacation in Iceland for a week from Friday 7/27 night to Friday 8/3 night.

We have found a way to get close-to-optimal time for Boolean MM, i.e. a quadrarithmic-time algorithm for it that doesn't require explicit packing as for bit spread/gather. It's tricky to know how much we need to get done before we should publish and in this sense it's a bit stressful. Part and parcel with the task, I suppose. We are attempting to implement, so there could be hidden issues. Morale boost can come from writing drafts of the article. For the most part, the work is essentially a secret, for now; I wouldn't want to get front-run.

## 2018-06-17

We went back to Physics 24, a freshman seminar with Prof. Jacobsen, from freshman year first semester (Fall 2007).

One thing that had been nagging us was a quote from Feynman about how in the low-intensity double-slit experiment lies "the heart of quantum mechanics" and "[its] only mystery." This is apparently from the Feynman lectures from 1965.

First, we must note that the standard double-slit experiment shows that particles can have wave-like behavior in that corpuscles shot at slits behave s.t. we observe interference much in the way one might expect if we shot corpuscles of water through slits on the surface of a lake.

The low-intensity flavor is, in our opinion, more interesting.

Where is the beef?

We're just going to go ahead and state that we assume that the multiple-worlds interpretation (MWI) is valid; this is to us a particularly colorful way of remembering an appropriate way of making sense of experimental results. In our opinion, there are three meanings of "wave" that we ought to care about. They are to do with (1) imprecision, (2) filled space, (3) multiple worlds. The first is valid when e.g. considering electron orbitals in chemistry given that we assume there are sub-atomic particles flying around in a relatively small region of space. The second is valid from the perspective that particles can be represented as waves and vice versa as we are apt to do in electrical engineering via Fourier analysis. The third is valid specifically to explain sterile environments such as in low-intensity double slit and EPR. We claim that wavefunction (or matter wave) is doing double duty and covers both the first and third types (i.e. imprecision and multiple worlds).

In the low-intensity double slit experiment, if treating the photons we shoot as particles were enough, why would we build up an interference pattern when we avoid determining which slit each particle passed through? Presumably, if each particle stays intact as we shoot them, they should not lead to interference ever.

If treating the photons we shoot as waves were enough, that would explain how we get an interference pattern in the high-intensity case; remember that this was originally the point of the standard experiment from Young in that sometimes we should consider that particles can behave like waves. But this is an inadequate approach for the low-intensity case because we require that the photons we shoot (even allowing for particle-wave equivalence via Fourier analysis) exist as covering point-like regions in space.

Let us assume we use photons to bounce off corpuscles. We know that momentum for the photon is inversely proportional to its wavelength. Resolving power for when we use this photon is also inversely proportional its wavelength and thus is proportional to its momentum. There have been experiments showing that with lower momentum when shooting these measurement-related photons near each slit we get closer to situation where we don't shoot measurement-related photons at all (as we would expect, if we assume that these measurement-related photons are prone to mucking up the paths of the corpuscles by virtue of imparting force). But, with lower momentum means worse resolving power; and it turns out that at the point where resolving power is s.t. we can distinguish between which slit a corpuscle must have gone through to the exclusion of the other, the interference pattern becomes absent and we just have a sum of two peaks as number of samples increases.

With multiple-worlds interpretation, we have mechanism of superposition across worlds. One might attempt as a last gasp to avoid this; say that we treat each corpuscle as an intermediate between particle and wave. Imagine that we have a wavefront emanating from a point source that comes to cover a large expanse and when it interacts with another object it is replaced by a particle. But, as we want to be able to visualize what is happening, would we have the particle that we end up with actually making up the original wavefront in a way similar to what we like to visualize with an electron orbital from chemistry; i.e. we have some traversal pattern and we then use concept of imprecision-based wavefunction? It seems to us personally that it is unreasonable to require that we imagine this traversal pattern that turns a particle in a sterile environment into a possibly large and intricate wavefront prior to collapse unless we come up with some mental aid. And, of course, we should be in compliance with clean probabilities and collapse for the various double slit scenarios.

So, let's say there is a concept of "wave" that we need to introduce that is orthogonal to both of the other two meanings of it that we mentioned before. This "wave" is one that leads us to consider multiple worlds. Let us talk about extremes; i.e. we don't consider where the boundary is between world-related collapse and world-related non-collapse for now (let alone for imprecision-related collapse/non-collapse). Presumably, world-related non-collapse is associated with sterile environment and world-related collapse is associated with what one normally encounters; this is how we arrive at a flavor of correspondence principle. As a reminder, we have correspondence principle for non-world-related small-scale, i.e. non-world-related QM, and for large-scale, e.g. relativity, s.t. they have as special cases intermediate-scale, i.e. classical physics.

Using multiple-worlds interpretation, when we look at low-intensity double slit experiment, we say that upon collapse (i.e. let's just say imprecision-related and world-related collapse are the same) if precision of our measuring equipment is s.t. we can rule out a slit then we are ruling out certain worlds and we effectively select a specific world. Then, that explains why if we collapse at slits we have no interference and if we collapse at recording screen we do.

We use the word "explain" loosely; this effectively is just a mental aid.

Apparently, MWI is compatible with EPR as well; we have world-splitting s.t. one of two entangled particles has a certain spin in one world and a different spin in a second world; once you collapse (and we will avoid talking about what causes collapse specifically), then you know about both particles' states as you've selected a world and as the sum of the spins is fixed. Also, ostensibly this is described as not being non-local.

We should mention the Copenhagen interpretation, by which we really mean a maximally non-committal interpretation. It would then be understandably more popular, given that it is also the case that we currently do not have a way to distinguish between such an approach and MWI based on current experiments (if it is possible at all). By non-committal, we mean this "Copenhagen" approach is agnostic as to giving a name to the mathematical behavior (such as having many worlds). It's been debunked that Feynman has said this specifically, but there are people who have described the default stance of many in the field (which might clumsily fall under the name of Copenhagen) as "shut up and calculate". By avoiding choosing an interpretation that goes beyond just the math, one arrives at what I admit is already present in a clean way in the summary section of Feynman's low-intensity double slit lecture. He describes straightforwardly in words "first principles" that would be sufficient to describe the observed interference/non-interference based on what we know about alternatives that is fairly non-committal and thereby avoids the risk of having some future discovery that breaks our impasse and that could make our decorational term ("many worlds") seem excessive.

Quantum teleportation, used for transferring qubits, uses entanglement.

Quantum cryptography also uses entanglement.

Important features of quantum computers are superposition/indeterminacy and chaining. Armed with the MWI perspective, it becomes easier to imagine why in a sterile environment strategically using pre-collapse particles can be in multiple states at once. Also, depending on your computational approach, we might be entangling in a way specific to your problem and entanglement is something we spend (i.e. we must be able to re-entangle at will).

A result is that we now have a bridge towards understanding the basis for quantum computing. Specifically, we have a sense of why it is plausible that for certain problems quantum computers could lead to exponential speed-up. That is, we could have an incredible number of worlds contributing to a probability distribution. However, we still need to design the algorithm s.t. we recover an answer assuming that we will not spend O(1) time for each world (i.e. a permutation from the search space). Also, we have a sense of why it is plausible that the problems that we can now solve in polynomially-bounded time is still not all of NP.

More concretely, we may also like to start thinking about quantum algorithms.

Relevant resources:

* Topics from quantum mechanics covered briefly (Univ. of Toronto, 2010)

  https://faraday.physics.utoronto.ca/GeneralInterest/QM.html

* Key - Quantum interference (Univ. of Toronto)

  https://faraday.physics.utoronto.ca/GeneralInterest/Key/quinterf.htm

* Key - Quantum mechanics: a poor person's guide (Univ. of Toronto)

  https://faraday.physics.utoronto.ca/GeneralInterest/Key/qutheory.htm

* Harrison - Stern-Gerlach experiment (Univ. of Toronto, 2005)

  https://faraday.physics.utoronto.ca/GeneralInterest/Harrison/SternGerlach/SternGerlach.html

* Harrison - Quantum teleportation (Univ. of Toronto, 2004)

  https://faraday.physics.utoronto.ca/GeneralInterest/Harrison/QuantTeleport/QuantTeleport.html

* Feynman Lectures on Physics - Vol. III Ch. 1 - Quantum Behavior (1965)

  http://www.feynmanlectures.caltech.edu/III_01.html

* Quora - What is Einstein-Podolsky-Rosen paradox and its solution?

  https://www.quora.com/What-is-Einstein-Podolsky-Rosen-paradox-and-its-solution

* Quora - How does the many worlds interpretation of quantum mechanics explain the EPR paradox?

  https://www.quora.com/How-does-the-many-worlds-interpretation-of-quantum-mechanics-explain-the-EPR-paradox

* Quora - What is the Copenhagen interpretation?

  https://www.quora.com/What-is-the-Copenhagen-interpretation

* Mermin - Could Feynman have said this?

  https://physicstoday.scitation.org/doi/10.1063/1.1768652

## 2018-05-07

Parallelism.

parallelism for construction and memoization should probably work in same overall time; except, now that we possibly have parallelization for all phases, larger n should be more commonplace (due to more acceptable concrete time used) and we should be able to reach parts of the time curve where we are significantly more favorable, even after taking into account constant factors for our algorithm

What do the below resources mention?

Finished Pride and Prejudice on May 4th, 2018.

Got root canal done in China.

Relevant resources:

* Datta - Efficient parallel algorithms for geometric k-clustering problems (1994)
* Cole - Parallel merge sort (1986)

## 2018-04-07

I'm in China right now.

I figured I should note some things that I've come across recently.

Apparently, deep neural networks (DNN's) can be formulated in a way that makes heavy use of matrix multiplication, according to a recent article from EE Journal.

Also, an Abstruse Goose comic recently came out that talks about the link between lucrativeness, general AI, matrix math, undergraduate math, working "by one's self" in a bedroom.

Still doing remedial work.

Resources:

* Abstruse Goose - The $25,000,000,000,000 Matrix (April 2, 2018)

  http://abstrusegoose.com/583

* Leibson - EE Journal - Fifty (or Sixty) Years of Processor Development...for This? (March 29, 2018)

  https://www.eejournal.com/article/fifty-or-sixty-years-of-processor-developmentfor-this

## 2018-01-31

We should note that for rectangular matrix input case s.t. we have A as a n\_1 x n\_2 matrix and B as a n\_2 x n\_3 matrix, we have a more detailed cross-over condition that treats square matrix input case as a special case.

Before, brute-force time is O(m / n \* n ^ 2) = O(m \* n), where m is number of input non-zeroes. Rader-NTT-hybrid-related magic bits determination for fancy approach takes time O(n \* polylog(n)). Assuming O-tilde is O(n ^ 2) at worst, cross-over m is O(n) or O(n \* polylog(n)).

Then, with rectangular input matrices, brute-force time is O(m / (n\_1 + n\_3) \* (n\_1 \* n\_3)), where m is number of input non-zeroes in either A or B. Rader-NTT-hybrid-related magic bits determination for fancy approach takes time O(n\_2 \* polylog(n\_2)). So, what is cross-over m? Assuming O-tilde is O(n\_1 \* n\_3) at worst, O (non-tilde) is O(n\_1 \* n\_3 \* polylog(n\_1 \* n\_3)). Setting the brute-force time to O-tilde time based on max. output number of non-zeroes, we get m equal to O((n\_1 + n\_3) \* polylog(n\_1 \* n\_3)). Then, cross-over m is max((n\_1 + n\_3) \* polylog(n\_1 \* n\_3), n\_2 \* polylog(n\_2)). Note that this degenerates for square case s.t. for n\_1 = n\_3 = n\_2 == n, cross-over m is again O-tilde of n or O(n \* polylog(n)). We have one last step; we are wondering whether if we can't afford Rader-NTT-hybrid-related magic bits determination, that brute-force-designated time (i.e. left of cross-over after introducing the max operator) is still in O-tilde of n\_1 \* n\_3. Is this the case? No, it isn't. However, we still have time softly quadratic in max(n\_1, n\_3, n\_2) and this is satisfactory. To reiterate, the cross-over m that we give is possibly s.t. times resulting from being on brute-force-designated (i.e. left) side of boundary could be huge as n\_2 can be arbitrarily large, given that n\_2 is independent of n\_1 or n\_3.

We should remind ourselves that rectangular matrix product is also a case of sparse square matrix product.

High n\_2 relative to n\_1 and n\_3 means high left-of-boundary, relatively speaking. Low n\_1 and n\_3 relative to n\_2 means low right-of-boundary, relatively speaking.

## 2018-01-28

We somehow got a burst of reputation points for various StackExchange sub-organizations, so we have enough to start posting comments for CS Theory subject. We did so for a conversation between Blaeser and Jeffε.

We are unsure as to how to tackle sparsity. We know that if n\_{non-zeroes, A} and n\_{non-zeroes, B} (i.e. for input matrices A and B) are <= n, the worst-case output non-zeroes is n ^ 2 and time in O(n ^ 2). However, at the other extreme, if we are not unlucky, for this case, we have output non-zeroes equal to one and time in O(n). We just barely reach worst-case time of O(n ^ 2) with the two caps on number of non-zeroes for A and B, so when we surpass the caps, we can resort to our fancy algorithm, which guarantees time softly quadratic in n. Conveniently, also, magic bits for Rader-NTT-hybrid takes O(n \* polylog(n)) time to generate, which is close to the boundary we have erected between brute-force and our fancy approach. We should note that this could be not as big of a deal if we have many same-size input matrices to find product for as we can re-use the Rader-NTT-hybrid-related magic bits.

We should note a distinction between output trivial zeroes and non-trivial zeroes; the latter is due to cancellation. We don't actually use this concept much for our current f.p. MM approach, though, as we are not output-sensitive for this first pass.

In many papers, we see that so-called sparse approaches for MM don't actually seem to provide time better than O(n ^ 2) except brute-force, which guarantees O(n \* n\_non-zeroes) time. They seem to mainly have speed-up assuming omega is not two (i.e. our ability to attain omega approximately equal to two makes these approaches less appealing). This includes Lingas; Yuster and Zwick; Le Gall; Jacob and Stoeckel; Amossen and Pagh. On the other hand, we might be deceived s.t. the bounds involving O(n ^ 2) may not necessarily be tight.

We might wish to also consider output non-zeroes if we have a fast way of estimating. However, we are reluctant to use existing methods (e.g. from Cohen or Amossen et al.) because they are randomized and approximate (i.e. at any given time may be totally wrong or not totally wrong but not exact). How we might use this information is to be able to consider minimal number of A-row-B-column pairs s.t. dense approach can be informed by the need to only consider these pairs and we get perfect exploitation of sparsity and get good time, except we also have to consider time for one-time operations, like determining Rader-NTT-hybrid-related magic bits, and time for finding output non-zeroes. This said, having affordable way to find output non-zeroes consistently and exactly almost seems like it would be too good to be true.

We should note that rectangular matrix multiplication can be viewed as sparse square matrix multiplication.

Also, we should note that one way of concisely interpreting our first-pass approach that takes advantage of sparsity is that we have time roughly optimal across worst-case configurations with given number of input non-zeroes; i.e. we have a gap between n and n \* polylog(n) which we could ignore, partially because there is precedent in that omega ignores polylog(n) factors. Alternatively, we could instead of having a boundary at n\_non-zeroes = O(n), we can have one at n\_non-zeroes = O(n \* polylog(n)) and the cross-over in terms of time would be more seamless. Since it seems unreasonable to currently believe omega can be two (i.e. not softly) without polylog(n) factor, one way to reasonably refine the description of our behavior is to say we have O-tilde time that is optimal across worst-case configurations with given number of input non-zeroes s.t. O-tilde hides polylog(n) factor.

Brute-force approach leads to O(n \* n\_non-zeroes) time for square input matrices of size n x n because then (s.t. n\_{non-zeroes, avg.} is number of non-zeroes per A row or B column) n\_{non-zeroes, avg.} \* n ^ 2 = O(n\_non-zeroes / n \* n ^ 2) = O(n\_non-zeroes \* n). Evenly distributing non-zeroes across A rows and B columns leads to maximal blow-up in time and we argue that under no circumstances is uneven better than even for blowing up time. This time is corroborated by many sources - e.g. Yuster and Zwick; Lingas; Buluc and Gilbert.

Again, we can place less emphasis on the O-tilde time for boundary between brute-force and our fancy approach being compatible with time needed for Rader-NTT-hybrid-related magic bits determination given that it seems somewhat reasonable to expect that we deal with same-size matrices s.t. we can determine the Rader-NTT-hybrid-related magic bits once and re-use them.

We still have not attempted non-SIMD, i.e. multiple-instruction-stream (e.g. MIMD), parallelism; parallel construction of 2-D range tree with fractional cascading seems to be the main challenge and (at some level) it seems unlikely to not be possible; however, it is possibly not the best subject to spend our time on at the moment, as if the rest of the f.p. MM algorithm works out, it will still have been a good accomplishment. If we get the that point, then we can choose to keep MIMD on backburner and chip at it gradually.

Again, we plan on returning to CS 61A material; this spurt of effort should be considered out of the ordinary, as it was nagging at us to find some consistent strategy for at least marginally exploiting sparsity for f.p. MM. Also, again, it's great that we have a blog so that we can change subjects for our attention on a dime.

Conversation from StackExchange:

* Blaeser - StackExchange - Complexity of computing the discrete Fourier transform? - Answer (2011)

  https://cstheory.stackexchange.com/questions/8196/complexity-of-computing-the-discrete-fourier-transform

Sparse MM resources:

* Amossen and Pagh - Faster join-projects and sparse matrix multiplications (2009)
* Pagh - Compressed matrix multiplication (2013)
* Le Gall - Faster algorithms for rectangular matrix multiplication (2012)
* Yuster and Zwick - Fast sparse matrix multiplication (2005)
* Buluc and Gilbert - Highly parallel sparse matrix-matrix multiplication (2010)

Output non-zero estimation for MM resources:

* Amossen, Campagna, Pagh - Better size estimation for sparse matrix products (2010)
* Jacob, Stoeckel - Fast output-sensitive matrix multiplication (2015)
* Cohen - Structure prediction and computation of sparse matrix products (1998)

## 2018-01-18

A problem is that we are exploiting sparsity, but magic bits for Rader combined with NTT require time big-omega of m \* polylog(m) time; m \* polylog(m) is in O(n \* polylog(n)); this means that we might not be able to take advantage of when number of non-zeroes is around less than n; we are not exploiting sparsity as much as we could unless we can come up with Rader-NTT-hybrid magic bits more quickly, which may be possible, but requires further investigation.

Also, we should note that we have not begun to consider processor parallelism; we are partly embarrassingly parallel, but not entirely (e.g. construction of 2-D range tree; as opposed to queries, for which we are embarrassingly parallel).

Also, we should note that we are not yet taking advantage of caching.

We are going to take a break and address lower-hanging fruit. This means less fast MM, numerically robust 2-D order-1 Voronoi and order-k Voronoi. This also means that we will divert energy towards CS 61A material and CS 169 MOOC. We note that this decision is partially driven by the realization that our internal ETA for order-k Voronoi is essentially infinity at the moment. Thank goodness we have a blog to help us change course more nimbly.

## 2018-01-17

The Zhang article mentions that Ben-Kiki has described an O(1)-time algorithm for finding left-most set bit in a word.

We note that word RAM does not directly give us good f.p. MM time, but it gives us flexibility.

Zhang tells us how to convolve in word-packed manner without going through FFT. We use direct definition of linear convolution, which leads to a time-domain signal, and re-write in terms of "diagonals".

We might think we are stuck, but then we can refer to Rader's FFT algorithm, which defines DFT (and possibly NTT) in terms of cyclic convolution. We can then define cyclic convolution in terms of linear convolution using "cyclic prefixing". We use a prime size for cyclic convolution equal to or larger than our given size. An alternative is to use Bluestein's FFT algorithm.

We determine "magic bits" for Rader-related partner signal once for each layer, of which we have at most five; we re-use these signals quite often. So, it is okay for the work for these signals to not involve time that benefits from the values being word-packed.

Crisis averted! We might still be able to use Zhang and we do so to implement NTT.

We still need to know whether Rader can be combined with NTT; and we have to accept another requirement - i.e. that Rader needs a prime size.

Relevant resources:

* Ben-Kiki et al. - Towards optimal packed string matching (2014)
* Dunna - How do I convert circular convolution to linear convolution? (2017)
* Rader - Discrete Fourier transforms when the number of data samples is prime (1968)
* Wikipedia - Rader's FFT algorithm
* Wikipedia - Convolution - Discrete convolution
* Wikipedia - Cyclic prefix

## 2018-01-13

Thankfully, we are safe w.r.t. Zhang word-packed NTT-based convolution. The time, from perspective of our application (f.p. MM), is O(m / m' \* log(m) \* log(m / m' \* log(m)) = O(m / m' \* log(n) \* log(m / m' \* log(n))), which leads to bottleneck time of our algorithm at around O(n ^ 2 \* log(n) ^ 2 \* log(m / m' \* n)) (as opposed to O(n ^ 2 \* log(n) ^ 3)). Of course, if m = O(m'), as is often the case, then we have a time of O(n ^ 2 \* log(n) ^ 3), again.

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

We deviate from what turned out to be an assumption made by someone else that at one point in time made us worry that the time for FFT is possibly O(n \* log(n) ^ 2). We don't have enough karma to post a comment directly to someone else, so we are recording our logic for posterity here. We should note that the assumption of significand size b = O(log(n)) is totally arbitrary. An equally plausible situation is b = O(w). Then, assuming we have floating-point numbers that fit in a word (of size w) and assuming that word operations generally take O(1) time each, time will be O(n \* log(n) ^ k) with k == 1, given that we want to support all numbers representable by such a floating-point number. Also, of course, Blaeser is being generous to Jeffε s.t. technically O(n \* log(n)) is in O(n \* log(n) ^ 2).

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

* Blaeser - StackExchange - Complexity of computing the discrete Fourier transform? - Answer (2011)

  https://cstheory.stackexchange.com/questions/8196/complexity-of-computing-the-discrete-fourier-transform

* Project Nayuki - Number-theoretic transform (integer DFT) (2017)

  https://www.nayuki.io/page/number-theoretic-transform-integer-dft

## 2018-01-10

We have to remember that we have two staircases for each point arrangement, of which we have two.

We realized that for a 2-D range tree, we don't have overall O(n) leaves for lower-level trees unless we use fractional cascading. Then, we will do so and choose an arbitrary lower-level leaf for each of O(n) points and make sure that we do so consistently. This cuts down range-tree contribution polylog(n) = O(log(n) ^ 2) to O(log(n)), which keeps the bottleneck polylog(n) factor at O(log(n) ^ 3). We note that we had a factor of O(log(n) ^ 2) already due to inflation from multiple passes of FFT.

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

We may now, then, have next the step of somehow finding word-packed NTT FFT via Zhang.

Edit: We haven't actually figured out if Zhang gives us convolution without FFT or it gives a faster FFT. The former is more tricky to make use of.

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
* AP English Lit. reading - Brave New World, Pride and Prejudice (done), Oedipus, Heart of Darkness, The Return of the Native, Hamlet (done), Mythology (done), Uncle Vanya, Great Expectations (done), My Antonia (done), Macbeth (done), The Importance of Being Ernest (done), Crime and Punishment, Madam Bovary
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


