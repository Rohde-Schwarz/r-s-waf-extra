Use cases
=========

This section list use cases for the R&S®Web Application Firewall.

Use cases are classified by categories:
 * [Security](./Security)

Documentation:
* 1 [How to import a subworkflow in the WAF](#how-to-import-a-subworkflow-in-the-waf)
* 2 [R&S documentation](#rohde-and-schwarz-documentation)


How to import a subworkflow in the WAF
--------------------------------------

Use case can provide backups to deploy it on a R&S®WAF.

You can import a backup file through the R&S®WAF Administration Interface. Go to Management > Backup view:

Click on "Upload":

![](doc/readme_img/1.png "Backup menu")

Choose the backup file and import it:

![](doc/readme_img/2.png "Upload a backup")

Right click on the imported backup file and click on "Restore":

![](doc/readme_img/3.png "Restore the backup")

Select all the elements (here there is one sub-workflow, but it could contain multiple subworkflows, ICX rules, static bundles...), and click on "OK":

![](doc/readme_img/4.png "Select objects to restore")

Now, in your workflow list, you can use your imported sub-workflow.


Rohde and Schwarz documentation
-------------

For more information, see the official documentation at https://documentation.appsec.rohde-schwarz.com/pages/viewpage.action?pageId=4004929
