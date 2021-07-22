
# Preparing your manuscripts the FMDL way

Read the following in detail to get started.

## Using this repo

1. Clone this repo using command line.

		git clone git@github.com:FMDLab/manuscript.git
		
1. Read through the contents if you need to. Generally, you will want to go through the included README (this file) and the PDF files in detail the first time.
1. Rename the folder created by git clone to reflect the contents of your manuscript. If it is on measuring TCR for VO2 based photoresistors, it could be named VO2TCR. Call this DOCNAME.
1. Rename IITD_manuscript.tex to DOCNAME.tex.
1. Delete all other files, including .git. 
1. Go to GitHub via the web interface, and create a new private repo with the name DOCNAME. If it is not available, then you will need to change DOCNAME for the folder and disk. Maybe VO2TCRPhotoresistor in the above example. Don't use a dumb name like VO2TCR1 (does 1 have anything to do with the contents of the manuscript?) or VO2TCRAPL (Does APL have anything to do with the contents of the manuscript?). The name has to reflect the contents.
1. Go to settings for the repo and add your email address and mine to the notifications.
1. Come back to your DOCNAME folder on your machine.
1. Initialize the repo and set the branch:

		git init
		git branch -M main
		
1. Do the initial commit:

		git commit -m "Initial commit. Blank manuscript"
		
1. Tell it where the remote repo lives:

		git remote add origin git@github.com:FMDLab/DOCNAME.git
		
1. Push to the main branch to remote:

		git push origin -u main

1. Go to GitHub web interface and confirm that indeed DOCNAME.tex has been pushed there.
1. Come back to your machine, and start editing DOCNAME.tex. After this, you can use this as a normal repo using the workflow below.

## Prerequisite tools and configuration

You will need the following tools in place on all your work machines to get started:

1. A github account that I have correctly linked to our lab's github repos. Set up a free account on github and send me your GitHub username. Chances are that if you are able to read this online, you are already set.

1. A working [LaTeX TeXLive installation](https://www.tug.org/texlive/), either on Linux (depends on your distro, see [instructions for Debian Linux](https://wiki.debian.org/Latex)) or [on Mac OSX](http://www.tug.org/mactex/), updated to the latest version at the time you read this.

	  Working on Windows with LaTeX is for dummies. I have nothing against [the MikTeX package](https://miktex.org), but it is sometimes out of date with TeXLive, and installing TeXLive on Windows is a pain that I cannot help you with. If you are addicted enough to Windows to compromise your productivity, it is your call. If you want to use [Overleaf](https://www.overleaf.com) and then manually manage pushing files to the lab's github repos, that is your mess to deal with.

	  Bottomline: don't expect me to cut you any slack on the use of Windows at work - if you pick the wrong platform, then you pay for the consequences. If your work suffers, I will just see you as error prone and unprofessional, and won't care for any Windows-related excuses you may offer. And no, I do not care if Prof. XYZ uses Windows to type in LaTeX markup for his or her work, or whether a collegue you met at a conference does.
	  
	  This will be a recurring theme: other tools you need to use also work better on a Linux/BSD or Mac platform. You are training to be a professional, switch to a professional OS. I understand that you may have some programs on Windows that you prefer to use, but that can be easily managed through the use of a VM: you can setup VMWare, or VirtualBox (free) or Qemu (free) with your favorite version of windows and use it when you need to. No, you do not need to buy a Mac - a laptop running elementary OS or Manjaro or Ubuntu or Debian (pick any) will do just fine. Modern Linux distros mostly work out of the box.

1. A professional LaTeX IDE. There are a lot of really good ones, and the choice is a matter of your taste. I have been partial to [Atom](https://atom.io) in recent past, but have used [Kile](https://cgit.kde.org/kile.git/) and [Emacs](https://www.gnu.org/software/emacs/) in the past with excellent results.  Emacs is an extremely powerful behemoth of an editor (and many other things) that I used with LaTeX (and Fortran, Matlab, etc., especially during my own PhD) for years, and have now resumed using (the name of the emacs package to install is called AucTeX). If you want a copy of my .emacs, ask. There are many others that I have not used - pick any that works with your LaTeX installation. Get good at it.

1. A working Zotero account. You must have the following installed/configured:

	  *  [Zotero standalone](https://www.zotero.org/download/) for your platform.
	  *  Zotero connector for the browser you use for reading journal articles. This will make your life immensely simpler.
	  *  [Better BibTeX](https://retorque.re/zotero-better-bibtex/installation/) installed.

	We do not use Mendeley, Readcube, etc., as they are not as clearly open source as Zotero, and hence have uncertainty regarding continued support, as well as useability.

1.  A working [Grammarly](https://app.grammarly.com) installation. Use the Institute license:

	  * Step 1: go to [www.grammarly.com/edu](www.grammarly.com/edu)  (mandatory to sign up from this URL)
	  * Step 2: Click on Join Your Organization button, fill up the self-service form. Ensure that users are registering from their respective official email id (@iitd.ac.in). You are requested to use your official email ID xx@iitd.ac.in without mentioning your Deptt/Centre name in the email ID and follow the steps given in the email.
	  * Step 3: After clicking signup, an activation email will be sent to the user's institutional email ID.

1. (Optional) A working installation of [LangTool](https://languagetool.org/) is a standalone library for grammar checking that supports add-ons for specific IDEs. Depending on which IDE you choose, you can set up and configure this for use. [TeXtidote](https://github.com/sylvainhalle/textidote) is a possible interface that can be used for this purpose. Recommended use is through the commandline. This requires downloading a .jar file for langtool which contains the actual library.

1.  A working [Python installation](https://www.python.org). Consult the Internet to figure out how to install the latest version of Python for your platform. Once that is done, [install texsoup](https://github.com/alvinwan/TexSoup), [numpy](https://www.numpy.org), [pandas](https://pandas.pydata.org), [matplotlib](https://matplotlib.org), [python-docx](https://python-docx.readthedocs.io/en/latest/), [Jinja2](https://palletsprojects.com/p/jinja/), [openpyxl](https://foss.heptapod.net/openpyxl/openpyxl), [Pillow](https://pillow.readthedocs.io/en/stable/) and [reportlab](https://www.reportlab.com/opensource/). Packages in python are generally installed using pip (specifically pip3).

1. (Optional)  A working Matlab installation. Use the [Institute license and installation instructions](http://repo.iitd.ac.in/matlab/). Matlab (and sometimes Python) can be used to produce scientific plots for your paper. Python is a superior alternative for most purposes at this point. Hence, Matlab is not necessary. You can still keep it around for running your legacy code. Unless you have specific needs, don't do any new code development on Matlab.

1. Access to [TurnitIn](https://www.turnitin.com). You will use this to check for originality of manuscripts. Never add any document to repository. The Institute has a license. Ask me for access - send me your IIT Delhi username, and a non-IITD (gmail) address.

1. An ORCID id that you must communicate to me, especially when you are writing a paper.

## Git

The recommended git workflow is as under (never deviate from this, holler if you need help):

* When you are ready to push changes,

		git add <every file you made changes to>
		git commit -m "<A brief one-sentence summary of the changes you made.>"
		git push

* When I or any of your co-authors has pushed changes, and you need to get the latest version of the paper,

		git pull

As you get more familiar with git, you will learn more useful tricks. 

Under no conditions must you delete a file from the repo. Tampering with the commit history of a manuscript is malpractice and makes it impossible to track what changes you made when. If you are uncomfortable, learn. This does not apply to any obsolete file you are not going to use again under the same name (this is almost exclusively done for deleting old figures, etc.). To accomplish that:

	    git rm <filename you want to get rid of>

* The only files you should include in the repo are your figures (.eps, .png), .tex source(s), .pdf (compiled from .tex). Do **not** add any auxillary files generated by running pdflatex.

GitHub has of late deprecated https logins, and you should set up your ssh key using the [procedure they have outlined](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent). For existing repos, you can convert them to ssh (from https they may have been earlier by default) using [these simple instructions](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#changing-a-remote-repositorys-url).

Please note that a new ssh key is needed for each of your machines, and you have to save it to GitHub for it to recognize your push and pull attempts. If you use the same laptop everywhere, then doing the above exercise just once will suffice. If you have a different machine you use at your apartment, or hostel room, you will need to repeat the above exercise for those as well.

## LaTeX

Develop, if you are new to it, sufficient LaTeX working knowledge, from web resources, and practice (nothing like writing to give you that practice). There are so many available that it makes little sense to choose one. Here is [one possible starting point](https://www.latex-tutorial.com/tutorials/) (result of a web search). The enclosed template, which you should rename before starting to edit things. Do not worry about the journal requirements about formatting of text when you get started. In LaTeX, it is very simple to switch from one style to another. The template uses a style that is minimal and allows you to focus on the content. We will make a final decision on which journal to submit this to when we get close to finalizing the manuscript.

We do not use Microsoft Word unless forced by our audience. If the journal we are writing for demands it (and very few are this way), we convert our LaTeX markup final document after all edits and discussions, to Microsoft Word [using a tool called pandoc](https://pandoc.org) using [citation styles](https://github.com/citation-style-language/styles) for the journal we are targeting.

Why? LaTeX is far superior to Word in terms of:
- tracking changes - the impact of this is big: you get complete usability with GitHub, or any version control system. Yes, Word has track changes, but what do you when you need to track changes for multiple documents in a given revision (which is the actual use case)? That is where you need a version control system with support for branching, etc. A format that is plain text, like LaTeX, just works. Binary blobs don't, unless you export Word to flattened XML and even that is buggy because Word (or LibreOffice Writer) still mess up with graphics.
- automatic generation of difference documents (see below),
- reduced size of documents (plain text),
- absence of [well-known irritation and time-wasteful factors](https://www.antipope.org/charlie/blog-static/2013/10/why-microsoft-word-must-die.html),
- ease of switching from one style to another (just needs editing of the preamble) - you will realize how powerful this is when you are resubmitting a paper to a different journal after an editorial rejection from the journal you previously submitted to.
- maintaining content robustness,
- superior quality output,
- better math, which takes less time to type up,
- robust and flexible citation management, etc.

The best part is that a .tex document is plain text, and can be opened anywhere, even on a mobile phone without need for any special apps. A comparison between LaTeX and Word is a bit akin to a comparison between a professional, and an amateur. Every Word paper I have written (in pre-pandoc days) has taken me several times as long to write, and there still were problems at the end with the document that I could not fix.

Make your working life simple. Just refuse to deal with Word unless forced to. I understand that some postdocs may have a problem as especially chemists generally do not use LaTeX. In that case, please request one of your co-author grad students to help you out. It is not a very bad idea to pick up a skill if your time permits. I am giving chemistry postdocs this option because they tend not to have the time to learn new skills, being so excellent with synthesis, and also work in a field where 95\%+ of the people use Word.

### Using Git versioning to generate difference documents

You can use git and latexdiff to generate PDFs for your manuscripts that allow you to visually compare different versions of the manuscript separated by any number of commits. This is particularly useful when you are editing the document with me, or when we need to submit a changes document with a revision - it nicely marks up what you need to see.

## Grammarly

Documents will need to be checked against Grammarly *prior* to pushing to GitHub. This will need to be done for each new document you open. Open Grammarly in a browser. Open a new document (or open the previously saved document and overwrite). Paste in your LaTeX markup for your paper after you are done with a draft. Change goals settings as below:

1. Audience: Expert.
1. Formality: Neutral.
1. Domain: Academic.
1. Tone: Neutral, Analytical.
1. Intent: Inform, Describe.

Make your corrections in the browser window. Once you are done, copy and paste it back into your IDE.

## Reference Management

We use Zotero for all reference management, citation management and bibliography generation tasks.

You will need to create one shared Zotero library, call it `<YourFirstName><YourLastName><Year you started in my lab>`. So, if you are Ram Kumar and started in my lab in 2017, the name of the shared collection will be RamKumar2017. You will need to go to [your Zotero account](https://www.zotero.org/groups/) to do this. After creating it, you will browse to the settings of the shared library (Library Settings) and set the following:
  -  Group Type: Private.
  -  Library Reading: Any group member.
  -  Library Editing: Any group member.
  -  File editing: No group file storage.

You will share this shared collection with me (go to Members Settings). My Zotero username: madhusudansingh.

You will create your own collections in Zotero based on area (can be Processing Methods, or Material Characterization, etc.) - this can be done from Zotero standalone. Connect your Zotero library using WebDAV to your Nextcloud space on IIT Delhi cloud. Settings:
  -  (under Sync) URL: https://owncloud.iitd.ac.in/nextcloud/remote.php/webdav/zotero. (the first and last bits of that URL are already on the setup screen). This will be followed by your IIT Delhi username and password. Download files at sync time. Make sure you uncheck Sync attachment files in group libraries using Zotero storage.
  -  (under Export) Default Format can be anything. Can be IEEE or Applied Physics Letters.
  -  (under Cite>Word Processors) You can install any add-ins you need. If you use Mac OSX, you can install the Microsoft Word add in if you have that installed from the Institute software repository.
  -  (under Better BibTeX>Citation Keys) Citation key format: [auth:lower]:[year]. This is different from the Zotero default.
  -  On your disk, create a folder under root folder (or anywhere sensible), called bib. Now go to your Zotero standalone main screen (My Library) and select all your references (add one or two using the Zotero browser connector if the library is empty). Right click>Export Items. Then select Better BibLaTeX format. Check Export Notes. Check Keep updated. Click OK. Then browse to the bib folder you just created and choose any filename with .bib extension. Could be something sensible like LibZoteroAutoExport.bib, that tells you that it is an automatic export from your Zotero library and should never be externally edited.
  -  (under Better BibTeX > Automatic Export) and confirm that a new entry named My Library. Make sure that you set Automatic export to On Change. This will ensure that whenever you add something to Zotero, it is automatically reflected in the bib file. Check Export unicode as plan-text latex commands (recommended). Set Add URLs to BibTeX export to no. Check Export Notes. You can do this for individual collections as well, which makes this handy when you are actively writing a paper.
  
### What is citable?

All peer-reviewed literature is citable. Also citable are named reports from respected agencies world-wide that have reference ids for their reports/publications, such as NIST, or BIS. However, web pages (which by definition can change between the date of citation, and date of review/publication/reading after publication) are **not** citable. Public domain patents are citable, as are conference papers for which an immutable record etc. exists.

### Using Zotero

This is the fun part. You will need to have a good browser. Go to [Zotero website](www.zotero.org) and download a connector (this is different from Zotero Standalone) for your browser. Note that the Chrome connector works for those of you who are using the Brave browser (recommended). Install the connector using the process defined for your browser. You may have to restart your browser at the end. 

Why are we doing this? Remember: you access papers through a browser? This is how you add papers to your Zotero collection in a form that is directly and immediatey usable in LaTeX or Word:

* Go to the URL for the paper you want to add in your browser (where you installed the Zotero connector). Let the paper finish loading. Not the PDF, but the main page where the abstract and links for PDF are present.
* In the meantime, open your Zotero standalone window and click on the target collection (can be your shared collection). Make sure that the collection is selected. 
* Go back to the browser. The main page for paper would have finished loading by now even if you have a slow connection. 
* On the browser toolbar, look for the icon for Zotero connector. This will be likely the icon you have not seen before on your browser toolbar. Click on it. A pop up of sorts will open up, and start saving the details of the paper to your collection. 
* Go back to Zotero and confirm. Click on the newly added paper, and see all the details on the right pane. That is all. You have successfully added your first paper to the collection.
* Confirm that your Better BibTeX installation is working by checking the Extra field in the right pane. It should look like a LaTeX citation key. This key will incidentally also appear as the very first field (Citation Key).
* To make sure that your citation key does not change subsequently (this is a problem with Zotero that Better BibTeX fixes), right click on the selected paper. Under Better BibTeX menu, click on Pin BibTeX key.

In the rare case that you are forced to use LibreOffice Writer or Word, Zotero will also be used to do reference management for those pieces of software, so this is really the only thing you need to setup.

#### Summary:

* The target zotero library (your own, or shared, like in this case) should be selected in Zotero standalone prior to using the Zotero connector.
* The paper must finish loading (can be the abstract, or the full HTML page) before you can use the Zotero connector.
One click. Done.
* Every paper added to your shared collection must be added this way.

Things for conference papers can get fuzzier. Some conferences have a nice Zotero importable format. Some don't. If they do not, you will not be able to use Zotero connector, but will have to do this manually. Go to New Item icon in the main window of Zotero standalone (green disc with a white plus in it) and choose Conference Paper. Then you fill in the details in the right pane. Make sure you capture all the details. It will probably take you 5 minutes the first time. Remember, in the name, you enter last name first. 

For Patents, this again may need to be done manually for Indian patents and patent applications (USPTO is nicer). The corresponding document type is under New Item > More > Patents.

## Scientific Graphics

We do not use Microsoft Excel at all in our group, nor does anyone who does scientific plots for a living. Microcal Origin is used in some related disciplines (especially Chemistry and Devices), but compared to Matlab/Python, it is a waste of time since each plot has to be replotted, and there is comparatively little availability of the data analysis and reduction that is possible otherwise. If you have an Origin (or a general WYSIWYG) habit, please get rid of it.

All scientific graphics, excepting scan data (such as AFM, SEM, TEM, etc.) must always be output in a [vector graphics](https://en.wikipedia.org/wiki/Vector_graphics) format. EPS (.eps), PDF(.pdf) and TikZ (.tex) files are typically used. Scan data is usually submitted in TIFF format (which is a bimap/raster format). JPEG is a lossy format and is almost never used. PNG (.png) images can be useful for making associated presentations. Consult the journal's webpage when finalizing the figures for resolution requirements.

Please also learn [TikZ](https://en.wikibooks.org/wiki/LaTeX/PGF/TikZ) and [PGF](https://ctan.org/pkg/pgf) for making illustrations. You can use [Inkscape](https://inkscape.org) as well as any other software that outputs vector graphics images. The [quality of TikZ](http://www.texample.net) is the best of all the available options. Get good at it. On the rare occasion you will need to generate a 3D model in a graphic (can happen when you are going for a very high impact factor journal), you will use [Blender](https://www.blender.org). The use of tools like qtikz or KTikZ can make your life considerably easier while working with TikZ.

Plotting of data will be done either in Matlab or Python (preferred of late with Matplotlib). [Gri](http://gri.sourceforge.net/gridoc/html/Introduction.html) or [GnuPlot](http://www.gnuplot.info) are classic alternatives, but they are not as versatile as Matlab or Python. The best option perhaps is TikZ output from Matlab/Python/Inkscape, which can be directly used in your LaTeX markup using

	\input{tikzimage.tex}

This option makes certain that the same fonts are used for plots as are used in your manuscript. However, many journals demand identifiable figure files, and in any case, complicated figures with a lot of points can [run into LaTeX memory limitations](https://github.com/matlab2tikz/matlab2tikz/wiki/TeX-capacity-exceeded,-sorry). It is one of those cases where the technically best option is not universally useable. What you can do is to use a tool like qtikz to generate the standalone .eps file just prior to manuscript submission.

The best thing to do? Please use Matlab or Python as a matter of habit for your routine data. Create functions (not scripts).

### Data

This part is not necssarily directly related to the business of writing a manuscript but directly impacts it. Whenever you save any data from an experiment, be it in NRF, CRF, or wherever, you *must* do the following:

1. Name your data in an obfuscated manner. You do not want to tell your local competitors what you are working on. Your lab notebook will contain the look up table between an unhelpfully named file `1-newexpt2.csv` and `20210717-NaYF4Gd2Y3-PL-300nm700nm-d1.csv`.
1. Grab your data off the measurement computer and save it on your own machine in a suitable place.
1. Have a systematic method for your local directories that are named in a manner that lets you locate the data within seconds.
1 Insist on getting a plain text format for your data, say .csv as opposed to binary blobs like .xlsx. Most tools that output .xlsx will also output .csv. If they do not for some reason, or the tool operator won't help you, do it yourself.
1. Maintain **automated** backups of **all** your data and analysis functions and scripts. Use any number of online backup options - Mega, OneDrive, etc. No, the backup needs to be automated, and not occassionally done manual. Human beings make mistakes, and loss of data can be a PhD derailing mistake. Set your rsync script to do the backup at least every hour.
1. Understand clearly - fudging data is a firing offense. No, it is not worth it no matter what pressure you are under. If you think a line of investigation is not working out, come talk to me. I am your advisor, and helping you make mid-course corrections is part of my job description.

### Plotting data

Our lab used to be Matlab-centric. So, a lot of what is written below is geared towards Matlab. Matlab is still a fine tool to use if that is what you prefer to work with. However, I am persuaded that Python's Matplotlib and Pandas library are as good, if not even better than Matlab. All of what is described below can be done in Python. One big advantage of Python over Matlab is that we do not need the Institute license for Python - it is open-source. This becomes a major concern when you are traveling, or working from off-campus (or there is a network issue on-campus). Using Python will make you more productive. So, read what is written below, but use Python if you can switch from Matlab. I personally switched to Python and have not looked back despite over 10-15 years working with Matlab.

Figures are the most important part of a paper. Please see the following links to get an idea on how to do this for Matlab:

 -  https://blogs.mathworks.com/loren/2007/12/11/making-pretty-graphs/
 -  https://blogs.mathworks.com/loren/2009/06/03/hold-everything/
 -  https://physicalmodelingwithpython.blogspot.com/2015/06/making-plots-for-publication.html
 -  For the lazy ones: https://github.com/masumhabib/PlotPub

However, there is this prevalent addiction to the gui that is leading to serious under-use of the power of Matlab, producing suboptimal results, and wasting your time. Sure you can drive a Ferrari at the pace of a bullock cart, but that is disrespectful to the Ferrari and yourself. Matlab is that Ferrari. Do not under-use it like a texty version of Microcal Origin.

Every call to ````uigetfile```` is a sign of laziness and paying for that laziness in repeated time wastage. As a grad student, it is borderline criminal to waste so much time on plotting, and spend less time (as an inevitable result) thinking about your data. Here are some rules that are designed to force you to do the right thing (these are written for Matlab users, but the same apply to Python users):

* No use of Matlab **scripts**. Use functions. Thinking modularly will
  - force you to become a better programmer who uses the vast power at your disposal,
  - allow code reuse, which will save scads of time when you are plotting similar data (as all of you do every week).

  How do you tell when you are using a function and when you are using a script - easy. Let us say you wrote a function func.m, which contains a function ````[oarg1,oarg2,...]=func(iarg1,iarg2,...)````, followed by its function body, ending in a ````return```` statement. You save the file and close it. If you find yourself editing func.m between uses of func, then you have written a script, and not a function. Congratulations on being lazy, but you have kissed goodbye to loads of my time while doing that. I do not appreciate students who waste my time.

  So, yes, its not sufficient to merely use ````function```` keyword in your file like a paper-pushing bureaucrat, you actually have to use it like one. Yes, it will force you to think, and yes, that takes some time (and effort) initially. And yes, you have to do it this way because thinking this way goes beyond rapid professional looking plots - it makes you more well-planned and considered in your actions.

  I do not care if your edit-needlessly-because-I-hate-to-think crap works. The point of a Ph. D. is to learn more effective ways of converting data into information, and in our lab, converting that information into deployable technologies. Not molly coddle your existing ineffective work habits at the cost of opportunities.

* Ban on uigetfile. Use wildcards against function input arguments, and parse the filenames and headers for the needed data. This will force you to name your files (data, etc.) in a standardized, easy to understand manner that eliminates future snafus like confusing one dataset for another. Once you know you to automate your analysis to the extent possible, you will automatically have files named like ````09272018_NRF_XRD_mode_thin_KNN_concK30_Tanneal450C_scanrate0.5_range_20-70.csv```` instead of the utterly useless (from an archival standpoint) ‘1.xlsx’.

  If you are using a shared facility like NRF for data, you should use `1.csv`, etc. since we do not want to tell the local competition what we are doing. However, when you come out, you should spend 5 minutes renaming all your files according to the paper based lookup table that some of you have in your notebooks.

  Your plotting exercise could be as simple as:

  ````a1=analyze_xrd_data(‘09272018’,’eps’);````

  where the input strings are parsed and manipulated to construct your output plot file names, as wildcards to identify the files you want to process, specify output formats, etc.

  Think in terms of
  - what you are providing Matlab, and
  - what you want to get out of it.

  Code **everything** in between. Yes, it is possible. What you think needs human intervention, actually doesn’t. Think before you waste more of your time and mine. The math works this way (time units are arbitrary, but indicative of relative magnitudes):

  | Style of coding | Time taken in function design and coding | Time taken in debugging | Time taken in production/use | Time taken for publication graphics |
  ---|---|---|---|---|
  |Use scripts, editing as needed for each dataset | 10 | 10 | 100 | 1000
  |Use functions, with thoughtfully selected input and output arguments that transfer maximal information efficiently, and produces publication quality plots | 1000 | 100 | 1 | 100 |

  Let us say you do about 4 experiments a week, over 3 months, to produce one paper with 6 figures. Let us also assume that debugging is needed for the first 4 experiments (as anything coded does).

  - The scripting approach will cost you 10 + 4 x 10 + 4 x 4 x 3 x 100 + 6 x 1000=10850 time units.
  - The careful function design approach will cost you 1000 + 4 x 100 + 4 x 4 x 3 x 1 + 6 x 100=2048 time units.

  That is a 5-fold difference in time spent. That is 8802 time units you have stolen from your time to think about the experiment (which can for instance ensure that you repeat a wrong experiment for several weeks before realizing your mistake), of which 5400 time units are stolen from me during paper editing process per iteration.

  Still want to use the old blind approach?

* Ban on proprietary formats. That especially includes .xls and .xlsx formats. Yes, you can open these in Matlab on Mac or Windows, but what happens if your Excel license is not working for some reason? Using closed formats is a very dumb choice when it comes to valuable stuff like your data. Every program that outputs xls also outputs csv (comma separated values), which is plain text, which any program on any platform can read.

* Mandatory use of Matlab handle graphics (or equivalent). You need stuff like:

		h1=figure(figname1);
		p1=plot(x1,y1,’r+’);
		ax1=gca;
		set(p1,'YScale','log');
		set(p1,'YTickMode','manual')
		yticks1 = 10.^(floor(log10(min(hdist1+hoffset1))):ceil(log10(max(hdist1+hoffset1))));
		set(p1,'YTick',yticks1)
		set(p1,'YLimMode','manual');
		set(p1,'YLim',[yticks1(1) yticks1(end)]);
		set(p1,'YGrid','on');
		set(p1,'FontName','Times');
		set(p1,'FontWeight','bold');
		set(p1,'FontSize',8);
		...
		print -depsc2 h1 strcat(figname1,’.’,fmt1);``

and not whatever you are writing right now. Similar fine-grained programmatic control is possible in Python.

Using handle graphics makes the whole armada of ‘set’ and ‘get’ functions available to you. Use them to standardize your analysis functions. Then use those functions every day.

5. Ban on white space. This is a direct result of your gui addiction and failure to use handle graphics. Any figure that has white space around it is a nucleus of a bomb that will gradually blow up in your face when it comes time to put figures together in a panel for a publication. It is space you have stolen from your data, and fonts, which in turn cannot be as clear as the space available can actually make them as. A standard journal column is 88mm (IEEE) or 84mm (RevTeX) across, with about 174 mm being the width of printable area of a full page. That space is for your data and any labels. Not thoughtless white space born out of process laziness.

The soul of a paper are its figures. These are what are done first after identifying the message, and then the paper grows organically around them. Without good papers (which are directly related to daily habits of producing publication quality figures, day after day, and not some special stuff you are forced to do 5-7 times in your Ph. D. / MS), your grad level work will not amount to much.

### Video supplementary data

Some manuscripts naturally involve the use of video. In such a case, you should prepare MPEG-4 video (H.264 codec) wit compression settings designed to produce a file smaller than about 2-3 MB in size. Typically, long animations, or videos do not much make sense. Please do not push large files (such as multimedia) on GitHub if they exceed about 5 MB in size. Nice tools for this purpose are ffmpeg, HandBrake, etc.

## Use of pre-print archives

You must never cite literature that is not peer-reviewed when it comes to papers. Depositing a paper to pre-print archives such as arXiv is possible but given that many prominent journals explicitly ban the use of pre-print archives, it is advisable not to use them. However, some classes of papers and journals, especially those involving pure theory, or in the general domain of Physics, can be placed on arXiv.

## Plagiarism

Plagiarism is an unforgivable sin in our business. It involves copying words, figures, data, tables, etc from one published work to another. It can be the relatively innocent kind - copying your own text/illustrations/images/tables, or it can be the malicious kind - copying someone else. Both are forbidden in our profession, and you have to ensure that your manuscript has less than 5\% overlap (excluding references and small phrases (less than 5 words)). The tool we use for this purpose is Turnitin. To use it effectively, use the Institute license, and make absolutely certain that you do not add your manuscript to any repository while you run the check. The class I have created for students who register (see above) explicitly removes repository addition. But you must check each time. If you accidentally add your manuscript to a repository, it will lead to whoever else checks to find a nearly 100\% match plagiarism alert with that repository and needlessly complicate your life. No, once you add stuff to Turnitin's repositories, it cannot be taken back. This incidentally also applies to your research proposal and thesis.

It is a dog eat dog world out there. And your competition is global. Get lean, hungry and yes, a bit OCD about your work practices + figures. Carefulness produces good results. *Chalta hai* leads to car crashes. Be careless if you like, but on your own time.
