# justmarried
## A graph theory approach to marriage, roommates, and college.
This project is concerned with matching people to people and people to things. We explore this in three flavors. 

The first problem deals with arranging marriages. This would be an easy problem if no one had preferences that overlapped. But the real world doesn't care if problems are easy. So rather than trying to arrange marriages that are simultaneously optimal for everyone, the solution here is concerned with stability. This means that there's an arrangement where no two people would rather be married to eachother than to their spouse. 

The second problem is a variation on the first. While the marriage problem is restricted to matches _between_ sets ("men" and "women"), the solution to this problem also allows for matches _within_ sets. 

The final problem comes up in college admissions. Colleges allot a fixed number of students to admit each year. But they can't assume that everyone admitted will accept. After all, some students are admitted to more than one school, which means every school but one will have a smaller-than-expected incoming class. And since no school knows with certaintly what the applicant's top school is, every college must admit more people than allotted. And waiting lists don't solve this problem. A student may accept admission to a safety school and join the waiting list of a top choice. Then if they're admitted to the top choice, they'll have to retract acceptance of the safety. The solution implemented here will guarantee that every college will exactly meet its quota while still preferentially matching students will schools.

### Marriage
Imagine this scenario: 
> A town would like to arrange marriages for its single men and women. Each person has a list of opposite sex suitors in order of preference. The town would like to find an arrangement that ensures no two people would rather be with eachother than with their partner. In other words, marriages should be stable. 

This is called the stable marriage problem (or the stable matching problem), which this project explores in detail. In addition, it will dive into two variations of stable matching, namely the stable roommates problem and the college admissions problem (also known as the hospital/residents problem).

Lloyd Shapely and David Gale were awarded the Nobel Prize in 1962 for proving that [for any pattern of preferences, it is always possible to find a set of stable marriages](https://apps.dtic.mil/dtic/tr/fulltext/u2/251958.pdf). They proved that there's always a configuration where instability doesn't occur. (Instability is when two people prefer each other over their partners.) The walkthrough below will make some sense of this.

The Gale-Shapely algorithm has the [following steps](https://www.youtube.com/watch?v=Qcv1IqHWAzg):
1. Everyone creates a list of who they'd like to marry in order of preference.
1. On day one, women submit their proposals to the men. Some men won't receive any, while others will receive more than one. Men that receive a proposal select the person they most prefer.
1. On day two, women that were rejected submit a proposal to their next choice. Men can negate their previous agreement if they receive a better proposal.
1. This continues for days three, four, five, etc.
1. Finally, a configuration is reached where everyone is in a stable marriage.

The  algorithm consists of [the following theorems](https://www.youtube.com/watch?v=LtTV6rIxhdo)::
* *Theorem 0* It eventually stops.
* *Theorem 1* It finds stable marriages.
  * Proof: No woman can trade since they propose their next highest preference each day until they're no longer rejected.
* *Theorem 2* It assigns every woman her best possible husband.
* *Theorem 3* It assigns every man his worst possible wife.

This algorithm arranges [simultaneously optimal marriages for women and simultaneously suboptimal marriages for men](https://youtu.be/LtTV6rIxhdo?t=331), leading to an interesting property; **It's far better to propose than to be proposed to!**

### Roommates

### College
