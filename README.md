# Multiagent_Power_Grid

In this project a Market-driven management of distributed, micro storage devices is simulated where
there are three types of agents. The generator agents (GA), load agents (LA) and directory facilitator
agents (DF). The generator agents (GA) advertise their distributed energy resources (DER) to the DF
agent while the load agents (LA) find out the lowest price energy unit with the highest sustainability
rating, that can be paid for the required Kilo-Watt-Hour (KWH) demand. 

![alt-text](https://github.com/msaadsadiq/Multiagent_Power_Grid/blob/master/figures/fig5.png)

In the perspective of multi-agent organization and development, our task is to develop a multi-agent
based distributed power grid. In this distributed Grid there are two parties, people who look for energy
known as 'Load Agents' and the energy providers that sell power to the distributed grid known as the
'Generator Agents'. There can be any number of load agents (LA) and generator agents (GA) at any
given time in the distributed power grid. There will be 5 different types of power, each one bearing
different cost and sustainability ratings, that the Generator Agents will sell to the market. These will be
1. Solar
2. Hydel
3. Wind
4. Fuel cells
5. Nuclear
The Generator agents will be able to add new power sources if they are available to their dispense or
remove a source if it goes out of order. More Load agents and Generator Agents can be added to the
JADE platform at any time to emulate the real life systematic working of the distributed Grid.
Generator Agents (GA) register with Directory Facilitator (DF) agent right after creation and Load
Agents (LA) always update their generator agent list by querying the Directory Facilitator (DF) agent.
As the source or consumer human we specify some criteria to the Load agent such as
1. Type of Power
2. Max price per KWH
3. Max number of generators to query
Load Agents send query to Generator Agents, collect the results and analyses them to decide the best
choice of power to buy. Then initiates byt buying process and finally buys the power with minimum
cost and highest sustainability power rating. 

Agent communication
We start by describing the agents communication in our project. Within Jade, agents can communicate
transparently regardless of whether they live in the same container, in different containers (in the same
or in different hosts) belonging to the same platform or in different platforms. Communication is based
on an asynchronous message passing paradigm. Message format is defined by the ACL language
defined by FIPA, an international organization that issued a set of specifications for agent
interoperability. An ACL Message contains a number of fields including
1. The sender
2. The receiver(s)
3. The communicative act
◦ (also called performative) that represents the intention of the sender of the message.
For instance when an agent sends an IN sends a REQUEST message it wishes the
receiver(s) to perform an action. FIPA defined 22 communicative acts, each one with
a well defined semantics, that ACL gurus assert can cover more than 95% of all
possible situations. Fortunately in 99% of the cases we don't need to care about the
formal semantics behind Communicative acts and we just use them for their intuitive
meaning.
4. The content i.e. the actual information conveyed by the message (the fact the receiver should
become aware of in case of an INFORM message, the action that the receiver is expected to
perform in case of a REQUEST message)
following is a sequence diagram as shown in figure 4, of the agent communication sequence between
the Load Agent, Generator Agent and Directory Facilitator agent. The sequence diagram is described in
the following steps
1. The generator agents first registers itself with the directory facilitator as soon as it is
alive.
2. The DF agent serves as a yellow papers directory for the load agent and provides them
with information about all the generator agents.
3. The load agents doesn't hold knowledge about the generator agents and thus looks for
the DF agent for power providers.
4. The load agents, after having list of all the GAs, will start communicating with generator
agents based on the search criteria
5. After receiving details from all GAs the load agents will decide which vendor to buy
from
6. After deciding, the load agents will contact specific generator agent to make the
purchase. 
