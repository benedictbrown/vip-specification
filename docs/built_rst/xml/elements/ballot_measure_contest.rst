.. This file is auto-generated.  Do not edit it by hand!

.. _multi-xml-ballot-measure-contest:

BallotMeasureContest
====================

The BallotMeasureContest provides information about a ballot measure before the voters, including
summary statements on each side. Extends :ref:`multi-xml-contest-base`.

+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Tag              | Data Type                               | Required?    | Repeats?     | Description                              | Error Handling                           |
+==================+=========================================+==============+==============+==========================================+==========================================+
| ConStatement     | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Specifies a statement in opposition to   | If the element is invalid or not         |
|                  |                                         |              |              | the referendum. It does not necessarily  | present, then the implementation is      |
|                  |                                         |              |              | appear on the ballot.                    | required to ignore it.                   |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| EffectOfAbstain  | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Specifies what effect abstaining (i.e.   | If the element is invalid or not         |
|                  |                                         |              |              | not voting) on this proposition will     | present, then the implementation is      |
|                  |                                         |              |              | have (i.e. whether abstaining is         | required to ignore it.                   |
|                  |                                         |              |              | considered a vote against it).           |                                          |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| FullText         | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Specifies the full text of the           | If the element is invalid or not         |
|                  |                                         |              |              | referendum as it appears on the ballot.  | present, then the implementation is      |
|                  |                                         |              |              |                                          | required to ignore it.                   |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| InfoUri          | ``xs:anyURI``                           | Optional     | Single       | Specifies a URI that links to additional | If the field is invalid or not present,  |
|                  |                                         |              |              | information about the referendum.        | then the implementation is required to   |
|                  |                                         |              |              |                                          | ignore it.                               |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| PassageThreshold | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Specifies the threshold of votes that    | If the element is invalid or not         |
|                  |                                         |              |              | the referendum needs in order to pass.   | present, then the implementation is      |
|                  |                                         |              |              | The default is a simple majority (i.e.   | required to ignore it.                   |
|                  |                                         |              |              | 50% plus one vote). Other common         |                                          |
|                  |                                         |              |              | thresholds are "three-fifths" and        |                                          |
|                  |                                         |              |              | "two-thirds". If there are `competing    |                                          |
|                  |                                         |              |              | initiatives`_, information about their   |                                          |
|                  |                                         |              |              | effect on the passage of the             |                                          |
|                  |                                         |              |              | BallotMeasureContest would go here.      |                                          |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| ProStatement     | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Specifies a statement in favor of the    | If the element is invalid or not         |
|                  |                                         |              |              | referendum. It does not necessarily      | present, then the implementation is      |
|                  |                                         |              |              | appear on the ballot.                    | required to ignore it.                   |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| SummaryText      | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Specifies a short summary of the         | If the element is invalid or not         |
|                  |                                         |              |              | referendum that is on the ballot, below  | present, then the implementation is      |
|                  |                                         |              |              | the title, but above the text.           | required to ignore it.                   |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Type             | :ref:`multi-xml-ballot-measure-type`    | Optional     | Single       | Specifies the particular type of ballot  | If the field is invalid or not present,  |
|                  |                                         |              |              | measure. Must be one of the valid        | then the implementation is required to   |
|                  |                                         |              |              | :ref:`multi-xml-ballot-measure-type`     | ignore it.                               |
|                  |                                         |              |              | options.                                 |                                          |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| OtherType        | ``xs:string``                           | Optional     | Single       | Allows for cataloging a new              | If the field is invalid or not present,  |
|                  |                                         |              |              | :ref:`multi-xml-ballot-measure-type`     | then the implementation is required to   |
|                  |                                         |              |              | option, when Type is specified as        | ignore it.                               |
|                  |                                         |              |              | "other."                                 |                                          |
+------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+

.. code-block:: xml
   :linenos:

   <BallotMeasureContest id="bmc30001">
      <BallotSelectionIds>bms30001a bms30001b</BallotSelectionIds>
      <BallotTitle>
         <Text language="en">State of the State</Text>
         <Text language="es">Estado del Estado.</Text>
      </BallotTitle>
      <ElectoralDistrictId>ed60129</ElectoralDistrictId>
      <Name>Referendum on Virginia</Name>
      <ConStatement label="bmc30001con">
         <Text language="en">This is no good.</Text>
         <Text language="es">Esto no es bueno.</Text>
      </ConStatement>
      <EffectOfAbstain label="bmc30001abs">
         <Text language="en">Nothing will happen.</Text>
         <Text language="es">Nada pasará.</Text>
      </EffectOfAbstain>
      <ProStatement label="bmc30001pro">
         <Text language="en">Everything will be great.</Text>
         <Text language="es">Todo va a estar bien.</Text>
      </ProStatement>
      <Type>referendum</Type>
   </BallotMeasureContest>

.. _competing initiatives: http://ballotpedia.org/Laws_governing_the_initiative_process_in_California#Competing_initiatives


.. _multi-xml-contest-base:

ContestBase
-----------

A base model for all Contest types: :ref:`multi-xml-ballot-measure-contest`,
:ref:`multi-xml-candidate-contest`, :ref:`multi-xml-party-contest`,
and :ref:`multi-xml-retention-contest` (NB: the latter because it extends
:ref:`multi-xml-ballot-measure-contest`).

+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Tag                     | Data Type                               | Required?    | Repeats?     | Description                              | Error Handling                           |
+=========================+=========================================+==============+==============+==========================================+==========================================+
| Abbreviation            | ``xs:string``                           | Optional     | Single       | An abbreviation for the contest.         | If the field is invalid or not present,  |
|                         |                                         |              |              |                                          | then the implementation should ignore    |
|                         |                                         |              |              |                                          | it.                                      |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| BallotSelectionIds      | ``xs:IDREFS``                           | Optional     | Single       | References a set of BallotSelections,    | If the field is invalid or not present,  |
|                         |                                         |              |              | which could be of any selection type     | then the implementation should ignore    |
|                         |                                         |              |              | that extends                             | it.                                      |
|                         |                                         |              |              | :ref:`multi-xml-ballot-selection-base`.  |                                          |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| BallotSubTitle          | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Subtitle of the contest as it appears on | If the element is invalid or not         |
|                         |                                         |              |              | the ballot.                              | present, then the implementation should  |
|                         |                                         |              |              |                                          | ignore it.                               |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| BallotTitle             | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Title of the contest as it appears on    | If the element is invalid or not         |
|                         |                                         |              |              | the ballot.                              | present, then the implementation should  |
|                         |                                         |              |              |                                          | ignore it.                               |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| ElectoralDistrictId     | ``xs:IDREF``                            | **Required** | Single       | References an                            | If the field is invalid, then the        |
|                         |                                         |              |              | :ref:`multi-xml-electoral-district`      | implementation should ignore it.         |
|                         |                                         |              |              | element that represents the geographical |                                          |
|                         |                                         |              |              | scope of the contest.                    |                                          |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| ElectorateSpecification | :ref:`multi-xml-internationalized-text` | Optional     | Single       | Specifies any changes to the eligible    | If the element is invalid or not         |
|                         |                                         |              |              | electorate for this contest past the     | present, then the implementation should  |
|                         |                                         |              |              | usual, "all registered voters"           | ignore it.                               |
|                         |                                         |              |              | electorate. This subtag will most often  |                                          |
|                         |                                         |              |              | be used for primaries and local          |                                          |
|                         |                                         |              |              | elections. In primaries, voters may have |                                          |
|                         |                                         |              |              | to be registered as a specific party to  |                                          |
|                         |                                         |              |              | vote, or there may be special rules for  |                                          |
|                         |                                         |              |              | which ballot a voter can pull. In some   |                                          |
|                         |                                         |              |              | local elections, non-citizens can vote.  |                                          |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| ExternalIdentifiers     | :ref:`multi-xml-external-identifiers`   | Optional     | Single       | Other identifiers for a contest that     | If the element is invalid or not         |
|                         |                                         |              |              | links to another source of information.  | present, then the implementation should  |
|                         |                                         |              |              |                                          | ignore it.                               |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| HasRotation             | ``xs:boolean``                          | Optional     | Single       | Indicates whether the selections in the  | If the field is invalid or not present,  |
|                         |                                         |              |              | contest are rotated.                     | then the implementation should ignore    |
|                         |                                         |              |              |                                          | it.                                      |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Name                    | ``xs:string``                           | **Required** | Single       | Name of the contest, not necessarily how | If the field is invalid, then the        |
|                         |                                         |              |              | it appears on the ballot (NB:            | implementation should ignore it.         |
|                         |                                         |              |              | BallotTitle should be used for this      |                                          |
|                         |                                         |              |              | purpose).                                |                                          |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| SequenceOrder           | ``xs:integer``                          | Optional     | Single       | Order in which the contests are listed   | If the field is invalid or not present,  |
|                         |                                         |              |              | on the ballot. This is the default       | then the implementation should ignore    |
|                         |                                         |              |              | ordering, and can be overrides by data   | it.                                      |
|                         |                                         |              |              | in a :ref:`multi-xml-ballot-style`       |                                          |
|                         |                                         |              |              | element.                                 |                                          |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| VoteVariation           | :ref:`multi-xml-vote-variation`         | Optional     | Single       | Vote variation associated with the       | If the field is invalid or not present,  |
|                         |                                         |              |              | contest (e.g. n-of-m, majority, et al).  | then the implementation should ignore    |
|                         |                                         |              |              |                                          | it.                                      |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| OtherVoteVariation      | ``xs:string``                           | Optional     | Single       | If "other" is selected as the            | If the field is invalid or not present,  |
|                         |                                         |              |              | **VoteVariation**, the name of the       | then the implementation should ignore    |
|                         |                                         |              |              | variation can be specified here.         | it.                                      |
+-------------------------+-----------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
