# External Tasks
An `external` task can be defined as a work unit that is run outside of the Dask Cluster, and the output of this task is pushed from its producer in the Dask distributed memory (worker's memory).
A typical use case of those external tasks is the *In Situ Data Analytics* of *High-Performance Simulation*. The running simulation is the external source of the data, and the Dask instance
runs the analytics on the same platform as the simulation. Find more [here](https://www.researchgate.net/publication/371595603_Distributed_Task_based_In_Situ_Data_Analytics_for_High_Performance_Simulations).

The `external` task feature can be used for other use cases where the data may come from external sources:
- Connecting IoT devices to Dask to collect data could be an interesting use case
- Building Digital Twins, for instance, or having several data sources feeding the same Dask workflow is also possible.
- Any other scenarios where we want to submit tasks on data coming from external resources in the future could be built on this feature. 

# Requirements 
The forked version of Dask [Distributed](https://github.com/GueroudjiAmal/distributed). 
# Content
Here are two Notebooks. 

**Client01:**
 - Creates a Local Cluster
 - Shows and demonstrates the need for the `external` task feature.
   
**Client02**
 - Is considered an external source of the data

# Scenario
1. Run steps in Client01
2. Once you submit tasks on the `external` (`deisa`) data, and get blocked waiting for the result, Goto Client02
3. Make sure to connect the `external_client` to the same Scheduler (copy/paste the address you get from Client01)
4. Run the steps in Client02, that represent you external source
5. Come back to Client01, where you will find the results of your computation

# Good luck!
