## HILT Early Outline

Q: What does it mean to set up a good machine learning problem?





1:30–5 PM


1:30–2:00
- People introductions & brief HiPSTAS/ARLO introduction
	- What's your problem?

- Point: We're coming from the humanities and we want to be able to use these tools


Get them in the mindset of sounds:

- Talk about why sound is interesting — its characteristics
	- This isn't automatic transcription; it's hard to work with
		- stress: sounds that are identifaable
		- Teaching an ML algorithm is like training a child ...
		- This discussion includes audio quality: recordings on street, cassette dubs, etc.




2:15–30
- Talk about other software: 
	- Open source tools:
		Praat, Sonic Visualizer, ARLO, and the command line programs Aubio and FFmpeg.
	- Talk about Adobe Audition


	- Talk about Marit's article
		- Her NEH grant may be helpful — lots of details on audio tools
		- and Hartwell Francis article on sound in libraries and archives



•   Identify practical ways to design, organize, and present information about an audio collection
•   Use free software tools to process and extract data from audio files
•   Use scripting to determine optimal classification threshold and window function for machine learning data
Discuss how datasets extracted from audio collections may be used in accordance with existing practices for metadata standards, teaching, and research. 




---- 
Tanya: 
- Walk them through a workflow
	and introduce software along the way


These are the 5 things we want to do:

pull up audio
isolate
annotate
collect them together

Maybe get people involved: What do you think  ...

These tools do these different parts of the workflow:
slide with various software tools: Audition, etc. ... linked together in a workflow.

From tags to CSV to ARLO


Talk about metadata too
- Tanya wants to talk about this: integrating into existing metadata schemas


Evaluation methods
cross-validation, maybe larger validation

visualization, smoothing



Discussion:








---- -
-spitballing email:


I agree that just showing off ARLO's potential might not make a great session. It would be great if people could do something with it, especially considering we have four hours to fill. But if ARLO isn't live, I could talk in detail about each step in our workflow and encourage discussion along the way. That might look something like this:

1. the basics of working with audio data (as opposed to text, for instance)
2. an ARLO interface walkthrough
3. explanation of the IBL algorithm vs. SVM and other ML approaches
4. the process involved in creating training sets
5. picking initial comparison parameters
6. overview of specs and configuration options for ARLO's back end
7. optimizing the accuracy of output data
8. cleaning the optimized data
9. running statistical tests between groups
10. interpreting and qualifying final results

Etc., etc. I could probably fill half a day, though the format above might be a bit dry.

Just spitballing: Even if we were ready to let people test drive ARLO on our server, it might take days or weeks to get results back. The only alternative I can think of is to install ARLO on an AWS server with 100 or so virtual cores (pretty cheap) and run it with a smallish dataset. If my envelope math is correct, with 100 or 200 training examples (instead of 5000 for the applause job) and 200 hours of audio (instead of 6000 for PennSound), we could probably get classification data back in around an hour. I know ARLO is set up for parallel processing, though I'm not sure how much work it would be to scale it to that many cores.

The real limiting factor is Tony's time, of course. If you think this kind of setup is remotely feasible, I'll write him and maybe set up a phone call to see what he thinks. If not, I can provide sample data and focus more on optimization and interpretation. Or if you think this is a terrible idea, we can just cancel it.

> I also want to make a weekly, scheduled meeting with you throughout the semester. At this point, my preference would be Wednesday afternoons. I'd like to make it a big block so that we can talk about your work, talk about the project, do some work, etc. I'm thinking something like 1:30-4:30. Does that work for you? Obviously, this counts as part of your 20 hours.

Meeting weekly on Wednesday sounds good. The fall semester begins 8/24, which is a Wednesday. Let's say 1:30–4:30 and you can let me know if another time looks better.
