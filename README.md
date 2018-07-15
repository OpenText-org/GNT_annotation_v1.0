# OpenText.org GNT annotation in new inline XML format #

## History ##

These files contain the OpenText.org v0.11 syntax annotations that were given to Logos Bible Software when they licensed the OpenText.org annotations in 2005.

The annotation data has been migrated to a new, inline XML format by Christopher Land and the base text has been corrected and updated to the NA28 by Christopher Land and Ryder Wishart. It should be noted that both of these developments have resulted in minor changes to the annotation.

## XML Format ##

The OpenText annotations were originally produced using stand-off annotation, but the three main annotation layers (clause, wordgroup, word) were combined into a semi-nested hierarchy for Logos Bible Software (see <https://github.com/OpenText-org/combined_annotation_v0.11>), with this combined format being the starting point for producing these files.

The current XML employs an @old_id attribute for the IDs used in the original v0.11 files in order to facilitate referencing (e.g. publications that cited the original IDs), but these old IDs have been deprecated in favour of new IDs that are more informative and transparent but still highly readable. The only detail that perhaps requires explanation is the use of a suffix (e.g. '_2') in cases where two nodes contain the exact same base text (NB: we count up from the lowest node in the tree).

Milestones are now used to mark canonical divisions, with the milestones placed as high in the tree as possible (i.e. preceding all start tags that immediately precede the first relevant word).

In this version of the OpenText.org annotations, only two @type values are possible: 'cl'= clause and 'wg' = wordgroup. The @connect and @level attributes have been deprecated, apart from their use on secondary clauses.

The @enclosed attribute has been deprecated, since the in-line format makes it redundant. For discontinuous units, @next and @prev have been used with reference to the @xml:id value of the following or preceding part.

The names and values of elements and attributes are unabbreviated for the sake of usability. We recommend the use of an XML database such as [BaseX](http://basex.org).

## Outstanding Issues ##

As an artefact of the migration to new XML, there are certain syntactic constructions in the annotations that do not very transparently represent the relationships that exist between clauses and wordgroups (e.g. when a participle is Head of a wordgroup). No attempt has been made to fix these issues for the legacy data, because OpenText 1.5 (and ultimately 2.0) will clarify the syntax.
