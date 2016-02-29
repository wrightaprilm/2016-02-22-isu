We ran a [genomics workshop](http://qingpeng.github.io/2016-02-22-isu/) this past week at Iowa State University. We used a mix of the regular and cloud [genomics materials](http://www.datacarpentry.org/lessons/). Here's a rundown of what worked and what didn't. The instructors were Qingpeng Zhang, Josh Herr, Jinlyung Choi and myself.

#### April -- just adding my comments, feel free to incorporate, rework, delete, disregard, etc.  Putting my comments with 4 hashes.

##What Worked

+ Instructors running through the instructional materials before the workshop: Jin and I both logged into EC2 instances early and ran through the shell materials the day before. Josh ran through his R materials the day before, as well. There have been relatively few workshops so far, and people have really tailored their materials for their communities. Because of this specialization, it is especially important for instructors to actually put their fingers on the keyboards and work it out in advance.

#### I was pretty amazed at how well all of this worked out -- a little bit of luck on our part as how things came together, but I think it was a testament to the quality of the instructors in the room to work with the material on the fly and make it work and comprehensible for the workshop participants.

+ Amazon EC2 instances: These instances come pre-loaded with the data. For the large genomic datasets, and unreliable room WiFi, this made everything run very smoothly. There are some aspects of how to start the instances that are a little opaque for new instructors. We've put some notes [here](https://github.com/wrightaprilm/2016-02-22-isu/blob/gh-pages/lessons/DayOneUnix/InstructorNotes.md).

#### This worked really well and we had no problems I have encountered before with two people trying to log into the same instance or people.  
+ [Qingpeng] I used the git-novice lesson materils from SWC and it went well I think. Basically I focused on the task of writing a manuscript and working with other collaborators. Most of the topics are covered except 6-Ignoring Things, and 10-12, since installing git on their own computers took some extra minutes. It was nice that Josh and I could demonstrate how collaboration on github works on the fly. It is novice lesson, so branch was not introduced officially but we talked about some deeper stuffs like "pull request" briefly to give the students general idea about how to work on a large project with many more people. In conclusion, the SWC git-novice materials works great for a morning session. There are some glitches in the SWC git-novice lesson materials that needs to be checked and I will submit pull/issue requests accordingly. 

+ [Qingpeng] I just reorganized the lesson directory on the workshop repo. https://github.com/qingpeng/2016-02-22-isu/tree/gh-pages/lessons
April and Jin made great efforts in preparing/organizing the lesson materials. 
Previously they are kind of scattered in different places. Now they are integrated as a whole and ready to go. I think both materials are worthy of further review by DC lesson maintainers.
https://github.com/qingpeng/2016-02-22-isu/tree/gh-pages/lessons/DayOneUnix_by_April
(April taught the sections except 05-UNIXShell 06-Automation.md 06.5ParallelAutomation.md in the morning.)
https://github.com/qingpeng/2016-02-22-isu/tree/gh-pages/lessons/Day1Afternoon-Shell_by_Jin
(Jin taught the shell/automation stuffs in the afternoon.)
[You are all welcome to edit this section if there is any inaccuracy here.]



##What Didn't

+ [AMW] The Git lesson went really smoothly, but I think the narrative needs to be reworked a little bit for DC learners. Git follows pretty naturally in a SC workshop - "How many of you had something working yesterday, and deleted a piece, or made a bad change?" With the smaller amount of scripting in DC workshops, we need to think a little more about how to sell that. 

#### I agree here -- git works well when the focus is general programming or automation, but the pertinence was hazy for a lot of people here.  I think hammering the "data analysis into manuscript" argument of why you want to learn git is the way to go here.

+ [Jin] There was a lost-data issue last year, so Jin tried to copy data instead of move data this time. But it takes more than 20 min which hold workshop for a while. Also, running 6 file for FastQC and Trimmomatic takes long time. Specially automation tried to show run shell script to run FastQC, maybe it is better idea only use 2 or 3 files instead of 6.
+ [Qingpeng] I agree. Actually the 6 files are in the hidden folder. In the dc_sample_data/untrimmed_fastq/ folder in that AWS image, there are only 2 files. I guess the maintainer may have been aware of this problem.
+ [Qingpeng] In the beginning I was planning to run the git stuffs on Amazon EC2 machine. But it was my bad that I didn't realized git was not preinstalled in that image. (Git was not included as core lessons for DC. So this should not be surprising.) I decided to help the students to install Git on their personal computer. This took about 20 minutes but finally it is not bad for them to have git in their own computer so they can start using it for their project/writing right away.

#### I think we (Data Carpentry in general) should slim down the data sets (or have multiple versions) so that students aren't stuck sitting running analyses.  Perhaps a solution is also to plan the material so when something is going to take a while and different topic or coffee or lunch break can be scheduled.  This takes some more planning and rigid scheduling ahead of time.  It's sometimes nice to improvise when people have questions or the room is of a specific discipline.

+ [Josh] The R material worked fairly well (especially concerning the fact I am not an R wizard or was familiar with the material).  I tried to work some extra material into the tutorial, which I will add, which I thinked worked to an extent, but some people had a hard time following when I deviated from the material.  I would like to incorporate some more graphing examples with genomics based R packages to connect to the EC2 portion more specifically.  The material now is basically: "Ok, here's what we sorted and analyzed, but you can make a bar chart of it now." The R material might go over better if it was more connected to the previous examples and had a more of a genomics focus.

