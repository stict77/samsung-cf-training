### Table of contents

1.	Introduction
2.	Viewing events
3.	Monitoring logs
4.	Application files

### Introduction

Ok, now we have an application deployed and two instances of that application running side by side, load balanced by the Cloud Foundry Router.
However, how do I see what is going on with the application?
How do I see the logs?
The Cloud Foundry CLI provides a couple of commands to satisfy these needs.
### Viewing events

An *event* is something that happens to your application at the deployment level. It is different from an internal application log. Application logs are generated by the application. An event log is generated by Cloud Foundry itself. All actions suffered by the application are recorded and can later be audited:

```exec
cf events MY_APP
```

As you can see, all these events are related to the operations performed by Cloud Foundry and NOT what is going on *inside* the application.
### Viewing logs

Logs are very easy to view:

```exec
cf logs MY_APP
```

While you are tailing the logs with the previous command, go to your browser and navigate to your application URL. Then, reload the page a couple of times.

> **Note**: Do not worry about the `ERR` messages. We will be fixing them  later as part of this course.

You can also dump the logs to a file instead of tailing, using the `--recent` flag.

```exec
cf logs MY_APP --recent > my-logs.txt
```