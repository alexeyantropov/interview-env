# interview-env

An environment for system administrators and SREs interviews.

# What's it?

The interviewing for jobs like system administrator or SRE sometimes requires some interaction between a candidate and an interviewer. The task is completely solved for a programming interview. You can use online platforms (codeshare.io e.g.) for screen/code sharing or the candidate may share their screen with IDE via Zoom or Google Meet.

But what should we do with the interview tasks about software/databases/system/network/etc troubleshooting and debugging? When we need tools like strace/proc/netstat/tcpdump/nsenter or console database client. Sure we can use imagination :) to talk and reason about situations and problems. 

I think the better way is using a similar service where the candidate may connect via SSH and get a set of tasks for online solving by their hands. The interviewers could see the candidate's terminal (w/o screen sharing) and may give some advice or may interact with the remote session.

# What a solution I see for the problem

(There're my thoughts and a small technical task. May be like the White Paper in FAANG companies).

The solution (or the product) should be maximum portable and independent from the environment. What follows from this? I can't use VMs images because the images depend on cloud providers. And I can use only open software and services (w/o the internals from my company e.g.)
Good idea is using Docker and Docker Compose. But I need privileged containers for tools like strace (the ptrace syscall) or ip (a network namespace creation). In general it isn't a problem.
