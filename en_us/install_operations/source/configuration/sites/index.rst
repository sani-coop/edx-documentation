.. _Configuring Sites:

######################################################
Configuring Sites
######################################################

You can configure multiple sites within your Open edX installation. A site
presents your Open edX courses and content in an individual way. You can
configure sites independently of each other. For example, you can assign
different themes to your Open edX sites.

By default, an Open edX installation has one site. The default site is what
users interact with when they visit your site. You do not need to add multiple
sites to your Open edX installation. You can apply themes to the default site.

Sites are hosted on separate domains or subdomains from your Open edX
installation. You configure the domain name for a site in the Django admin site
when you create it. Your Open edX installation uses a site when a user visits
the domain that you configure for it. For example, you might configure one site
with the domain name ``universityofhere.edu`` and another site with the domain
name ``universityofthere.edu``. Or you might configure one site with the domain
name ``arts.myuniversity.edu`` and another site with the domain name
``sciences.myuniversity.edu``.

.. _Create a Site:

****************************************
Create an Open edX Site
****************************************

To create an Open edX site, do the following.

#. Log into the Django admin site for your Open edX site.

#. Select **Sites** to open the ``http://{hostname}/admin/sites/site`` page.

#. Enter the domain name for the site.

.. _Configuring Sites Independently:

****************************************
Configure Sites Independently
****************************************

You can set configuration properties independently for individual sites. For
example, you can set the ``PLATFORM_NAME`` property to different values for
sites to indicate that the sites present courses for different organizations.

.. What is the complete set of configuration properties that you can set for a
.. site? If you set a property for one or more site, do you need to remove it
.. from lms.env.json?

To set configuration properties for an individual site, do the following.

#. Log into the Django admin site for your Open edX site.

.. Confirm all UI after this point in the procedure.

#. Select **Site Configurations** to open the
   ``http://{hostname}/admin/site_configuration/siteconfiguration`` page.

#. Select **Add site configuration**.

#. From the **Site** menu, select the site you want to configure.

#. Enter configuration properties in the **Values** field. Structure all
   properties in valid JavaScript Object Notation (JSON) format. This section
   includes an example

#. If you want the configuration properties to affect the site immediately,
   select **Enabled**. The configuration properties will not affect the site
   until you select **Enabled**. If needed, you can return to the **Site
   configurations** screen for this site to enable the configuration properties
   later.

The following example shows a set of configuration properties for a site.

.. code-block:: json

    {
      "course_email_from_addr":"my-site@example.com",
      "domain_prefix":"my-site",
      "university":"Education Programs",
      "PLATFORM_NAME":"Education Programs",
      "platform_name":"Education Programs",
      "show_only_org_on_student_dashboard":true,
      "email_from_address":"my-site@example.com",
      "payment_support_email":"payments@example.com",
      "SITE_NAME":"my-site.org",
      "site_domain":"my-site.org",
      "SESSION_COOKIE_DOMAIN":"my-site.org",
      "ALWAYS_REDIRECT_HOMEPAGE_TO_DASHBOARD_FOR_AUTHENTICATED_USER":false,
      "ENABLE_COURSE_SORTING_BY_START_DATE":true,
    }

