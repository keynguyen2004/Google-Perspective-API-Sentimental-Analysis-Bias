# Google Perspective API Sentimental Analysis Bias

## Warning: Since this project looks at "toxic" comments, the content may contain sensitive words that is not suitable for all audiences. Please be aware of what you are about to view and what you may see. 


### Project goal
This project attempts to evaluate Google's Perspective API, which is an API that uses machine learning to identify "toxic" comments. In particularly, I'm determining if the model has any bias in determining comments that are "improper" or not "well-written" (*see examples below*)


### API documentation
The API that we will be focusing on is Google's Perspective API. Its documentation can be found here: https://perspectiveapi.com/


### Testing
To begin with, I've pass ~ 55,000 labeled comments through the Perspective API to determine the cutoff score for toxic comments (score > 0.5). Using this cutoff score, I pass the test data, which contain 2 data sets. 

  1. **Control group**: Contain 100 comments, 50 toxic and 50 non-toxic ones.
  2. **Experimental group**: Contain 100 comments, 50 toxic and 50 non-toxic ones. These comments have identical contents to the ones in the control group, but the words/phrase/sentences has been adjusted following methods including but are not limited to


    i. Addition/removal of characters: h.ow fking d.umb can y.ou be
    ii. "Deform" the comment: hooooww sTOopid r u?
    iii. Substitute (similarly-looking) characters: y0u A$$h0le
  

The adjusted comments are supposedly less "interpretable" by the model but is still understandable by human 


### Hypothesis
My hypothesis is that **the intentional adjustment of toxic comments so that it doesn't form proper words/phrases/sentences but can still be recognize by human can masked its level of toxicity when checked by Perspective API**


### Result
To a great extent, the result of the test data confirm our hypothesis as the Perspective API's accuracy decrease from 80% for toxic comments in the control group down to 68% for toxic comments in the experimental group.

