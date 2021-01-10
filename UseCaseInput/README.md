# Use Case Description

This work uses two artificially created scenarios that are generally inspired by industrial use cases from different sectors. Use case design follows the goal of representing the assembly related characteristics of different industries. Key characteristics include the number of processes, the number of products, and the average processing time. Both use cases focus on large-scale products. The first use case is inspired by automotive assembly lines. The second use case represents typical aerospace structure assembly processes. .

Each use case specifies a production program, process durations for each product, process to station assignments (capabilities), distances, resource to station assignments, and further information such as the maximum number of stations and information related to product transport. During use case specification, the yearly production volume and the resulting external takt time  were taken into consideration to determine the number of simultaneously active stations. The external takt time results from an estimation based on yearly production. The number of simultaneously active stations is determined through estimation using. As this provides an idealised number of stations, the real required number of stations is often higher. For the presented use cases, these have been iterated using the assessment model to arrive at the numbers indicated in the following subsections. Note that while the presented use cases aim to mimic realistic cases, they do not represent optimised systems, i.e. the process to station assignment or maximum WIP may have optimisation potential.  

Beside the key characteristics of the use cases, different design paradigms of LMAS design need to be considered. A key design decision of LMAS is the degree of redundancy of process to station assignment, i.e. how many different stations can provide the same process, thereby influencing the number of topology conflicts. 
Redundancy is determined by the mean value of the number of processes assigned to each station configuration.  The number of topology conflicts is the number of processes to which there is more than one station available. To take this key design decision into account for the validation, two different scenarios for each use case are defined. These scenarios are referred to as "A" and "B". Scenario A is characterised by a low redundancy (<1.5), whereas scenario B has a higher redundancy (>=3.0). The production program and the processing times per product remain identical for both scenarios to a use case. In total four different scenarios are considered for all further investigations, covering a vast range of possible design decisions and applications.

## Use Case 1: Automotive

The first use case is inspired by automotive assembly with process and cycle times in the range of minutes, a high number of processes, and multiple product variants with different process durations and sequences. Examples are the low to medium volume assembly of cars or trucks either during final assembly or in the body shop. The use case considers five different product types and a total of 30 processes. Assuming 220 workdays per year, three shifts, and eight hours per shift at a utilisation rate of 90% an external takt time of 420.1 and approximately 12 stations in simultaneous operation are required. The standard deviation of the total processing time for all products is at 8 % of the average value.

Two different assembly scenarios are provided. Scenario 1A has a large number of station configurations and a low redundancy index (station configurations that handle one or two processes) to mimic typical assembly lines. Scenario 1B assumes a high degree of universality; the station configurations can perform at least three different processes. Some of these station configurations are redundantly available. 
![](UC1.png)
## Use Case 2: Aerospace

The second use case mimics the characteristics of the assembly of aircraft structural components such as fuselage, wing elements, or similar large scale mechanical structures made from several thousands of parts and repeated fastening processes. The similarity of the processes allows for a high degree of resource sharing. The processing times are in the order of hours. The annual production rate is relatively low compared to the automotive use case. The deviation of total processing time is higher than for use case 1 with a standard deviation of 31 % of the average value.

The use case considers eight different product types and 15 processes. Assuming 220 workdays, two shifts, and eight hours per shift at a utilisation rate of 90 %, meeting the desired production rate results in an external takt time of 2.5h, requiring eight stations in simultaneous operation. Similar to use case 1, two scenarios are considered. Design 2A uses mostly dedicated station configurations which are capable of executing one or two processes. Design 2B assumes highly universal stations so that some station configurations are available multiple times to provide the required production capacity. 
![](UC2.png)

## Structure of Input Information

* Matrix D: distanceBetweenStations.csv
* Matrix T(P,PC):jobOperationMatrix.csv
* Vector f(P): productionProgram.csv
* Matrix R(R,SC):resourceStation.csv
* Matrix C(SC,PC):stationOperationMatrix.csv