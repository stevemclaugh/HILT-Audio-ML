## ASIST

- General introduction:
	- Q: What does it mean to set up a good machine learning problem?
	- How to pick a productive query for audio
	- the kinds of sounds you might you look for

- Executing a project:

	1. build corpus
	2. annotating corpus
	3. Designing a ML query
	4. Running query
	5. Validating



## My rough outline for the ASIST workshop:

#### Overview

- Introductions among crowd & brief HiPSTAS/ARLO background
	- What's the problem you're trying to solve?
	- What are you searching for?
	- What don't you know about what's in your archive?

- Point: We're coming from the humanities and we want to be able to use these tools ourselves.

- Get them in the audio mindset
	- Talk about why sound is interesting and why it's difficult to work with
	- [good spot to pass around 3D-printed spectral data]()
	- This isn't automatic transcription; it's messy and opaque compared to working with text.
		- This discussion includes audio quality: recordings on street, cassette dubs, etc.
		- Don't trust the performance measures you see in machine learning papers; they're typically using internally consistent corpora.
	- Stress: What makes a particular sound identifiable?
		- Teaching an ML algorithm is like training a child.

#### Tools and Standards

- Talk about other software: 
	- Open source tools: Praat, Sonic Visualizer, ARLO, FFmpeg, Pydub, Aubio, etc.

	- Talk about Marit's article.
		- Her NEH grant may be helpful — lots of details on audio tools
			- Hartwell Francis et al. article on sound in libraries and archives


	- Slide with various software tools and how they connect
		- Talk about Adobe Audition vs. Audacity and what role they might play in your workflow.
		- Use free software when possible

	- Identify practical ways to design, organize, and present information about an audio collection

	- Discuss how datasets extracted from audio collections may be used in accordance with existing practices for metadata standards, teaching, and research. 

#### Interactive Demo

- Walk them through a workflow and introduce software along the way.

	- Things we want to cover:
		- examine audio
		- isolate phenomena to search for
		- annotate
		- assemble data and 
		- run classification
		- demonstrate the rigor of your approach 

	- i.e., from tags to CSV to ARLO to CSV + visualization/stats software

	- Evaluation methods
		- cross-validation
		- sampling-based validation on an unknown audio collection
	- Visualization, smoothing
	- Determining optimal classification threshold and window function for machine learning data
	- Don't put too much stock in your accuracy score — an imperfect measure for many classification tasks.
	- Analyzing measurements across a collection
	- When data is noisy, correcting classification instances by hand for analysis in aggregate



## And here's a rough outline I included in our first email about the workshop:

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


