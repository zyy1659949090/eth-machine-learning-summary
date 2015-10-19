# ETH Machine Learning Summary

We cherry-pick the most understandable explanations and definitions into one summary to summarize the content of the lecture about Machine Learning of Prof. Joachim Buhmann.

Machine learning algorithms are data analysis methods which search data sets for patterns and characteristic structures. Typical tasks are the classification of data, automatic regression and unsupervised model fitting. Machine learning has emerged mainly from computer science and artificial intelligence, and draws on methods from a variety of related subjects including statistics, applied mathematics and more specialized fields, such as pattern recognition and neural computation. Applications are, for example, image and speech analysis, medical imaging, bioinformatics and exploratory data analysis in natural science and engineering:

nonlinear decision boundary	linear discriminant analysis	gene expression levels Non-linear decision boundary of a trained support vector machine (SVM) using a radial-basis function kernel.	Fisher's linear discriminant analysis (LDA) of four different auditory scenes: speech, speech in noise, noise and music.	Gene expression levels obtained from a micro-array experiment, used in gene function prediction.

This course is intended as an introduction to machine learning. It will review the necessary statistical preliminaries and provide an overview of commonly used machine learning methods.

# Subversion/svn basics (If you know neither git nor svn) #

The repository page with a wiki and an issue tracker in our case is at: https://github.com/benelot/eth-machine-learning-summary
You can go to this website and you will see that you have the permissions of a committer if you log in with your github account. The same link is the link for the svn repository as you can see in the lower right of the page:
https://github.com/benelot/eth-machine-learning-summary
This link is accessible with your web browser as well, but that is not how you should use it. This link should be accessed via an svn client, for windows I recommend a client such as TortoiseSVN, which integrates directly into your windows explorer.

The first thing before you can do anything else is to choose the way you want to use svn. It can be used in the terminal, but this might be harder to do than the graphical svn client. A good graphical client for windows might be ¨TortoiseSVN¨, for Mac and linux I recommend rapidSVN, even though in the end it does not matter much. Install the graphical svn client and find a suitable folder on your computer where you want to have your local copy of the machine learning summary. Then you check out the summary via terminal by "svn checkout https://github.com/benelot/eth-machine-learning-summary eth-machine-learning-summary --username your-github-mailaddress" and when prompted, your password. In the graphical svn client, this might be as simple as right-clicking in the suitable folder for the summary, then svn->checkout... There you specifiy this link "https://github.com/benelot/eth-machine-learning-summary" as the svn repository link and let the client check out for you. It might be, that you are prompted your github account and your password when you commit your first changes. So now you should have a folder full of latex documents of which the MachineLearning.tex is the main document, but you can also compile the sub-chapters separately.

## So what is subversion (svn)? ##
So to give you a short description of subversion, I describe the functionality in simple words. It is a version control system with a so called version control repository. It keeps revisions of all documents that are ¨checked in¨ to the repository. This means that initially, a document is saved only on your computer, but if you check it in to the repository, the file is uploaded to the server and its current state belongs to a revision. Whatever happens to your file from now on, you can always go back to the old revision if you mess it up. If you think you made some good changes to the document, you can commit your new document state again, the document in the new state then belongs to a new revision. From then on, you are able to go back to both old states of the document via their revision number.
As we will work together on the Machine learning summary, we also need the updates from the others, which we get by updating the states on our side via an update. I created several subdocuments that are compilable by themselves. This helps us, that our work does not very often affect the same document when we work together. Furthermore, subversion helps us that we do not overwrite each others changes by telling you that there is a conflict between your document state and the last revision of this document on the repository.

## So let us look at a simple example: ##
First, before you commit any changes, you get new updates from the repository, as somebody might have changed something. In the terminal, you do this via the command  "svn update", in a graphical svn client, you might be able to right-click anywhere in the summary folder and click "svn->update".
You wrote some part of the summary in the part "04-Classification.tex". You also added a new figure "classification.png" to the document, which you saved in the folder "figs". This means we have a new state of "04-Classification.tex" but the file was checked in before, so we have a change in that document, and we have a file ¨classification.png¨ not yet under version control. First of all, the new figure needs to be checked in to the repository. In svn on the commandline, we write "svn add path-to-file/classification.png", in a graphical svn client, this might work as easy as going to the file explorer, right-clicking on the figure file and select svn->add... (this depends on the graphical svn client you are using). The other file does not have to be touched especially, as the file is already under version control. So now, you want to commit your changes to the repository, on the terminal you write "svn commit -m " and then message describing in short words what you have changed. Here this would mean: "Write part X in 04-Classification.tex. Add picture to part X." in a graphical svn client, this might again mean a right-click anywhere in the folder of your summary folder, svn->commit... and it will open a window where you see what you commit and a message field for your commit message.

Look at this short presentation from cern to revise the content in short terms again:
https://indico.cern.ch/event/110092/contribution/1/material/slides/0.pdf

As a latex editor I use TexMaker, which works under Windows and Linux and is easy to install and use. But that is totally up to you.
