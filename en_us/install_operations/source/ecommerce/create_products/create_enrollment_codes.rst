.. _Enable and Create Enrollment Codes:

#####################################
Enable and Create Enrollment Codes
#####################################

.. note::
  The enrollment codes in this topic are not related to the enrollment codes in
  the :ref:`Create and Manage Coupons` topic.

Enrollment codes allow users to purchase bulk enrollments for a course.

************************
Enable Enrollment Codes
************************

To enable enrollment codes for a course, you use the **Create New Course** page
in the course administration tool, which is located at
``http://localhost:8002/courses/``, to create course seats. When you complete
the form to create course seats, you select an **Include Enrollment Code**
option. Enrollment codes are then enabled for the course.

To enable enrollment codes, follow these steps.

#. Run the following command to enable enrollment codes in the E-Commerce
   service.

   ::

     ``--enable-enrollment-codes=True``

   For more information, see :ref:`Add Another Site Partner and Site
   Configuration`.

#. Follow step 1 through step 5 in :ref:`Create Course Seats` to access and
   select options on the **Add New Course** page. Do not select **Create
   Course** after you complete step 5.
#. Select **Include Enrollment Code**.
#. Select **Create Course**.

After you select **Create Course**, enrollment codes are enabled for that
course.

************************
Create Enrollment Codes
************************

#. Go to the enrollment page for the course.
#. On the enrollment page, select **Buy enrollment**. Do not select **Enroll in
   the course**.

   The **Page Name** page opens.

#. For **Number of Enrollment Codes**, enter the number of enrollment codes
   that you want. Each enrollment code is for one course seat.
#. Select **Purchase**.

After you select **Purchase**, you receive an e-mail message that contains a
link to a .csv file. The .csv file lists the enrollment codes.



.. include:: ../../../../links/links.rst
