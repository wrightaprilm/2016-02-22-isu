# Move data onto your instance

## Moving data is simple
(but not always easy!)


You've already been working on the cloud instance and moving data from external servers onto your instance as well as moving data around your instance.

Remember, when you downloaded the *E. coli* reference genome 

```bash
$ wget ftp://bacteria.ensemble....
```

In this case, you are using a command line tool, *wget*, to download content from a webserver.  This command supports downloading files from FTP and HTTP(s).  The tool *wget* also supports recursive download (with the parameter *-r*), allowing you to download content from a directory or folder.  For your information, there are other command line tools that can also be used to download data (e.g., *curl*), but *wget* should serve you well for this lesson and bioinformatic analysis.

##Exercises 

### Moving files between your laptop and your instance

These directions are platform specific so please follow the instructions for your system

##Uploading Data to your Virtual Machine

#### PC

Using PC, we recommend you use the *PSCP* program. This program is from the same suite of tools as the putty program we have been using to connect. 

1. If you haven't done so, download pscp from [http://the.earth.li/~sgtatham/putty/latest/x86/pscp.exe](http://the.earth.li/~sgtatham/putty/latest/x86/pscp.exe)
2. Make sure the *PSCP* program is somewhere you know on your computer. In this case, your Downloads folder is appropriate. 
3. Open the windows [PowerShell](https://en.wikipedia.org/wiki/Windows_PowerShell); go to your start menu/search enter the term **'cmd'**; you will be able to start the shell (the shell should start from C:\Users\your-pc-username>). 
4.Change to the download directory
```
> cd Downloads
```
5. locate a file on your computer that you wish to upload (be sure you know the path). Then upload it to your remote machine (**you will need to know your ip address, and login credentials**). You will be prompted to enter a password, and then your upload will begin. **(make sure you use substitute 'your-pc-username' for your actual pc username)**

   ```
C:\User\your-pc-username\Downloads> pscp.exe local_file.txt dcuser@ip.address:/home/dcuser/
```

#### MAC/Linux

1. Open the terminal and use the *scp* command to upload a file (e.g. local_file.txt) to the dcuser home directory:

   ```bash
$  scp local_file.txt dcuser@ip.address:/home/dcuser/
```
##Downloading Data from your Virtual Machine

Let's download a zipped file from our remote machine.  You should have a fastqc report in ~/dc_workshop/results/fastqc_untrimmed_reads/SRR097977_fastqc.zip

**Tip:** If you are looking for another (or any really) zip file in your home directory to use instead try
   ```bash
$ find ~ -name *.zip
```

#### PC

1. Follow the instructions in the Upload section to download (if needed) and access the *PSCP* program (steps 1-3)
2. Download the zipped fastqc report using the following command **(make sure you use substitute 'your-pc-username' for your actual pc username and dcuser@ ip.address with your remote login credentials)**

   ```
C:\User\your-pc-username\Downloads> pscp.exe dcuser@ip.address:/home/dcuser/dc_workshop/results/fastqc_untrimmed_reads/SRR097977_fastqc.zip C:\User\your-pc-username\Downloads\datacarpentry
```
#### Mac/Linux

1. Download the fastqc report in ~/dc_workshop/results/fastqc_untrimmed_reads/SRR097977_fastqc.zip to your home ~/Dowload directory using the following command **(make sure you use substitute dcuser@ ip.address with your remote login credentials)**:

   ```bash
$ scp dcuser@ip.address:/home/dcuser/dc_workshop/results/fastqc_untrimmed_reads/SRR097977_fastqc.zip ~/Downloads/datacarpentry
```

##Updating Data Stores with RSync

Downloading big data is an intense task. When we're running experiments on a remote machine, we may continue to accumulate results after we initially downloaded them. In this case, we don't want to download a whole results directory at once - we just want the new stuff.

Enter RSync. RSync stands for remote sync. As you may have guessed, we can use RSync to make sure the files on our personal machine are the same as those on a remote machine. Once we have a working copy of files locally, RSync simply looks for the differences between our local copy, and the remote copy, or vice versa. Because RSync downloads _only the differences_, this is much more efficient than downloading the all of your files again to get the new ones.

Let's begin by making an edit to the remote copy of our files. On your EC2 instance, enter the fastqc_untrimmed_reads directory. We will now make and add a README file explaining what these data are:

```
nano README.md
```

Enter a short explantation of what is contained in this directory. 

Now, we will sync the file between the machines. On your personal machine:

```
rsync -zvh dcuser@ip.address:/home/dcuser/dc_workshop/results/fastqc_untrimmed_reads/ ~/Downloads/datacarpentry
```

Some of this syntax should be familiar, some not. Have a look at the below commands, and discuss with a neighbor what you think has happened.

|Command| Meaning|
|----|--------|
| v | verbose |
|r | recursive |
|a | archive - preserve data/time stamps |
| h | human readable - translate numbers to human-readable formats |


RSync, by default, will not recursively copy subdirectories of your main directory. But, it does have a flag to allow us to do this. Let's put what we learned earlier to use and create a results directory on our remote machine.

```
mkdir output
cd output
mkdir trimmed_reads statistics notes
```

Now, on our personal machines, we can sync these directories like so:

```
rsync -zvhr dcuser@ip.address:/home/dcuser/dc_workshop/results/fastqc_untrimmed_reads/ ~/Downloads/datacarpentry
```

We should now have our output directory, and its three subdirectories in our downloads folder.

### A few tips and tricks

*–progress* flag:

```
rsync -zvhr -progress --max-size='200k'dcuser@ip.address:/home/dcuser/dc_workshop/results/fastqc_untrimmed_reads/ ~/Downloads/datacarpentry

``` 

As you may have guessed, this flag prints the per-file transfer progress.

*--max-size=* flag

```
rsync -zvhr -progress --max-size='50k' dcuser@ip.address:/home/dcuser/dc_workshop/results/fastqc_untrimmed_reads/ ~/Downloads/datacarpentry

``` 
This flag sets a maximum file size: if you don't want to download a ton of 5G files to your computer, you can tell RSync that here.

*--dry-run* flag
```
rsync -zvhr -progress --max-size='50k' --dry-run dcuser@ip.address:/home/dcuser/dc_workshop/results/fastqc_untrimmed_reads/ ~/Downloads/datacarpentry

``` 

This prints to the screen what files will be moved. Handy for checking that your max size command worked!

##Challenge#

I don't know!


