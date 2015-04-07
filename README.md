# Theory 1

## Scale Factors
    1. Prec - have we done this before?
        We should choose experienced developers rather than novices. Doing so will decrease the effort needed.
    2. Flex - development flexibility
        If we have to meet lots of interface specifications then that will drasticaly harm our speed. Let's minimize those specifications.
    3. Resl - risk resolution
        We should identify as many risks as possible and develop a plan to mitigate each one.
    4. Team - how 'together' the team is
        We'll choose the team that has worked together a lot rather than forming a brand new team. Doing so will decrease our effort.
    5. Pmat - process maturity
        Switching from our ad-hoc and undocumented process to a proven process like waterfall or agile lets us draw from past experiences and will help us complete our project.

## Decrease effort
    1. acap - analyst capability
        Our best business analyst left and now our team is having a harder time identifying requirements.
    2. pcap - programmer capability
        We found out that one programmer always slacked off. We could replace him with another programmer to get more work done.
    3. pcon - programmer continuity
        We work hard to keep our team happy so that they don't leave. If they did, we'd have to keep training new people and would lose time.
    4. aexp - analyst experience
        We should use our most experieneced team of analysts for the most complex portions of the system.
    5. pexp - programmer experience
        We should use our most experieneced team of programmers for the most complex portions of the system.
    6. ltex - language and tool experience
        Most of our team knows Java. No one knows Haskell. Therefore, we are choosing to use Java so we can ship this faster.
    7. tool - use of tools
        We could buy better development tools for everyone to decrease our time to market.
    8. site - how many physical locations and how well connected?
        We could bring all employees onsite to improve communication and reduce effort.
    9. sced - length of schedule
        We have a compressed schedule and thus will have to put more work in near the end of the project.

## Increase effort
    1. rely - how reliable the software must be
        NASA needs our software to never crash. This is going to take a ton more effort than we thought...
    2. data - secondary memory storage requirements
        Sounds like we'll have to store multiple petabytes of information which will require a lot of overhead.
    3. cplx - program complexity
        When the client called us initially, the project sounded simple, but we found out it was very complex once we talked with him.
    4. ruse - software reuse
        We want to reuse this software later so we'll have to put more time into it now so that we don't have to later.
    5. docu - documentation requirements
        We're going to have to ship our portion of the contract to have another team finish it. This means we to need to heavily document the work which will take more time.
    6. time - runtime pressure
        We're making a video game, thus everything needs to run in real time. This will take a lot more work.
    7. stor - main memory requirements
        If we have to run on embedded systems, we won't have very much memory and will have to design our system so that it can run in those constraints.
    8. pvol - platform volatility
        If we use a long term support release of Ubuntu we should have to worry about less frequent updates.



# Theory 2

1. Improve personnel
    * Our team sucks, so we should get better people. This will let us use less effort. Specifically, we want analysts who are more talented and experienced as well as programmers who are more talented and experienced.
2. Increase Architectural Analysis Risk Resolution
    * If we spend more time look at the upcoming risks and how to mitigate them we will be able to put less effort into the product.
3. Reduce functionality
    * If we reduce the scope of the product we will definitely be able to put less effort into the product.


# Theory 3

## Three Key Differnces between flight and ground:
1.  There is 1 more values for the reliability factor (rely) for ground but the additional number is low.
    - This can be interepretted as the associated risk seem less.

2.  The range of lines of code(kloc) is smaller for ground.
    - The values leads to a more confident/precise analysis of the project

3.  The program complexity(cplx) values for flight are higher [3,4,5,6] and ground is [1,2,3,4]
    - They have the same number of values but the intensity is higher for the flight project.

## Three Key Differences between osp and osp2:
1. Development flexibility(Flex) for osp2 only has a subset of the values liste in osp.
    - osp Flex= [2,3,4,5] v.s. osp2 Flex=[3]

2. In osp2 the dimension of runtime pressure(time) has been added.
    - This can be considered as one of the additions that can are added to scope as a project grows.

3. The number of values associated with process maturity(pmat) is now smaller and considers higher values in osp2.
    - osp Pmat = [1,2,3,4] v.s. osp2 Pmat = [4,5]


Overall it seems as though during the estaimation of the second version osp the team felt more confident about what to expect in the project incomparison to the first version of osp 1.


# Theory 4 

## Bad smell stories

- There are programmers who are not capable of completing this project since they have been trying to conform to using the tool. There is a learning curve between learning the language for the project which is extending the schedule.

Stink[('ltex','pcap')] = Stink[('sced','acap')] = \
Stink[('sced','pexp')] = Stink[('sced','pcap')] = \
Stink[('sced','aexp')] = [
 [4,2,1,0,0,0],
 [2,1,0,0,0,0],
 [1,0,0,0,0,0],
 [0,0,0,0,0,0],
 [0,0,0,0,0,0],
 [0,0,0,0,0,0]]

- We don't have the amount of main memory requirements expected for this project. The analyst on the team  had difficulties understanding what was expected of this project and now we are in a pickle.


Stink[('cplx','acap')] = Stink[('cplx','pcap')] = \
Stink[('cplx','tool')] = Stink[('stor','acap')] = \
Stink[('time','acap')] = Stink[('ruse','aexp')] = \
Stink[('ruse','ltex')] = Stink[('Pmat','pcap')] = \
Stink[('stor','pcap')] = Stink[('time','pcap')] = [
 [0,0,0,0,0,0],
 [0,0,0,0,0,0],
 [0,0,0,0,0,0],
 [1,0,0,0,0,0],
 [2,1,0,0,0,0],
 [4,2,1,0,0,0]]


 - The analyst on the team have issues understanding the task and designing it appropriately. The main issue with this is that we have human lives at stake. The fact the programmers may not be capable to bounce back from any disasterous events makes this a scary situation. 


Stink[('rely','acap')] = Stink[('rely','Pmat')] = \
Stink[('rely','pcap')] = [
 [0,0,0,0,0,0],
 [0,0,0,0,0,0],
 [1,0,0,0,0,0],
 [2,1,0,0,0,0],
 [4,2,1,0,0,0],
 [0,0,0,0,0,0]]



# Practice
We spent several hours looking over the given source code and found the numbers very confusing. Thus while we actually found the below by modifying the values in the code, the output did not seem to be meaningful and is thus not included.

## Task 1
Making a treatment to decrease sced but increase rely made the stink worse but decreased the effort required.

## Task 2
Making a treatment to increase sced and increase rely made the stink better but increased the effort required.

## Task 3
Not attempted due to time.