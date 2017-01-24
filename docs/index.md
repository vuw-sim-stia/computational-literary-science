---
layout: default
---

## [](#header-2-1)Project outcome I: A Computational Approach to Dickens’ Dynamic Character Networks

### [](#header-2-1-1)Background
Character networks have emerged as a central object of inquiry and analysis in computational approaches to literature and the novel. Moretti (2011) proposed that character networks provide visual models of literary texts and offer new perspectives on how they function, offering a static picture of their structure and systems. In addition to providing a tool for the analysis of plot, character networks offer a foundation for social network analysis—for understanding how novels construct relationships between characters and thus the social worlds they represent.  As both Moretti and Piper (2015a) admit, the construction of character maps can be extremely time consuming and challenging, especially when working with novels containing a vast cast of characters. Piper (2015a) and Elson, et al. (2010) have developed programs for extracting social networks from texts by identifying character co-occurrence within paragraphs or by using dialogue interaction to establish relation. While this work reveals the inherent difficulties in reliably generating social networks with speed and ease, it has also shown the possibilities for using character networks to understand genre (Piper 2015b), character typology (Bamman, et al., 2014), and character-space (Piper 2016).

### [](#header-2-1-2)Serial Form and Dickens’s Dynamic Character Networks
The novels of Charles Dickens (1812-1870) are a particularly interesting object of investigation within this field of research. Not only was Dickens a central figure in the development of the nineteenth-century novel—the literary form that has been a primary object of computational analyses—but his novels construct vast and elaborate character networks as they represent and the rapidly changing Victorian world. Scholars have analysed the network elements of Dickens’s novels through more traditional methodologies. Grossman (2012, 2015) has examined how Dickens’s novels reflect the alterations of time and space brought about by public transportation and the development of global transport networks. Levine (2015) has argued that Bleak House represents society as composed of interconnected and dynamically unfolding networks. Gibson (2015) has analysed the “network form” of Our Mutual Friend to show how it conceives social life as an open-ended system of evolving connections. And Andrew Gelman (2015) has speculated that Dickens’s novels work to reproduce the networks of the London world in a sampling. 

Dickens’s character networks are important because of their density and of the complex social world they represent; the way in which those networks were generated also warrants attention. Dickens was a pioneer of the serial novel form, writing monthly (or weekly) instalments of his novels over the course of up to eighteen months. Thus, his novels not only create character networks in the process of their unfolding, but also dramatize the creation and management of those networks in the very act of composition. They offer the opportunity to analyse both how a novel, taken as a completed aesthetic object, maps character connections and also how those networks are imagined and managed in their production. Furthermore, the evolution of Dickens’s career provides another avenue for analysis, as his early novels present episodic structure before he self-consciously announces (Dickens 1844) an intention “to keep a steadier eye on the general purpose and design” of his works. Thus, Dickens’s mode of production, the arc of his career, the substantial but manageable corpus of fourteen completed novels, and the very substance of the world he represents present variables for analysing his character networks through a computational approach.

### [](#header-2-1-3)Methodology and Approach

Our method applies the Transcendental Information Cascades (TIC) approach (Luczak-Roesch et al., 2015) to understand how emergent structures of information are generated during the unfolding of a text. It treats the text as a diachronically evolving information system and uses TIC to isolate the structural properties of that system. Theoretically, one could create an infinite number of models of any given system, depending on the dictionary one chose as the structuring element of the system (e.g., bigrams or trigrams, place names, articles or prepositions, affect words, etc.). We use character names as the structuring element. The network thus provides a visualization of the occurrence of characters and models the information structures they generate.

Our approach treats character names as units of information; thus it is not concerned primarily with their social relation, though a social network can be extrapolated from the dynamic network. The approach, instead, allows analysis of how a cast of characters is generated and managed dynamically over the duration of a text. The text is broken into “slices” of 1000 words (with chapter breaks terminating a slice). Dickens’s larger novels are over 300,000 words, with chapters averaging 4,000 and 8,000 words; this size produces a complex but still manageable network—larger or smaller slices would produce different networks with different properties. Each slice is scanned to detect the presence of the character, so each node in the network is defined by the characters who appear in that segment of the text. Two characters can appear in the same node if they are not linked explicitly or relationally in that segment of text (i.e., they are linked by the contiguity of their names in the text rather than by their interaction), and a character can appear in a node if they do not physically appear in the represented action (e.g., another character mentions or thinks of that character). Edges signify consecutive appearances of a character.

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net1.png "Network construction")
 
The algorithm works from the input of two files: (1) a file containing the text of a novel and (2) a library of character names. Text files for the novels were taken from Project Gutenberg; character libraries were generated beginning with resources such as Pierce (1878) and Hawes (1998), though these lists had to be refined manually so that the “tags” for each character flagged all appearances of that character. For example, the list of tags for Bella Wilfer in Our Mutual Friend consisted of six identifiers: “Bella Wilfer, Miss Wilfer, Bella, Mrs John Harmon, Mrs John Rokesmith, Mrs Rokesmith.” The process and algorithm, as they were refined, produced a high degree of accuracy; full accuracy (i.e., the matching of every instance of a character appearance to the correct character) cannot be guaranteed. In some instances, the text of the novel itself was modified so as to ensure accuracy. Martin Chuzzlewit, for instance, contains two characters named Martin Chuzzlewit, so instances of “Martin” and “Mr. Chuzzlewit” had to be manually disambiguated so that the correct character was flagged. The algorithm can be run on any text, provided the user can input the text file and the character library. Texts for hundreds (even thousands) of novels not under copyright are readily available through resources like Project Gutenberg, though character lists need to be created manually—this presents the most significant barrier to the large-scale application of the method. Character lists need not be comprehensive, as a network can represent any selection of characters from a given novel (e.g., only major characters, only female characters, characters with a particular type of relationship, etc.). 

### [](#header-2-1-4)Tools and Visualization
The algorithm generates several different types of outputs and visualizations, which, both individually and in tandem, offer scholars and students multiple tools for analysis. One output is a dynamic network, which operates as an HTML page that displays the unfolding of the network. 

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net2.png "Network construction")

The dynamic networks can be paused at any point and can provide information about the contents of particular nodes and edges. Each edge can be clicked to reveal the links between two nodes. And each node can be clicked to reveal the characters contained within the node. Moreover, each node contains a “Go to content” link that will take users to the text from the novel that corresponds to that slice. 

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net3.png "Network construction")

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net4.png "Network construction")

Alongside the dynamic network, the algorithm also produces a static network, which provides a picture of the entire network.

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net5.png "Network construction")

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net6.png "Network construction")

Both the dynamic and static networks can be navigated with the aid of outputs that display information for individual characters and also show the overall patterns of character usage. Outputs display a list of all appearances of individual characters, the frequency of character appearance, as well as the first and last appearance of each character.

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net7.png "Network construction")

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net8.png "Network construction")

above: character frequency; below: first and last appearance

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net9.png "Network construction")

Finally, the algorithm generates graphs related to the overall properties of the system: an entropy graph and a coordinates graph that displays the number of unique nodes within the network and their number of appearances. 

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net10.png "Network construction")

### [](#header-2-1-5) Preliminary Analysis
The algorithm has been run on 14 novels to this point, seven novels by Dickens, and four by other Victorian novelists for comparative purposes. Initial analysis reveals several ways in which the outputs might be utilized by scholars and students alike. 

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net11.png "Network construction")

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net12.png "Network construction")

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net13.png "Network construction")

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net14.png "Network construction")

![alt Network construction](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/net15.png "Network construction")

### [](#header-2-1-6)Next Steps
Initial findings demonstrate the potential for using these computational analyses to better understand the underlying structures of the Victorian serial novel form, as well as possibilities for using the visualisations and data to ground close readings of individual novels. 

In addition to applying the algorithm to more novels by Dickens and others, our team aims to refine quantitative values for the networks so as to better understand their properties for comparative purposes.

Tools have also been developed to conduct user studies and analyse how individuals interact with the networks. 

### [](#header-2-1-7)References
Bamman, et al. 2014. “A Bayesian Mixed Effects Model of Literary Character.” ACL 2014.

Dickens, Charles. 1844. Martin Chuzzlewit. Penguin Books, 1999.

Gibson, Anna. 2015. “Our Mutual Friend and Network Form,” NOVEL 48.1. 

Grossman, Jonathan. 2012. Charles Dickens’s Networks: Public Transport and the Novel. Oxford University Press.

———. 2015. “Living the Global Transport Network in Great Expectations,” Victorian Studies 57.2.

Hawes, Donald. 1998. Who’s Who in Dickens. Routledge, 2002.

Elson, David, et al. 2010. “Extracting Social Networks from Literary Fiction.” ACL 2010.

Levine, Caroline. 2015. Forms: Whole, Rhythm, Hierarchy, Network. Princeton University Press. 

Luczak-Roesch, Markus et al., 2015, August. From coincidence to purposeful flow? properties of transcendental information cascades. In Proceedings of the 2015 IEEE/ACM International Conference on Advances in Social Networks Analysis and Mining 2015 (pp. 633-638). ACM.

Moretti, Franco. 2011. “Network Theory, Plot Analysis,” New Left Review 68. 

Pierce, Gilbert. 1878. The Dickens Dictionary. Chapman and Hall. 

Piper, Andrew. 2015a. “Development of a (Semi-) Automatic Character Network Tool” [https://txtlab.org/?p=528]

———. 2015b. “Detecting Literary Characters.” [https://txtlab.org/?p=559]

———. 2016. “The Constraints of Character. Introducing a Character Feature-Space Tool.” [https://txtlab.org/?p=611]

### [](#header-2-1-0)Tool prototype demonstration

[![Alt Screencast demonstration of the distant reading tool for English literature](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/vid1.png)](http://www.youtube.com/watch?v=QnXvtYlL9VA)

[![Alt Screencast demonstration of the distant reading tool for English literature](https://github.com/vuw-sim-stia/computational-literary-science/raw/master/docs/vid2.png)](http://www.youtube.com/watch?v=VD2t1VE4RVc)


## [](#header-2-2)Team

Led by Markus Luczak-Roesch and Adam Grener this interdisciplinary research project was supported under the [spearheading digital futures theme](http://www.victoria.ac.nz/about/strengths/digital-futures), which is part of the areas of strategic distictiveness of Vicotria University of Wellington. 

### [](#header-3-1)Markus Luczak-Roesch

Markus Luczak-Roesch is a Senior Lecturer in Information Systems at the School for Information Management, Victoria Business School, Victoria University of Wellington. Before joining Victoria Markus worked as a Senior Research Fellow on the prestigious EPSRC programme grant [SOCIAM - The Theory and Practice of Social Machines](http://sociam.org) at the University of Southampton, Electronics and Computer Science (UK, 2013-2016). A computer scientist by education, Markus investigates the formal properties of information in socio-technical systems and human factors of information and computing systems. More information: [http://markus-luczak.de](http://markus-luczak.de)

### [](#header-3-2)Adam Grener

Adam Grener is Lecturer in the English Programme at Victoria University of Wellington. His main area of research is the nineteenth-century British novel, though he also has interest in the history of the novel, narrative theory, and computational approaches to literature. His work has appeared in the journals Genre, Narrative, and Modern Philology, and he is the co-editor of a special issue of Genre, "Narrative Against Data in the Victorian Novel," set to appear in March 2017. He is completing a book on realist aesthetics and the history of probabilistic thought. More information: [http://www.victoria.ac.nz/seftms/about/staff/adam-grener](http://www.victoria.ac.nz/seftms/about/staff/adam-grener)

### [](#header-3-3)Research assistants
 * Emma Fenton
 * Tom Goldfinch
