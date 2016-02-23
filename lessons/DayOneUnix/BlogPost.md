We ran a [genomics workshop](http://qingpeng.github.io/2016-02-22-isu/) this past week at Iowa State University. We used a mix of the regular and cloud [genomics materials](http://www.datacarpentry.org/lessons/). Here's a rundown of what worked and what didn't. The instructors were Qingpeng Zhang, Josh Herr, Jinlyung Choi and myself.

##What Worked

+ Instructors running through the instructional materials before the workshop: Jin and I both logged into EC2 instances early and ran through the shell materials the day before. Josh ran through his R materials the day before, as well. There have been relatively few workshops so far, and people have really tailored their materials for their communities. Because of this specialization, it is especially important for instructors to actually put their fingers on the keyboards and work it out in advance.

+ Amazon EC2 instances: These instances come pre-loaded with the data. For the large genomic datasets, and unreliable room WiFi, this made everything run very smoothly. There are some aspects of how to start the instances that are a little opaque for new instructors. We've put some notes [here](https://github.com/wrightaprilm/2016-02-22-isu/blob/gh-pages/lessons/DayOneUnix/InstructorNotes.md).

##What Didn't

+ There was a lost-data issue last year, so Jin tried to copy data instead of move data this time. But it takes more than 20 min which hold workshop for a while. Also, running 6 file for FastQC and Trimmomatic takes long time. Specially automation tried to show run shell script to run FastQC, maybe it is better idea only use 2 or 3 files instead of 6. 

