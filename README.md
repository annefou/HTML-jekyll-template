# norESM documentation




Except where otherwise noted, content on the norESM documentation is licensed under the following license:[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)


### Table of Contents

*   [NORESM wiki](https://wiki.met.no/noresm/start#noresm_wiki)
    
    *   [Purpose of wiki](https://wiki.met.no/noresm/start#purpose_of_wiki)
        
    *   [Obtaining a version of the model](https://wiki.met.no/noresm/start#obtaining_a_version_of_the_model)
        
    *   [Running / Configuring the model](https://wiki.met.no/noresm/start#runningconfiguring_the_model)
        
    *   [Develop the model](https://wiki.met.no/noresm/start#develop_the_model)
        
        *   [Setting up at different machines](https://wiki.met.no/noresm/start#setting_up_at_different_machines)
            
        *   [Issue tracker](https://wiki.met.no/noresm/start#issue_tracker)
            
        *   [Testing](https://wiki.met.no/noresm/start#testing)
            
        *   [Version control best practices](https://wiki.met.no/noresm/start#version_control_best_practices)
            
        *   [NorESM2 branches in active development](https://wiki.met.no/noresm/start#noresm2_branches_in_active_development)
            
        *   [NorESM1 branches in active development](https://wiki.met.no/noresm/start#noresm1_branches_in_active_development)
            
        *   [Uncertain parameters in the aerosol model](https://wiki.met.no/noresm/start#uncertain_parameters_in_the_aerosol_model)
            
    *   [Analyze model results](https://wiki.met.no/noresm/start#analyze_model_results)
        
    *   [Archive model results](https://wiki.met.no/noresm/start#archive_model_results)
        
    *   [Share model results](https://wiki.met.no/noresm/start#share_model_results)
        
    *   [Past and ongoing work](https://wiki.met.no/noresm/start#past_and_ongoing_work)
        
    *   [Resources](https://wiki.met.no/noresm/start#resources)
        

NORESM wiki
===========

NorESM1 is the Norwegian Earth System model used for CMIP5. The model is based on the CCSM framework ([http://en.wikipedia.org/wiki/Community\_Climate\_System\_Model](http://en.wikipedia.org/wiki/Community_Climate_System_Model "http://en.wikipedia.org/wiki/Community_Climate_System_Model")). However, NorESM has special features developed by Norwegian researchers.

Main references are:

GMD - Special issue The Norwegian Earth System Model: NorESM; basic development, validation, scientific analyses, and climate scenarios

[http://www.geosci-model-dev.net/special\_issue20.html](http://www.geosci-model-dev.net/special_issue20.html "http://www.geosci-model-dev.net/special_issue20.html")

Bentsen, M., I. Bethke, J. B. Debernard, T. Iversen, A. Kirkevåg, Ø. Seland, H. Drange, C. Roelandt, I. A. Seierstad, C. Hoose, and J. E. Kristjansson (2013): The Norwegian Earth System Model, NorESM1-M. Part 1: Description and basic evaluation of the physical climate, Geosci. Model Dev., 6, 687-720, doi:10.5194/gmd-6-687-2013

Iversen, T., M. Bentsen, I. Bethke, J. B. Debernard, A. Kirkevåg, Ø. Seland, H. Drange, J. E. Kristjansson, I. Medhaug, M. Sand, and I. A. Seierstad (2013): The Norwegian Earth System Model, NorESM1-M – Part 2: Climate response and scenario projections, Geosci. Model Dev., 6, 389-415, doi:10.5194/gmd-6-389-2013

Kirkevåg, A., T. Iversen, Ø. Seland, C. Hoose, J. E. Kristjánsson, H. Struthers, A. M. L. Ekman, S. Ghan, J. Griesfeller, E. D. Nilsson, and M. Schulz (2013): Aerosol–climate interactions in the Norwegian Earth System Model – NorESM1-M, Geosci. Model Dev., 6, 207-244, doi:10.5194/gmd-6-207-2013

Tjiputra, J. F., C. Roelandt, M. Bentsen, D. M. Lawrence, T. Lorentzen, J. Schwinger, Ø. Seland, and C. Heinze (2013): Evaluation of the carbon cycle components in the Norwegian Earth System Model (NorESM), Geosci. Model Dev., 6, 301-325, doi:10.5194/gmd-6-301-2013

The next version of the model NorESM2 is built on a update version of the CCSM framework, CESM2. ([http://www.cesm.ucar.edu/models/cesm2/](http://www.cesm.ucar.edu/models/cesm2/ "http://www.cesm.ucar.edu/models/cesm2/")) ; ([https://en.wikipedia.org/wiki/Community\_Earth\_System\_Model](https://en.wikipedia.org/wiki/Community_Earth_System_Model "https://en.wikipedia.org/wiki/Community_Earth_System_Model"))

This wiki contains information shared between NorESM developers and users

Purpose of wiki
---------------

The purpose of the wiki is to provide a common place for NorESM users and developers to share information. What tools are you using? Which version should I run for what purpose? etc.

Any questions about the wiki content should be directed to [oyvindse@met.no](mailto:mailto:oyvindse@met.no "mailto:oyvindse@met.no")

Obtaining a version of the model
--------------------------------

**NEW** The development version has been moved to git: Obtain a copy through

 git clone https://githubUserName@github.com/metno/noresm.git  

You first need to be registered as a noresm user on github (see detailed info in [Obtain a copy of the model (using git)](https://wiki.met.no/noresm/gitbestpractice "noresm:gitbestpractice"))

To obtain the current official version (i.e an old version used in CMIP5) : svn checkout [https://svn.met.no/NorESM/noresm/branches/noresm-ver1-cmip5](https://svn.met.no/NorESM/noresm/branches/noresm-ver1-cmip5 "https://svn.met.no/NorESM/noresm/branches/noresm-ver1-cmip5"). If you are not a registered user, contact trond.iversen@met.no to get the proper authorization.

The main trunk (stable development verison) is at the “master” branch on github (including CAM 5.3). (see detailed info in [Obtain a copy of the model (using git)](https://wiki.met.no/noresm/gitbestpractice "noresm:gitbestpractice"))

If you are on a normal ubuntu PC and want the source code, you might see that “svn checkout” complains about “gnome keyring”. If you see this problem, the solution is here: [http://askubuntu.com/questions/206604/svn-and-gnome-keyring](http://askubuntu.com/questions/206604/svn-and-gnome-keyring "http://askubuntu.com/questions/206604/svn-and-gnome-keyring")

**Need access to other versions: Special access document**: [https://docs.google.com/a/met.no/document/d/1G1ezxtBhzDyNWwrKJYWmp8gn402bOWThe\_6gN00PDMQ/edit?usp=sharing](https://docs.google.com/a/met.no/document/d/1G1ezxtBhzDyNWwrKJYWmp8gn402bOWThe_6gN00PDMQ/edit?usp=sharing "https://docs.google.com/a/met.no/document/d/1G1ezxtBhzDyNWwrKJYWmp8gn402bOWThe_6gN00PDMQ/edit?usp=sharing")

Running / Configuring the model
-------------------------------

[Newbies guide to running NorESM](https://wiki.met.no/noresm/runmodel/newbie "noresm:runmodel:newbie")

[Advanced configuration (NorESM1)](https://wiki.met.no/noresm/runmodel/advanced "noresm:runmodel:advanced")

[Advanced configuration of NorESM2](https://wiki.met.no/noresm/runmodel/advancednoresm2 "noresm:runmodel:advancednoresm2")

[Fluxes crossing boundaries](https://wiki.met.no/noresm/runmodel/fluxescrossingboundaries "noresm:runmodel:fluxescrossingboundaries")

[CMIP6 volcanic forcing](https://wiki.met.no/noresm/runmodel/cmip6_volcanic_forcing "noresm:runmodel:cmip6_volcanic_forcing")

[CMIP6 emissions of short-lived components](https://wiki.met.no/noresm/runmodel/cmip6emissionsofshortlivedcomponents "noresm:runmodel:cmip6emissionsofshortlivedcomponents")

[CMIP6 greenhouse gas concentrations in NorESM](https://wiki.met.no/noresm/runmodel/cmip6greenhousegasconcentrations "noresm:runmodel:cmip6greenhousegasconcentrations")

Develop the model
-----------------

### Setting up at different machines

Most developers compile and run NorESM on hexagon (hexagon.bccs.uib.no). That machine uses the portland group fortran compiler. Most developers develop the code on that machine using “develop/compile/run/analyze print statments” on that machine.

Some experiments have also been done with compiling running CAM on a normal Linux PC in order to use interactive debuggers. (see below)

[Setting up CAM on your own linux PC](https://wiki.met.no/noresm/settingupcamonlinuxpc "noresm:settingupcamonlinuxpc")

### Issue tracker

Any development should ideally be agreed with the NorESM development team and be properly described in the issue tracker, see the link below

[Using the issue tracker](https://wiki.met.no/noresm/usingtheissuetracker "noresm:usingtheissuetracker")

If you have changed the model and want to merge your changes to the trunk, your model has to pass some tests:

### Testing

[Test list for NorESM](https://wiki.met.no/noresm/testlist "noresm:testlist")

### Version control best practices

**NEW**: After switching to git (13th november 2015) the svn-repository is read-only. Some advice on how to use the new git-repository are available her: [Obtain a copy of the model (using git)](https://wiki.met.no/noresm/gitbestpractice "noresm:gitbestpractice")

Some guidelines for modifying NorESM’s subversion repository: [SVN - Best Practice/FAQ](https://wiki.met.no/noresm/svnbestpractice "noresm:svnbestpractice")

How-to for setting up svn repositories on NorStore: [Subversion how-to for NorStore](https://wiki.met.no/noresm/svnnorstorehowto "noresm:svnnorstorehowto")

### NorESM2 branches in active development

*   [https://github.com/metno/noresm/](https://github.com/metno/noresm/ "https://github.com/metno/noresm/") : master (this is the trunk/master version)
    
*   [https://github.com/metno/noresm/](https://github.com/metno/noresm/ "https://github.com/metno/noresm/") : featureCAM5-OsloDevelopment\_trunk2.0-6 (Main development branch for CAM-Oslo aerosol features)
    
*   [https://github.com/metno/noresm/](https://github.com/metno/noresm/ "https://github.com/metno/noresm/") : feature-classnuc-ice\_featureCAM5-OsloDevelopment-2 (ice nucleation feature branch)
    
*   [https://github.com/metno/noresm/](https://github.com/metno/noresm/ "https://github.com/metno/noresm/") : featureNitrate\_featureCAM5-OsloDevelopment-2/ (aerosol nitrate feature branch)
    

### NorESM1 branches in active development

*   [https://github.com/metno/noresm/](https://github.com/metno/noresm/ "https://github.com/metno/noresm/") : noresm-ver1-cmip5/ (Original NorESM1-M CMIP5 version. Only technical updates)
    
*   [https://github.com/metno/noresm/](https://github.com/metno/noresm/ "https://github.com/metno/noresm/") : noresm-ver1\_r112-r169/ (Further development from the CMIP5 version. Include EU-ACCESS project improvements)
    

You obtain the model code through checking it out. The command would be

git clone https://githubUserName@github.com/metno/noresm.git

git checkout -b aBranchName origin/aBranchName

This gives the code in your directory

### Uncertain parameters in the aerosol model

Developing the model also involves setting some uncertain numbers into the model. Not all of these are available from namelists. Go to the link below to understand where main uncertainties are.

[Uncertain parameters (which can be discussed) in the aerosol model](https://wiki.met.no/noresm/uncertainaerosolparameters "noresm:uncertainaerosolparameters")

Analyze model results
---------------------

[General diagnostics page](https://wiki.met.no/noresm/modeldiagnostics "noresm:modeldiagnostics")

Several tools are shared among NorESM users

*   Prepare atmospheric output on pressure surfaces (Need working netcdf libraries) [pressuresurfaces.tar.gz](https://wiki.met.no/_media/noresm/pressuresurfaces.tar.gz "noresm:pressuresurfaces.tar.gz (4.7 KB)")
    
*   [NorESM output compression tool on hexagon](https://wiki.met.no/noresm/noresm2nc4mpi "noresm:noresm2nc4mpi")
    
*   [NorESM output compression tool on NorStore](https://wiki.met.no/noresm/noresm2nc4norstore "noresm:noresm2nc4norstore")
    
*   [ESM Model including Aerosol Diagnostic Tools](https://wiki.met.no/noresm/modeldiagnostics "noresm:modeldiagnostics")
    
*   [Earth System Model eValuation Tool (ESMValTool)](https://wiki.met.no/noresm/esmvaltool "noresm:esmvaltool")
    

Archive model results
---------------------

Long-term archiving is normally done on NorStore's disk resources (e.g, in /projects/NS2345K/noresm/cases).

To avoid loss of data, another copy should be placed on tape. For instructions, see [Norstore Tape](https://wiki.met.no/noresm/norstoretape "noresm:norstoretape")

Data that builds the basis of publications should be migrated to NorStore's Research Data Archive in order to guarantee preservation and also to offload the project area. For specific NorESM instructions, see [Norstore Archive](https://wiki.met.no/noresm/norstorearchive "noresm:norstorearchive")

Share model results
-------------------

Model output and derived data products can be shared via the Norwegian Earth System Grid data portal [http://noresg.norstore.no](http://noresg.norstore.no/ "http://noresg.norstore.no") (see [Simple online sharing](https://wiki.met.no/noresm/norstoreesg "noresm:norstoreesg") for instructions).

Some aerosol and cloud-relevant output for the development version of NorESM2 is available for those with MET Norway affiliation through VpN at /vol/fou/emep/People/alfk/CAM-Oslo-diagnostics/

Past and ongoing work
---------------------

Several simulations have been performed with NorESM. A list of available simulations and runs can be found here. [List of model runs by NorESM](https://wiki.met.no/noresm/listofruns "noresm:listofruns"). The page also contains an overview of planned simulations. A fairly extensive description of the model and to some extent also the CMIP5 runs can be found at [http://pcmdi9.llnl.gov/esgf-web-fe/](http://pcmdi9.llnl.gov/esgf-web-fe/ "http://pcmdi9.llnl.gov/esgf-web-fe/")

Choose one of the links. Search for NorESM1-M CMIP5 in the search fields. Choose the link model documentation

NorESM is also used in several projects: [Existing projects](https://wiki.met.no/noresm/projects "noresm:projects")

Resources
---------

*   [EVA final meeting: CMOR-ization and ESGF publication of NorESM2 simulations - Ingo Bethke](https://wiki.met.no/_media/noresm/EVAannualMeeting2018_WP4_IngoBethke_20180831.pdf "noresm:evaannualmeeting2018_wp4_ingobethke_20180831.pdf (930.1 KB)")
    
*   [NICEST workshop for ESGF at NSC: CMOR post-processing of NorESM CMIP5 & CMIP6 output - Ingo Bethke](https://wiki.met.no/_media/noresm/LiuWorkshopESGF2018_IngoBethke.pdf "noresm:liuworkshopesgf2018_ingobethke.pdf (4.8 MB)")
    
*   [ESMValTool setup for NorESM (10 May 2017) - Ingo Bethke](https://wiki.met.no/_media/noresm/NorESMValTool20170510.pdf "noresm:noresmvaltool20170510.pdf (1000.5 KB)")
    
*   TaiESM CCliCS workshop in Taipei 2016 - Ingo Bethke ([pptx](https://wiki.met.no/_media/noresm/BethkeEtAl_CCliCS2016_v2.pptx "noresm:bethkeetal_cclics2016_v2.pptx (3.2 MB)"), [pdf](https://wiki.met.no/_media/noresm/BethkeEtAl_CCliCS2016_v2.pdf "noresm:bethkeetal_cclics2016_v2.pdf (3.7 MB)"))
    
*   [HappiEVA kick-off 2016 - Ingo Bethke](https://wiki.met.no/_media/noresm/HappiEVA_kickoff-meeting_Ingo.pdf "noresm:happieva_kickoff-meeting_ingo.pdf (627.1 KB)")
    
*   [NeIC/Nordic ESM workshop 2015 - CMOR-izing of NorESM output by Ingo Bethke](https://wiki.met.no/_media/noresm/NeICESMworkshop2015_IngoBethke.pdf "noresm:neicesmworkshop2015_ingobethke.pdf (1001.7 KB)")
    
*   [Presentation on data management in EVA - EVA meeting, 2014, Bergen](https://wiki.met.no/_media/noresm/eva2014_ingobethke.pdf "noresm:eva2014_ingobethke.pdf (1.1 MB)")
    
*   [NorESM Workshop 2014 SU - Alf Grini](https://wiki.met.no/_media/noresm/alfg_stockholmpres.pdf "noresm:alfg_stockholmpres.pdf (1.2 MB)")
    
*   [NorESM Workshop 2014 SU - Annica Ekman](https://wiki.met.no/_media/noresm/annica_new_noresm_workshop_2014.pdf "noresm:annica_new_noresm_workshop_2014.pdf (400.2 KB)")
    
*   [NorESM Workshop 2014 SU - Chandan Basu](https://wiki.met.no/_media/noresm/workshop-14_chandan.pdf "noresm:workshop-14_chandan.pdf (98.8 KB)")
    
*   [NorESM Workshop 2014 SU - Francesco Pausata](https://wiki.met.no/_media/noresm/pausata_noresm_2014.pdf "noresm:pausata_noresm_2014.pdf (1.3 MB)")
    
*   [NorESM Workshop 2014 SU - Juan-Camilo Acosta](https://wiki.met.no/_media/noresm/pegasos_oct_acosta.pdf "noresm:pegasos_oct_acosta.pdf (1.2 MB)")
    
*   [NorESM Workshop 2014 SU - Risto Makkonen](https://wiki.met.no/_media/noresm/makkonen_noresm_ws_2014.pdf "noresm:makkonen_noresm_ws_2014.pdf (3.4 MB)")
    
*   [NorESM Workshop 2014 SU - Trond Iversen](https://wiki.met.no/_media/noresm/trondiversen_noresm-workshop_oct2014.pdf "noresm:trondiversen_noresm-workshop_oct2014.pdf (894.5 KB)")
    
*   [NorESM Workshop 2014 SU - Vidya Varma](https://wiki.met.no/_media/noresm/vidya_noresm_ws_2014_su.pdf "noresm:vidya_noresm_ws_2014_su.pdf (2.6 MB)")
    
*   [After NorESM Workshop 2014 SU - Alf Kirkevåg: some AeroTab-slides](https://wiki.met.no/_media/noresm/aerotab-slides.pdf "noresm:aerotab-slides.pdf (936.2 KB)")
    

noresm/start.txt · Last modified: 2018-10-12 08:06:36 by oyvindse

* * *

### Page Tools

*   [Show pagesource](https://wiki.met.no/noresm/start?do=edit "Show pagesource [V]")
*   [Old revisions](https://wiki.met.no/noresm/start?do=revisions "Old revisions [O]")
*   [Backlinks](https://wiki.met.no/noresm/start?do=backlink "Backlinks")
*   [ODT export](https://wiki.met.no/noresm/start?do=export_odt "ODT export")
*   [Back to top](https://wiki.met.no/noresm/start#dokuwiki__top "Back to top [T]")

