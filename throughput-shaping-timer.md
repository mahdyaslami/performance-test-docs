## Throughput Shaping Timer

Long time JMeter users had to try their tests on and on, finding exact number of threads and timer delays that produce desired number of requests per second (RPS) to server. This is "closed workload" approach, and it has major drawbacks (see here why). And if you changed load generator machine or server response time - you were doomed to do all this stuff again.

Here's the solution - Throughput Shaping Timer! Now you can just set schedule of RPS easily, observing it on preview graph. This schedule can be as various as you want. It gives you the happiness of the "open workload" approach.

## Few Important Notes

JMeter threads of Thread Groups in scope of the Element will be stopped when RPS schedule finishes.
provide enough working threads for your RPS, JMeter timers can only delay threads (and limit RPS). You may pair this plugin with Concurrency Thread Group using Schedule Feedback Function to dynamically maintain thread count required to achieve target RPS.
if you're using versions of JMeter lower than 3.3 and if you have RPS that lower at the end of test, make threads to lower also. Оtherwise you'll have a spike in last second.
avoid using zero RPS value as start of test, this produce spike also
avoid zero RPS during the test, this may lead to nasty effects

## How Many Threads I Need To Produce Desired RPS?

Threads pool size can be calculated like `RPS * <max response time> / 1000`. The more rate desired the more threads you will need. The more response time service have the more threads you will need.

For example, if your service response time may be 2.5sec and target rps is 1230, you have to have `1230 * 2500 / 1000 = 3075 threads`.

It is better to have some threads overhead to handle unexpected response time spikes. But beware of too much overhead, it will lead to "final spike".
