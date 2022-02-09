Synapse CI/CD Configuration with Github
=======================================

1.  CI/CD Workflow

2.  Dev Synapse git integration setup

CI/CD Workflow:

1.  Work on feature branch

2.  Test

3.  Integrate into collaboration branch through pull request

4.  Approve pull request and merge into collaboration branch (main or master)

5.  Push to QA environment using branch filter on workspace_publish

6.  Test in QA environment

7.  Approve moving to production

8.  Code moves into production

![Graphical user interface, text, application, email Description automatically generated](media/050428b6a019fc09fa97f166a6851f04.png)

Collaboration branch –

![Text Description automatically generated](media/49172ebcf682d217b49bd5227119900c.png)

Be sure that Import existing resources to repository is checked.

![Graphical user interface, text, application, email Description automatically generated](media/ff9926446524e30f87f0193e31eebe2d.png)

![Graphical user interface, text, application, email Description automatically generated](media/00d95205137260d25ed3d17e238dffdb.png)

Working with Branches:
======================

![Graphical user interface Description automatically generated](media/826411ddcf3eef14365337fda5c78a60.png)

In your working branch create a notebook.

![Graphical user interface, text, application, email Description automatically generated](media/4a7066a501636ea7b327ad6f9da6e4e2.png)

Commit the change.

Note the change added a working branch

![Graphical user interface, text, application Description automatically generated](media/b7e5ed08ddb4f76f479c6ea7aff384ce.png)

![](media/a6b100016c48af226394b538b20b9116.png)

![Graphical user interface, text, application Description automatically generated](media/6cdc0f86e511e95cca400f89d37ef2b3.png)

![Graphical user interface, text, application, email Description automatically generated](media/6f354f2f1b0d105dae12d3c01ba896a7.png)

Merge pull request

![Graphical user interface, text, application, email Description automatically generated](media/95e8c4e10611881e3f46885b218876df.png)

![Graphical user interface, text, application, email Description automatically generated](media/58f07613b3855a7acef1b3b4321d188d.png)

![Graphical user interface, application, Word Description automatically generated](media/14aa42ecb28c32d8ee0b71d9ba8f761f.png)

![Graphical user interface, text, application, email Description automatically generated](media/0448b9a62c5fb276a0284287b0b2ec45.png)

![Graphical user interface, text, application, email Description automatically generated](media/5b137e885ed626c1cee2eaa91c0d8356.png)

![Graphical user interface, text, application, email Description automatically generated](media/9fe5bfd8f1def83d4043864232125c57.png)

Publishing 
===========

By default, Synapse Studio generates the workspace templates and saves them into
a branch called workspace_publish

![Graphical user interface, text, application, email Description automatically generated](media/15db3bc81ee7a498e20ef0923e335dec.png)

Best Practices:
===============

-   **Permissions**. After you have a git repository connected to your
    workspace, anyone who can access to your git repo with any role in your
    workspace will be able to update artifacts, like sql script, notebook,spark
    job definition, dataset, dataflow and pipeline in git mode. Typically you
    don't want every team member to have permissions to update workspace. Only
    grant git repository permission to Synapse workspace artifact authors.

-   **Collaboration**. It's recommended to not allow direct check-ins to the
    collaboration branch. This restriction can help prevent bugs as every
    check-in will go through a pull request review process described
    in [Creating feature
    branches](https://docs.microsoft.com/en-us/azure/synapse-analytics/cicd/source-control#creating-feature-branches).

-   **Synapse live mode**. After publishing in git mode, all changes will be
    reflected in Synapse live mode. In Synapse live mode, publishing is
    disabled. And you can view, run artifacts in live mode if you have been
    granted the right permission.

-   **Edit artifacts in Studio**. Synapse studio is the only place you can
    enable workspace source control and sync changes to git automatically. Any
    change via SDK, PowerShell, will not be synced to git. We recommend you
    always edit artifact in Studio when git is enabled.

Setting up CI/CD Pipeline:

[Continuous integration & delivery in Azure Synapse Analytics - Azure Synapse
Analytics \| Microsoft
Docs](https://docs.microsoft.com/en-us/azure/synapse-analytics/cicd/continuous-integration-delivery)
