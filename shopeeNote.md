### Spark

Driver - Workers

用户自定义的Map函数接受一个输入的key/value对值，然后产生一个中间key/value对值的集合。MapReduce库把所有具有相同中间key值的中间value值集合在一起后传递给Reduce函数。用户自定义的Reduce函数接受一个中间key的值和相关的一个value值的集合。Reduce函数合并这些value值，形成一个较小的value值的集合

map(max) -> reduce(max)

1. method1
sublist 1st, then map reduce 

2. method2
mapPartitions(lambda x: [max(x)]) works on all the iterables

use write_csv instead of toPandas

#### SQL
1. less columns in select
2. use union all instead of union
	- union is using distinct actually

1. Low Coupling

independent

2. High Cohesion

One module do one thing

DRY instead WET(write everything twice) code



### Shopee CX sharing

Inspiration seeking - Finding - 


Seller
#### Profiles:
1. age, gender
2. order volume
 - sign up, early life, core

F >24, <=24, M -
\#  orders >15, 1-15, 0


People prefer use IG first

Hypothesis 1: IG has better visuals for discovery

Finding:

People prefer to research products outside Shopee
1. websites
2. youtube

What people see on product card:

Seller type

Image

Reviews

photo

#### PDP: Product details page
1. Make reviews more accessible by removing seldom used info on PDP

Make nudges to let customer prone to leave picture review

2. Users want to know the shipping from, but rarely use filter to filter location

show shop location in product card

3. standardize warranty

#### Shop page
1. to check updates
2. to check more items

emphasize products on Shop page instead of shop info


new users & core users: hasn't buy 180 days|

#### Home page



1. differs among core, early life and sign up

	- core users: Flash deals, daily discover
	- sign up users use **categories** more than core & early life users

Follow-up:

optimise category navigation for new users

2. Find the page too croweded
	
	- simplify the home page
		- cut the flash sale displays (3->2)
		- reduce redundant text

#### Overall expression to Shopee

1. top 3 reasons: 
	
	- cheap price, free shipping, promo

2. quality, faster shipping fee


1. Rmb and build relationship with people
2. Who is involved and affected


Why is SM important:
1. Create place and plan for communication
2. 4Ps: performance, people, process, pespectives/purpose
3. Pull vs push communication with stakeholders (balance)

Team Development Model:
Form(clarity) -> Storm(diversity) -> Norm(consistency) -> Perform(celebrate) -> Adjourn(review)

How do you profile your stakeholder:
1. Involvement
2. Character(personality)
3. Power(influence)
4. Objective & KPI
5. Relatinship
6. Strengths and weakness
7. Style of communication
8. Perception
9. Needs
10. Comflicts


Steps for profiling
1. Influence Map:
2. 



|Stakeholder|Impact|Interest|Object|Contribution|Resistance|Plan|
|--|--|--|--|--|--|--|
|Chris|||||||||
||||||||||

Interest Influence

|High Influence|Keep satisfied|Manage Closely|
|--|--|--|
|Low influence|Monitor|Keep informed|
||Low interest|High Interest|

|High Cooperation|Collaborate|Involve|
|--|--|--|
|Low Cooperation|Defend|Monitor|
||Low Threat|High Threat|

PM triangle:

Scope(Quality), Cost(Resources), Time
-->Objective

Yes and & Yes if


#### To solve
##### Priorities:
1. Aligned with boss & sponsor
2. Use the triangle (PM) with yes &
3. Gather stakeholders together and discuss

##### Relationship with different person
1. Deal with emotion first, then deal with issue (in this sequence)
	- Face to face
	- Mood - Talking mode: Parent -> Adult -> Children
	- 4Rs : 
		- Relate (build relate)
		- Reframe (think from their perspective)
		- Reciprocate (think in long term)
		- Remind (remind them what they might have forgot)
	- APAC: deal with objections
		 - Acknowledge(thank you xxx) - Probe(ask) - Answer - Confirm

2. Sequence on: WHAT - WHY - HOW 
