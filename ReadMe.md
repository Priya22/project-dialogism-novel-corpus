# The Project Dialogism Novel Corpus

This repository contains data associated with the [The Project Dialogism Novel Corpus:
A Dataset for Quotation Attribution in Literary Texts](https://arxiv.org/abs/2204.05836).


**Updates (29 JUNE 2023)**
- Data for 6 novels has been added to PDNC. The novels are: "Mansfield Park", "Hard Times", "Oliver Twist", "Winnie The Pooh", "Where Angels Fear to Tread", and "A Passage to India".  
- Character information for many novels has been updated with gender information.
- Various errors in metadata have been corrected.


## Data and Annotation
The PDN Corpus contains annotations for speaker, addressees, referring expression, and pronominal mentions for all quotations in full-length novels. 

The full list of novels being annotated can be found in the `PDNC-Novel-Index.csv` file. The file lists various metadata for each novel, including a unique `Novel Code`, the narrative person (first, second, third, or a mixture), gender of the narrator, various publication details, names of the annotators, and a unique `Author Code` indicating the author of the novel (see `PDNC-Author-Index.csv` for author metadata).  The `Folder Name` field indicates the name of the folder within the `data/` folder where annotated quotation information is stored.

**Note**: If the `Folder Name` column for a particular novel does not have an entry, it indicates that annotations for that novel are still being processed.

### Annotation Guidelines

The full text of the annotation guidelines that were used to annotate this corpus can be viewed at [this link](https://docs.google.com/document/d/1eBsX2rjdLBkmA-kWB_jHCxC1nmbzinH04WUg9PeN_2A/edit?usp=sharing). This includes instructions for annotating quotation information as well as entering corpus metadata.

### Data Description

In the `data` folder, for each novel, there are three files:
- `text.txt`: The text of the novel
- `quotations.csv`: This is a CSV file where each row contains, for a quotation:
    - `quoteId`: A unique ID assigned to the quotation
    - `quoteText`: The text of the quotation
    - `subQuotationList`: A single quotation can sometimes be interrupted by a referring expression in the text -- we call these parts "sub-quotations". This stores the sub-quotations associated with the quotation in a list.
    - `quoteByteSpans`: This is a list of lists, where each element is of the form [start-byte, end-byte], indicating the corresponding character-byte spans from the novel text for each sub-quotation.
    - `speaker`: The name of the speaker
    - `addressees`: The names of the addressees
    - `quoteType`: The type of the quotation (implicit, anaphoric, or explict)
    - `referringExpression`: The referring expression associated with the quotation, if any
    - `mentionTextList`: This is a list of lists, where each element contains the texts of the mentions within each sub-quotation. 
    - `mentionSpansList`: This is a list of lists, where each element contains the character-byte spans of the mentions within each sub-quotation.  
    - `mentionEntitiesList`: For each mention from the above list, this stores the corresponding list of character entity or entities referred to by that mention.
- `character_info.csv`: Each character-entity in a novel is assigned a unique ID. Each row of this CSV has the following information for each character:
    - `Character ID`: The ID assigned to the character
    - `Main Name`: The *main* name associated with each character
    - `Aliases`: A list of aliases by which the character is referred to throughout the text
    - `Gender`: Character gender, as inferred from pronouns used by the author. 'U' if unknown, 'X' if un-annotated.
    - `Category`: A rough categorization into major, intermediate, and minor characters based on the amount ad proportion of spoken dialogue.

### Helper Files
The IPython notebook `load_data.ipynb` shows how to load and read the data files for a novel using the `pandas` library for Python (version 3.7 or above).



## Contact
The authors can be contacted via email.

- [Krishnapriya Vishnubhotla](https://priya22.github.io/) (University of Toronto)
- [Adam Hammond](https://www.adamhammond.com/) (University of Toronto)
- [Graeme Hirst](https://www.cs.toronto.edu/~gh/) (University of Toronto)

Email: vkpriya@cs.toronto.edu, adam.hammond@utoronto.ca, gh@cs.toronto.edu

