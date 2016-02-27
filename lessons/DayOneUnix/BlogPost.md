We ran a [genomics workshop](http://qingpeng.github.io/2016-02-22-isu/) this past week at Iowa State University. We used a mix of the regular and cloud [genomics materials](http://www.datacarpentry.org/lessons/). Here's a rundown of what worked and what didn't. The instructors were Qingpeng Zhang, Josh Herr, Jinlyung Choi and myself.

##What Worked

+ Instructors running through the instructional materials before the workshop: Jin and I both logged into EC2 instances early and ran through the shell materials the day before. Josh ran through his R materials the day before, as well. There have been relatively few workshops so far, and people have really tailored their materials for their communities. Because of this specialization, it is especially important for instructors to actually put their fingers on the keyboards and work it out in advance.

+ Amazon EC2 instances: These instances come pre-loaded with the data. For the large genomic datasets, and unreliable room WiFi, this made everything run very smoothly. There are some aspects of how to start the instances that are a little opaque for new instructors. We've put some notes [here](https://github.com/wrightaprilm/2016-02-22-isu/blob/gh-pages/lessons/DayOneUnix/InstructorNotes.md).

##What Didn't

+ The Git lesson went really smoothly, but I think the narrative needs to be reworked a little bit for DC learners. Git follows pretty naturally in a SC workshop - "How many of you had something working yesterday, and deleted a piece, or made a bad change?" With the smaller amount of scripting in DC workshops, we need to think a little more about how to sell that. 