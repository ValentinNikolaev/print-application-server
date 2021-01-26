# Simple print application server

![visitors](https://visitor-badge.laobi.icu/badge?page_id=ValentinNikolaev.print-application-server)

 Simple application server that prints a message at a given time in the future

The server has only 1 API:
[GET] "/printMeAt" - which receives two parameters, _time_ and _message_, and writes that message to the server console at the given time.
Since we want the server to be able to withstand restarts it uses Redis to persist the messages, and the time they should be sent at.
There might be more than one server running behind a load balancer.
In case the server was down when a message should have been printed, it should print it out when going back online.

The focus of the exercise is:
- only native php/go api (apart from redis, for it can be used any extension/library)
- server should start from cli and print messages to stdout
- the efficient use of Redis and its data types
- messages should not be lost
- the same message should be printed only once
- message order should not be changed
- should be scalable
- docker
- tests
- only redis

