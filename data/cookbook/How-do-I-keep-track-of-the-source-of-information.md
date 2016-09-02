### Problem Statement:

When the AAC begins to generate a graph of all of the partner's information, many entities that reference the same entity will exist and be reconciled.

We would like to be able to connect statements made about the entities to the instituion making the statement, particularly when they disagree.

For example, given an person named  Maria von Trapp, I'd like to know that Princeton thinks that Maria von Trapp's middle name is "von" and the last name is "Trapp", but that Harvard thinks that "von Trapp" is the last name.

If the information is reconciled without provenance, we will only know that "Trapp" and "von Trapp" are two possible last names.

### Best Practice:

*To Be Determined*

### Discussion:

*(From David Newbury)*

I'd like to maintain field-level provenance for data fields, and I'd like to do this without URL parsing.  This will be essential for things like constituents, where we're going to end up with conflicting data provided by multiple partners, and we're going to have to be able to distinguish between them.

How do we credit external sources for providing us with information, and how do we allow users to judge the authority of statements made?

(I know we can potentially do this through looking at the URL.  Is this sufficient?)

*(From Rob)*

We shouldn’t care about [the source of external references].  And if we do, I’d like to know why we care about it enough to essentially requiring reification of the entire dataset, making it miserable to work with.

*(From Vladimir)*


First of all, we'd like to know that <princeton/constituent/123> and <harvard/constituent/456> are the same.  Better yet, we want to map them both to VIAF or ULAN if possible.  How to deal with labels is a secondary question.

But I see what you mean: for properties of art-research interest, you want to record them all, with provenance.

*(From Rob)*

To me, this question could be off-loaded to “How do AAC partners contribute to ULAN?” which is a Getty question we need to answer in the near future.

---


I think PROV-O is over-engineering for singly-mastered data (e.g. about objects)

*(From Rob)*

I’ve run afoul of the PROV-O constraints so many times over the past few years that I would recommend either extreme caution and checking any use with real experts, or avoiding it entirely.  (e.g. <https://www.w3.org/TR/prov-constraints/#generation-generation-ordering> )

---

> How do we know the source of an external reference (ULAN vs VIAF) using only RDF, and not by parsing the URLs?

If someone just gives you a URL, you'll have to parse the URL.
- ULAN has such links, e.g.
  ulan:nnnn skos:inScheme ulan:
  But to get them, you need to load the full ULAN.
- VIAF doesn't have such links. But you can add them to you repo e.g. like
  viaf:nnnn void:inDataset viaf:



### Reference: