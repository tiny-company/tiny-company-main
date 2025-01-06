# Interview for admin system position

Technical interview presentation (around 60 minutes) :
    - part 1 : company and job presentation (5-10 minutes)
    - part 2 : candidate presentation (5-10 minutes)
    - part 3 : technical interview (10-20 minutes)
    - part 4 : personnality and experiences interview (5-10 minutes)
    - Part 5 : candidate questions

## Part 1 : Company, Service and job presentation (5-10 minutes)

NewCo AI, previously Webdrone : IT service provider company oriented in cybersecurity (OSINT, anti-piracy)

### Service presentation

- Main service :
    - manage by
    - members
    - missions

- [Service Valors](https://asana.com/resources/company-values-examples) :
    - rigour
    - teamplay, communication (sharing)
    - passionate (seek to improve)
    - proactive

### job presentation

- Technology :
    - Database
    - Web framework
    - Devops :
        - git
        - ansible
        - terraform
        - jenkins
        - github action
        - packer
    - System :
        - proxmox
        - docker
        - kubernetes
    - Monitoring :
        - Prometheus
        - Grafana

- Missions :
    - linux server mgmt
    - windows server mgmt
    - scripting (python, bash, powershell)
    - monitoring
    - logging
    - MCO / debugging / support
    - security
    - automation (devops, CICD)
    - Documentation writing

## Part 2 : Candidate presentation (5-10 minutes)

Presentation expectation :
- Education
- Experience
- Skills

## Part 3 : Technical Questions (10-20 minutes)

### Low level (entry) questions

> Note : An invalid answer on any of these question reject candidate.

- What is OSI model ? (model that describe communication between systems, divided into 7 layers)

- Do you know docker ? (no is a rejection)
    - define a dockerfile (incorrect response is a rejection)
    - define an docker image (incorrect response is a rejection)
    - define a docker registry, like dockerhub (incorrect response is a rejection)
    - do you know docker-compose, what is it purpose ? (no is a rejection)

- Have you ever work on linux ?
    - how to show linux command history on linux ? (history)
    - how to list file in linux ? how to have file size ? (ls -lh)
    - Give 2 methods to transfer file between 2 server on linux (scp, ftp, rsync)
    - How to list iptables rules on linux ? (iptables -L)
    - How to filter linux command output (using pipe and awk, grep)

### Medium level questions

> Note : these are more advanced question in order to define candidate technical level, invalid response are not penalizing. Greater score (good answer) mean better level.

- Have you ever work with DNS ?
    - Give 2 record type and explain them (A, AAA, SOA, TXT, MX, ...) : /2
    - Give 2 DNS server types (Recursor, authoritative, TLD, Root) : /2

- How do you define your level on linux ?
    - how to get space occupied on a disk ? (df -h) : /1
    - How to list user existing on a linux server ? (cat /etc/passwd) : /1
    - how to list disk on a linux server (lsblk or fdisk -l) : /1

- How are you working in team ?
    - Give example of previous experiences
    - How are you sharing knowledge between team member ? : /5
    - Are you use to procedure or documentation ? Have you ever right some ? : /4

- Have you ever work with virtualization system ?
    - What kind of hypervisor is docker ? (trap question, it is not an hypervisor, it is a implementation of container technology which are based on kernel call, cgroup and namespaces) : /5
    - Give 2 container technology and 2 virtualization technology ( docker, podamn, lxc and kvm, qemu, XEN, vmware, proxmox, virtualbox, HyperV) : /4

- Have you ever work with devops tools (ansible, terraform, ...) ?
    - What is CICD ? give framework example : /1
    - Give previous implementation example of devops project (if any) : /1

- Have you ever work on a security project or tasks ?
    - what is hardening ? give implementation example : /1
    - Give 1 docker security best practice : /1
    - Is docker rootless or rootful by default ? : /1

total score : /30

### High level questions

> Note : These questions define the profile of an efficient candidat (is he an architect, a dev, basic admin, oriented to security)

- What is LVM on linux storage, what is the purpose of it ?
- Do you know sysbox ?
- Have you ever work with kubernetes ?
- What is your preferred programmation language ?
- Have you ever develop an application, for what purpose or project ?

## Part 3 : Personnality questions (5-10 minutes)

> Note : The goal is to define what is the candidat psychological profile and if he match expectations of the job.

- Soft skills questions (stress, team work, organization, logic ...):
    - **stress management** : How do you manage stress situation / conflict  ?  Give previous situation example.
    - **team play** : What are you looking for by integrating a team ? (technical, friendliness, project)
    - **time management** : How are you organizing your work time ? Describe a typical work day.
    - **autonomy** : How do you manage a situation where you have to learn a new technology ?
    - What are your 3 mandatory valors in your work (communication, rigour, exchange, passion, respect ...)

- passion question :
    - Have you any personal projects ?
    - Is work also a passion ? Where do you define the limit between these two ?
    - What are your expectation on this job ? (salary, technical project, team play, ...)

## Part 4 : Candidate question

## Sources :

- [manage interview](https://www.youtube.com/watch?v=qi4w1euJo9A)