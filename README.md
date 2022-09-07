# Hadoop-Shakespeare

####  Apache Hadoop: Running a MapReduce Job

####  Using the code we will compile Java files,create a JAR, and run MapReduce jobs.
Working with the Virtual Machine <br>
##### Uploading Files 

> $ hadoop fs <br>
> $ hadoop fs -ls / <br>
> $ hadoop fs -ls /user/training <br>
> $ cd ~/training_materials/developer/data <br>
> $ tar zxvf shakespeare.tar.gz <br>
> $ hadoop fs -put shakespeare /user/training/shakespeare <br>
> $ hadoop fs -ls /user/training <br>
> $ hadoop fs -ls <br>
> $ hadoop fs -mkdir weblog <br>
<img width="410" alt="image" src="https://user-images.githubusercontent.com/23645932/188765701-a8cc4a95-a343-4e43-a17b-d954a3a293b4.png">
<br>

>  $ gunzip -c access_log.gz \  | hadoop fs -put - weblog/access_log <br>
    
> $ hadoop fs -mkdir testlog <br>
> $ gunzip -c access_log.gz | head -n 5000 \
   | hadoop fs -put - testlog/test_access_log <br>
   
 ##### Viewing and Manipulating Files
 
 > $ hadoop fs -ls shakespeare <br>

 > $ hadoop fs -rm shakespeare/glossary <br>
 > $ hadoop fs -cat shakespeare/histories | tail -n 50 <br>
 
<img width="437" alt="image" src="https://user-images.githubusercontent.com/23645932/188765770-b4478168-b201-4602-863b-34e930e5bfb2.png">

<img width="429" alt="image" src="https://user-images.githubusercontent.com/23645932/188765817-56dea0b2-9495-43cd-910c-7da1a104ff9b.png">


> $ hadoop fs -get shakespeare/poems ~/shakepoems.txt! $ less ~/shakepoems.txt <br>
> $ hadoop fs <br>

<img width="371" alt="image" src="https://user-images.githubusercontent.com/23645932/188765832-48619baf-e64f-4c74-bab5-0f9567112fb3.png">

<img width="371" alt="image" src="https://user-images.githubusercontent.com/23645932/188767001-c7e56fc3-75aa-4db6-b4a6-b6e909175605.png">

 #####  Compiling and Submitting a MapReduce Job
 >  $ hadoop classpath <br>
 >  $ javac -classpath ` hadoop classpath ` stubs/*.java <br>
 >  $ jar cvf wc.jar stubs/*.class <br>
 >  $ hadoop jar wc.jar stubs.WordCount \ 
    shakespeare wordcounts 
    <br>
 <img width="468" alt="image" src="https://user-images.githubusercontent.com/23645932/188767307-ac8e7e0b-4051-4a10-b773-43941158e1b1.png">


>  $ hadoop jar wc.jar stubs.WordCount \ shakespeare wordcounts <br>
<img width="461" alt="image" src="https://user-images.githubusercontent.com/23645932/188767407-7bc22609-5e4c-4077-bbfe-4fdad3faaccb.png">

>  $ hadoop fs -ls wordcounts <br>
>  $ hadoop fs -cat wordcounts/part-r-00000 | less <br>
<img width="461" alt="image" src="https://user-images.githubusercontent.com/23645932/188767424-7e788e51-20ea-4b05-953d-362206ec3752.png">
<img width="400" alt="image" src="https://user-images.githubusercontent.com/23645932/188767483-5ec3865e-1008-4392-8add-87395940d06f.png">


>  $ hadoop jar wc.jar stubs.WordCount \ shakespeare/poems pwords <br>
>  $ hadoop fs -rm -r wordcounts pwords <br>

##### Stopping MapReduce Jobs

>  $ hadoop jar wc.jar stubs.WordCount shakespeare \count2 <br>
>  $ mapred job -list <br>
>  $ mapred job -kill jobid <br>
<img width="455" alt="image" src="https://user-images.githubusercontent.com/23645932/188767517-adaadc81-960e-4d16-a725-8458b01a23fd.png">
<img width="442" alt="image" src="https://user-images.githubusercontent.com/23645932/188767529-3622bfdd-a19f-4e4b-b146-e14b4c84604f.png">
<img width="442" alt="image" src="https://user-images.githubusercontent.com/23645932/188767545-f338604f-3c07-4a81-8331-1cd571e7f43b.png">
