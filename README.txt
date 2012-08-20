CMU ARK Twitter Part-of-Speech Tagger v0.3-pre 
http://www.ark.cs.cmu.edu/TweetNLP/

Basic usage
===========

Requires Java 6.  To run the tagger from unix shell:

    ./runTagger.sh example_tweets.txt modelfile > tagged_tweets.txt

Another example:

    ./runTagger.sh --input-format json barackobama.jsonlines.txt -output tagged_barackobama.txt

The outputs should match tagged_tweets_expected.txt and barackobamaexpected.txt respectively.



Advanced usage
--------------

We include a pre-compiled .jar of the tagger so you hopefully don't need to
compile it.  But if you need to recompile, do:
  mvn install
NOTE: requires Maven 3.0.3+

To train and evalute the tagger, see:
  ark-tweet-nlp/src/main/java/edu/cmu/cs/lti/ark/ssl/pos/SemiSupervisedPOSTagger.java
  scripts/train.sh and scripts/test.sh

Contents
--------
 * runTagger.sh       is the script you probably want
 * lib/               dependencies
 * ark-tweet-nlp/src  the project code itself (all java)

Information
-----------
This tagger is described in the following paper.  Please cite it if you write a
research paper using this software.

  Part-of-Speech Tagging for Twitter: Annotation, Features, and Experiments
  Kevin Gimpel, Nathan Schneider, Brendan O'Connor, Dipanjan Das, Daniel Mills,
  Jacob Eisenstein, Michael Heilman, Dani Yogatama, Jeffrey Flanigan, and Noah A. Smith
  In Proceedings of the Annual Meeting of the Association for Computational
  Linguistics, companion volume, Portland, OR, June 2011.
  http://www.ark.cs.cmu.edu/TweetNLP/gimpel+etal.acl11.pdf

The software is licensed under Apache 2.0 (see LICENSE file).

Version 0.2 of the tagger differs from version 0.1 in the following ways:

* The tokenizer has been improved and integrated with the tagger in a single Java program.

* The new tokenizer was run on the 1,827 tweets used for the annotation effort and the
annotations were adapted for tweets with differing tokenizations. The revised annotations
are contained in a companion v0.2 release of the data (twpos-data-v0.2).

* The tagging model is trained on ALL of the available annotated data in twpos-data-v0.2.
The model in v0.1 was only trained on the training set.

* The tokenizer/tagger is integrated with Twitter's text commons annotations API.

Contact
-------
Please contact Brendan O'Connor (brenocon@cmu.edu) and Kevin Gimpel (kgimpel@cs.cmu.edu)
if you encounter any problems.
