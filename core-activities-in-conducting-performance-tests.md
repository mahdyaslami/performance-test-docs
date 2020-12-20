## Core activities in conducting performance tests:

- **Identifying acceptance criteria:** What is the acceptable performance of the
various modules of the application under load? Specifically, we need to identify
the response time, throughput, and resource utilization goals and constraints.
How long should the end user wait before rendering a particular page? How long
should the user wait to perform an operation? Response time is usually a user
concern, throughput a business concern, and resource utilization a system
concern. As such, response time, throughput, and resource utilization are key
aspects of performance testing. Acceptance criteria are usually driven by
stakeholders, and it is important to continuously involve them as the testing
progresses, as the criteria may need to be revised.

- **Identifying the test environment:** Becoming familiar with the physical test and
production environments is crucial for a successful test run. Knowing things such
as the hardware, software, and network configurations of the environment helps
derive an effective test plan and identify testing challenges from the outset. In
most cases, these will be revisited and/or revised during the testing cycle.

- **Planning and designing tests:** Know the usage pattern of the application
(if any), and come up with realistic usage scenarios, including variability among
the various scenarios. For example, if the application in question has a user
registration module, how many users typically register for an account in a day?
Do those registrations happen all at once, at the same time, or are they spaced
out? How many people frequent the landing page of the application within an
hour? Questions such as these help put things in perspective and design
variations in the test plan. Having said that, there may be times when the
application under test is new, and so, no usage pattern has been formed yet. At
such times, stakeholders should be consulted to understand their business
process and come up with as close to a realistic test plan as possible.

- **Preparing the test environment:** Configure the test environment, tools, and
resources necessary to conduct the planned test scenarios. It is important to
ensure that the test environment is instrumented for resource monitoring to help
analyze results more efficiently. Depending on the company, a separate team
might be responsible for setting up the test tools, while another team may be
responsible for configuring other aspects, such as resource monitoring. In other
organizations, a single team may be responsible for setting up all aspects.

- **Preparing the test plan:** Using a test tool, record the planned test scenarios. There
are numerous testing tools available, both free and commercial, that do the job
quite well, with each having their pros and cons.

- **Running the tests:** Once recorded, execute the test plans under light load and
verify the correctness of the test scripts and output results. In cases where test or
input data is fed into the scripts to simulate more realistic data (more on this in
subsequent chapters), also validate the test data. Another aspect to pay careful
attention to during test plan execution is the server logs. This can be achieved
through the resource monitoring agents set up to monitor the servers. It is
paramount to watch for warnings and errors. A high rate of errors, for example,
can be an indication that something is wrong with the test scripts, application
under test, system resource, or a combination of all these.

- **Analyzing results, report, and retest:** Examine the results of each successive run
and identify areas of bottleneck that need to be addressed. These can be related to
system, database, or application. System-related bottlenecks may lead to
infrastructure changes, such as increasing the memory available to the
application, reducing CPU consumption, increasing or decreasing thread pool
sizes, revising database pool sizes, and reconfiguring network settings. 
Databaserelated bottlenecks may lead to analyzing database I/O operations, top queries
from the application under test, profiling SQL queries, introducing additional
indexes, running statistics gathering, changing table page sizes and locks, and a
lot more. Finally, application-related changes might lead to activities such as
refactoring application components, and reducing application memory
consumption and database round trips. Once the identified bottlenecks are
addressed, the test(s) should then be rerun and compared with the previous runs.
To help better track what change or group of changes resolved a particular
bottleneck, it is vital that changes are applied in an orderly fashion, preferably
one at a time. In other words, once a change is applied, the same test plan is
executed and the results are compared to a previous run to check whether the
change made had any improved or worsened effect on the results. This process is
repeated until the performance goals of the project have been met.


The performance testing core activities are displayed as follows:

![the-performance-testing-core-activities](the-performance-testing-core-activities.png)

## Baselines

A **Baseline** is the process of capturing performance metric data for the sole purpose of
evaluating the efficacy of successive changes to the system or application. It is important
that all characteristics and configurations, except those specifically being varied for
comparison, remain the same in order to make effective comparisons as to which change (or
series of changes) is driving results toward the targeted goal. Armed with such baseline
results, subsequent changes can be made to the system configuration or application and
testing results can be compared to see whether such changes were relevant or not. Some
considerations when generating baselines include the following:

- They are application-specific
- They can be created for systems, applications, or modules
- They are metrics/results
- They should not be over generalized
- They evolve and may need to be redefined from time to time
- They act as a shared frame of reference
- They are reusable
- They help identify changes in performance

## Load and stress testing

**Load testing** is the process of putting demand on a system and measuring its response, that
is, determining how much volume the system can handle. **Stress testing** is the process of
subjecting the system to unusually high loads, far beyond its normal usage pattern, to
determine its responsiveness. These are different from performance testing, whose sole
purpose is to determine the response and effectiveness of a system, that is, how fast the
system is. Since load ultimately affects how a system responds, performance testing is
mostly done in conjunction with stress testing.

## NOTES

### Ramp-up Time

> It is important that the ramp-up be long enough to avoid too large  a workload
> at the start, of a test as this can often lead to network saturation and
> invalidate  test results. If the intention is to have 9 number of users active
> in the system, it is better to  ramp-up slowly and increase the number of
> iterations. A final option the configuration  provides is the scheduler. This
> allows the setting of the start and end time of a test  execution. For example,
> you can kick-off a test to run during off-peak hours for exactly 1  hour.

### Listeners

> Some listeners, such as Assertion Results, Comparison Assertion
> Visualizer, Distribution Graph, Graph Results, Spline Visualizer, and View
> Results in tree, are memory and CPU intensive and should not be used
> during actual test runs. They are okay to be used for debugging and
> functional testing.

