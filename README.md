# connect
a stealify component and cli command to create bidirectional connections. Implements the concepts of Tasks as replacement for Processes.

When you before for example did use process pipes to connect one process to a other you do now something similar but not the same. We define the results of Many Tasks as a Effect so Tasks are compare able to pipe processing as the pipe produces a single result we do not assume the same for Tasks
and Tasks can be combined out of Many Tasks.

Comparing Processes to Tasks. Tasks can run and depend on other Tasks they get scheduled and never directly executed as a process would get. Also Tasks can almost never without additional linking components talk to each other if they are not executed from the Same Tasks.

This is archived via a well defined component system designed independ from Posix concepts or *nix Windows concepts. It is a total other method to handle Resource Allocation for binary code invocation. There is no Signal Handling or such a Concept. While Tasks can implement interfaces to abort the task a kernel task always implements abort/interupt capabilitys so there is never a situation for a deadlock the system is designed by default to kill tasks if the resources get over used and gets to a protected state by default to garantee always beeing operate able. 

## Usage

```
npm i -g stealify
# $(npm prefix -g)/bin/stealify
# creates a temp profile and use its return value as 
stealify connect create id_or_name_or_<path_to_app>
stealify connect run id_or_name_or_<path_to_app>
# connect
stealify run id_or_name_<path_to_app> id_or_name_<path_to_app>
```

connect Is like a programatical docker attach so it executed the secund app inside the first it can also be compared to running to containers on the same network or connect 2 apps via stdio stream pipes. 
