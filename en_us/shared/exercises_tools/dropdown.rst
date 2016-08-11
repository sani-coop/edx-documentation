.. _Dropdown:

#####################
Dropdown Problem
#####################

.. note:: EdX offers full support for this problem type.

The dropdown problem type is a core problem type that can be added to every
course. At a minimum, dropdown problems include a question or prompt and
several answer options. By adding hints, feedback, or both, you can give
learners guidance and help when they work on a problem.

.. contents::
  :local:
  :depth: 2

For more information about the core problem types, see
:ref:`Working with Problem Components`.

**********
Overview
**********

In dropdown problems, learners select one option from a list of answer options.
Unlike :ref:`multiple choice<Multiple Choice>` problems, where the answer
choices are always visible directly below the question, the answer options for
dropdown problems do not appear until the learner selects the dropdown arrow.


================================
Example Multiple Choice Problem
================================

In the LMS, learners select a single answer option to complete a dropdown problem. An example of a completed dropdown problem follows.

.. image:: ../../../shared/images/DropdownExample.png
 :alt: A problem component that contains a series of three dropdown problems.
     The questions have been answered, and two are marked correct and one
     incorrect.
 :width: 600

In this example, a single problem component contains multiple questions, all of
them using the dropdown problem type. To add the example illustrated
above, you enter the following text and Markdown formatting in the simple
editor in Studio.

::

  What type of data are the following?

  >>Age:<<
  [[Nominal, Discrete, (Continuous)]]
  >>Age, rounded to the nearest year:<<
  [[
  Nominal
  (Discrete)
  Continuous
  ]]
  >>Life stage - infant, child, and adult:<<
  [[(Nominal), Discrete, Continuous]]

.. note:: You can separate the answer options with either comma (,) characters
  or new lines.

The OLX markup for this example problem follows.

.. code-block:: xml

  <problem>
    <p>What type of data are the following?</p>

    <label>Age:</label>
    <optionresponse>
      <optioninput options="('Nominal','Discrete','Continuous')" correct="Continuous"></optioninput>
      </optionresponse>
    <label>Age, rounded to the nearest year:</label>
    <optionresponse>
      <optioninput options="('Nominal','Discrete','Continuous')" correct="Discrete"></optioninput>
      </optionresponse>
    <label>Life stage - infant, child, and adult:</label>
    <optionresponse>
      <optioninput options="('Nominal','Discrete','Continuous')" correct="Nominal"></optioninput>
    </optionresponse>
  </problem>

============================================
Analyzing Performance on Dropdown Problems
============================================

For the dropdown problems in your course, you can use edX Insights to review
aggregated learner performance data and examine submitted answers. For
more information, see :ref:`insights:Using edX Insights`.

********************************
Adding a Dropdown Problem
********************************

You add dropdown problems in Studio by selecting the **Problem**
component type and then using either the simple editor or the advanced editor
to specify the prompt and the answer options.

.. contents::
  :local:
  :depth: 1

.. note:: You can begin work on the problem in the simple editor, and then
  switch to the advanced editor. However, after you save any changes you make
  in the advanced editor, you cannot switch back to the simple editor.

.. _Use the Simple Editor to Create a Dropdown Problem:

=================================================
Use the Simple Editor to Add a Dropdown Problem
=================================================

To use the :ref:`simple editor<Simple Editor>` to add a dropdown problem,
follow these steps.

#. In the unit where you want to create the problem, under **Add New
   Component** select **Problem**.

#. From the list of **Common Problem Types**, select one of these problem
   types.

  * **Dropdown**

  * **Dropdown with Hints and Feedback**

    Studio adds a problem of the selected type to the unit.

#. Select **Edit**. The simple editor opens to a template that shows the
   markdown that you can use for this problem type.

#. Replace the guidance provided by the template to add your own text for the
   prompt, answer options, explanation, and so on.

#. Select **Settings** to provide an identifying **Display Name** and define
   settings for the problem. For more information, see :ref:`Problem Settings`.

#. Select **Save**.

========================================================================
Use the Advanced Editor to Edit a Dropdown Problem
========================================================================

To use the :ref:`advanced editor<Advanced Editor>` to add a dropdown
problem, follow these steps.

#. Follow steps 1-3 for creating the problem in the :ref:`simple editor<Use
   the Simple Editor to Create a Dropdown Problem>`.

#. Select **Advanced Editor**. The advanced editor opens to a template that
   shows the OLX (open learning XML) markup that you can use for this problem
   type.

#. Replace the guidance provided by the template to add your own text for the
   label, answer options, solution, and so on.

#. Update the OLX to use any additional tags and attributes in your problem.
   For more information, see :ref:`Dropdown Problem XML`.

#. Select **Settings** to provide an identifying **Display Name** and define
   settings for the problem. For more information, see :ref:`Problem Settings`.

#. Select **Save**.

.. _Use Feedback in a Dropdown Problem:

********************************************
Adding Feedback to a Dropdown Problem
********************************************

For an overview of feedback in problems, see :ref:`Adding Feedback and Hints to
a Problem`. You can add feedback for each of the answer options you provide in
the problem. Use the following guidelines when providing feedback.

* Use feedback for the incorrect answers to target common misconceptions and
  mistakes.

* Ensure feedback provides some guidance to the learner about how to arrive at
  the correct answer.

* Use feedback for the correct answer to reinforce why the answer is correct.
  Because learners are able to guess, ensure that feedback provides a reason
  why the answer is correct for learners who might have selected that answer by
  chance.

You can add feedback in a dropdown problem using the simple editor or the
advanced editor.

=========================================
Configuring Feedback in the Simple Editor
=========================================

You can configure feedback in the :ref:`simple editor<Simple Editor>`.  When
you add a dropdown problem, select the template **Dropdown with Hints and
Feedback**. This template has example feedback syntax that you can replace.

::

  [[
  Wrong Answer {{Feedback for learners who select this answer.}}
  Wrong Answer {{Feedback for learners who select this answer.}}
  (Correct Answer) {{Feedback for learners who select this answer.}}
  ]]

.. note:: When you include feedback, you might find it more convenient use new
  lines to to separate the answer options.

For example, the following problem has feedback for each possible answer.

::

  >>A/an ________ is an example of a vegetable.<<

  [[
    apple {{An apple is the fertilized ovary that comes from an apple tree and
      contains seeds classifying it as a fruit.}}
    pumpkin {{A pumpkin is the fertilized ovary of a squash plant and contains
      seeds classifying it as a fruit.}}
    (potato) {{A potato is an edible part of a plant in tuber form and is
      classified as a vegetable}}
    tomato {{Many people mistakenly think a tomato is a vegetable. However,
      because a tomato is the fertilized ovary of a tomato plant and contains
      seeds it is classified as a fruit.}}
  ]]

===========================================
Configuring Feedback in the Advanced Editor
===========================================

In the :ref:`advanced editor<Advanced Editor>`, you configure answer feedback
with the following syntax.

.. code-block:: xml

    <option correct="False">Option Label
      <optionhint>Feedback for when learner selects this answer.</optionhint>
    </option>

For example, the following problem has feedback for each answer.

.. code-block:: xml

  <problem>
  <label>A/an ________ is an example of a vegetable.</label>
  <optionresponse>
    <optioninput>
      <option correct="False">apple
        <optionhint>An apple is the fertilized ovary that comes from an apple tree and contains seeds classifying it as a fruit.
        </optionhint>
      </option>
      <option correct="False">pumpkin
        <optionhint>A pumpkin is the fertilized ovary of a squash plant and contains seeds classifying it as a fruit.
        </optionhint>
      </option>
      <option correct="True">potato
        <optionhint>A potato is an edible part of a plant in tuber form and is classified as a vegetable.
        </optionhint>
      </option>
      <option correct="False">tomato
        <optionhint>Many people mistakenly think a tomato is a vegetable. However, because a tomato is the fertilized ovary of a tomato plant and contains seeds it is classified as a fruit.
        </optionhint>
      </option>
    </optioninput>
  </optionresponse>
  </problem>

===========================
Customizing Feedback Labels
===========================

By default, the feedback labels shown to learners are **Correct** and
**Incorrect**. If you do not define feedback labels, learners see these terms
when they submit an answer, as in the following example.

::

  Incorrect:
  An apple is the fertilized ovary that comes from an apple tree and contains
  seeds classifying it as a fruit.

You can configure the problem to override the default labels. For example, you
can configure a custom label for a specific wrong answer.

::

  Not Quite:
  Many people mistakenly think a tomato is a vegetable. However, because a
  tomato is the fertilized ovary of a tomato plant and contains seeds it is
  classified as a fruit.

.. note::
  The default labels **Correct** and **Incorrect** display in the learner's
  requested language. If you provide custom labels, they display as you define
  them to all learners. They are not translated into different languages.

Customize Feedback Labels in the Simple Editor
***********************************************

In the :ref:`simple editor<Simple Editor>`, you configure custom feedback
labels with the following syntax.

::

  [[
  (Correct Answer) {{Label:: Feedback for learners who select this answer.}}
  .
  .
  .
  ]]

That is, you provide the label text, followed by two colon (:) characters,
before the feedback text.

For example, the following feedback is configured to use a custom label.

::

  [[
  tomato {{Not Quite:: Many people mistakenly think a tomato is a
  vegetable. However, because a tomato is the fertilized ovary of a tomato
  plant and contains seeds, it is a fruit.}}
  .
  .
  .
  ]]

Customize Feedback Labels in the Advanced Editor
*************************************************

In the :ref:`advanced editor<Advanced Editor>`, you configure custom feedback
labels with the following syntax.

.. code-block:: xml

   <option correct="False">
     Answer
     <optionhint label="Custom Label">
       Feedback for learners who select this answer.
     </optionhint>
   </option>

For example, the following feedback is configured to use a custom label.

.. code-block:: xml

  <option correct="False">tomato
    <optionhint label="Not Quite">Many people mistakenly think a tomato is a vegetable. However, because a tomato is the fertilized ovary of a tomato plant and contains seeds it is classified as a fruit.
    </optionhint>
  </option>

.. _Use Hints in a Dropdown Problem:

************************************
Adding Hints to a Dropdown Problem
************************************

You can add hints to a dropdown problem using the simple editor
or the advanced editor. For an overview of hints in problems, see
:ref:`Adding Feedback and Hints to a Problem`.

.. include:: ../../../shared/exercises_tools/Subsection_configure_hints.rst


.. _Dropdown Problem XML:

**********************************
Dropdown Problem OLX Reference
**********************************

========
Template
========

.. code-block:: xml

  <problem>
  <optionresponse>
    <label>Question or prompt text</label>
    <description>Optional information about how to answer the question</description>
    <option correct="False">Option Label
      <optionhint>
        Feedback for when learner selects this answer.
      </optionhint>
    </option>
    <option correct="True">Option Label
      <optionhint>
        Feedback for when learner selects this answer.
      </optionhint>
    </option>
  <solution>
    <div class="detailed-solution">
      <p>Explanation or Solution Header</p>
      <p>Explanation or solution text</p>
    </div>
  </solution>
  </optionresponse>
  <demandhint>
    <hint>Hint 1</hint>
    <hint>Hint 2</hint>
    <hint>Hint 3</hint>
  </demandhint>
  </problem>

========
Tags
========

* ``<optionresponse>`` (required): Indicates that the problem is a dropdown
  problem.

* ``<label>`` (required): Identifies the question or prompt.

* ``<description>`` (optional): Provides clarifying information about how to
  answer the question.

* ``<option>`` (required): Lists an answer option.

* ``<solution>`` (optional): Identifies the explanation or solution for the
  problem.

* ``<demandhint>`` (optional): Specifies hints for the learner.

**Tag:** ``<optionresponse>``

Indicates that the problem is a dropdown problem.

  Attributes

  (none)

  Children

  ``<option>``

**Tag:** ``<option>``

Lists the answer options.

  Attributes

  .. list-table::
     :widths: 20 80

     * - Attribute
       - Description
     * - ``correct``  (at least one required)
       - Indicates whether an answer is correct. Possible values are ``"true"``
         and ``"false"``. Only one ``correct`` attribute can be set to "true".

  Children

  ``<optionhint>``

**Tag:** ``<optionhint>``

Specifies feedback for the answer.

  Attributes

  (none)

  Children

  (none)

**Tag:** ``<label>``

  Identifies the question or prompt.

  Attributes

  (none)

  Children

  (none)

**Tag:** ``<description>``

 Provides clarifying information about how to answer the question.

  Attributes

  (none)

  Children

  (none)

**Tag:** ``<demandhint>``

Specifies hints available to the learner.

  Children

  ``<hint>``

**Tag:** ``<hint>``

Specifies a hint available to the learner.

  Children

  (none)
