# What is it


It's a set of [mr.bob](https://mrbob.readthedocs.io/en/latest/)
templates to use when developing Odoo addons.

<a href="https://asciinema.org/a/CPQNpMuoKPZawVVuvb7rX35xr" target="_blank"><img src="https://asciinema.org/a/CPQNpMuoKPZawVVuvb7rX35xr.svg" width="600px" height="600px" /></a>

It provides the following templates with file structures:

  * ``addon`` : 

        {addon.technical_name}/doc/index.rst
        {addon.technical_name}/doc/changelog.rst
        {addon.technical_name}/__manifest__.py
        {addon.technical_name}/__init__.py
        {addon.technical_name}/static/description/icon.png

  * ``controller`` : 

        {addon.technical_name}/controllers/__init__.py
        {addon.technical_name}/controllers/{model.name_underscored}.py
        
  * ``css`` :

        {addon.technical_name}/static/src/css/{css.name_underscored}.css
        {addon.technical_name}/views/assets.xml

  * ``data`` : 

        {addon.technical_name}/data/{data.name_underscored}.xml

  * ``demo`` :

        {addon.technical_name}/demo/{demo.name_underscored}.xml
        
  * ``js`` : 

        {addon.technical_name}/static/src/js/{js.name_underscored}.js
        {addon.technical_name}/views/assets.xml

  * ``model`` : 

        {addon.technical_name}/models/{model.name_underscored}.py
        {addon.technical_name}/models/__init__.py
        {addon.technical_name}/security{model.name_underscored}_ir.model.access.csv

  * ``qweb`` :

        {addon.technical_name}/static/src/xml/{qweb.name_underscored}.xml

  * ``test`` :

        {addon.technical_name}/tests/test_{test.name_underscored}.py
        {addon.technical_name}/static/src/js/test_{test.name_underscored}}.js
        {addon.technical_name}/views/assets.xml

  * ``view`` :

        {addon.technical_name}/views/{view.name_underscored}.xml

  * ``wizard`` : 

        {addon.technical_name}/wizards/{wizard.name_underscored}.py
        {addon.technical_name}/views/{}.xml
  
# Installation

* Install (Update) via pip from github-repository:
    
        pip install -U git+https://github.com/it-projects-llc/bobtemplates.odoo.git@master

# Configuration

* List of public variables (bite also exists a list (not represented here) of a private variables, which values corresponds with public variables values):

    * ``Copyright`` variables:
        * ``copyright.name``: name of author of template
        * ``copyright.github``: github-name
        * ``copyright.year``: year of creation of template
    
    * ``Addon`` variables:
        * ``addon.version``: version of addon;
            * [ ``10`` | ``11`` | ``12`` ]
        * ``addon.name``: addon's name
        * ``addon.technical_name``: name of addon's folder
        * ``addon.category``: category in manifest;
            * [ ``Accounting`` | ``Discuss`` | ``Document Management`` | ``eCommerce`` | ``Human Resources`` | ``Industries`` | ``Localization`` | ``Manufacturing`` | ``Marketing`` | ``Point of Sale`` | ``Productivity`` | ``Project`` | ``Purchases`` | ``Sales`` | ``Warehouse`` | ``Website`` | ``Extra Tools`` | ``Hidden`` ]

        * ``addon.technical_category``: for choosing icon
            * [ ``access`` | ``barcode`` | ``mail`` | ``misc`` | ``pos`` | ``saas`` | ``stock`` | ``telegram`` | ``website`` | ``website_sale`` ]
        * ``addon.dependency``: list of modules in manifest in ``depends``-field
            * e.g.: ``mail, website, pos``
        * ``addon.upstream``: name of repository
            * [ ``access-addons`` | ``l10n-addons`` | ``mail-addons`` | ``misc-addons`` | ``odoo-saas-tools`` | ``odoo-telegram`` | ``pos-addons`` | ``rental-addons`` | ``website-addons`` ]
        * ``addon.summary``: short description of module in ``README.rst``
        * ``addon.description``: Detailed description of module in ``README.rst``

    * ``Controller`` variables:
        * ``controller.name_dotted``: Controller class name;
            * e.g.: ``controller.class.name``
    
    * ``Model`` variables:
        * ``model.inherit``: inherited model or not?
            * if ``yes`` - write something;
            * if ``no`` - leave blank
        * ``model.name_dotted``: name of model (in ``name``-field or in ``inherit``-field)
            * e.g.: ``model.class.name``
        * ``model.description``: description of model (if not inherited model)
        * ``model.security``: access-rights for model?
            * if ``yes`` - write something;
            * if ``no`` - leave blank
    
    * ``Data`` variables:
        * ``data.name_underscored``: name of file;
            * e.g.: ``data_file_name``
    
    * ``Demo`` variables:
        * ``demo.name_underscored``: name of file;
            * e.g.: ``demo_file_name``
    
    * ``View`` variables:
        * ``view.name_underscored``: name of file;
            * e.g.: ``view_file_name``
    
    * ``Qweb`` variables:
        * ``qweb.name_underscored``: name of file;
            * e.g.: ``qweb_file_name``
    
    * ``wizard`` variables:
        * ``wizard.inherit``: inherited model or not?
            * if ``yes`` - write something;
            * if ``no`` - leave blank
        * ``wizard.name_dotted``: name of model
            * e.g.: ``wizard.name.class``
        * ``wizard.description``: description of model
    
    * ``test`` variables:
        * ``test.name_underscored``:
            * e.g. ``name_of_test``
        * ``test.qweb``: if module uses QWeb?
            * if ``yes`` - write something;
            * if ``no`` - leave blank
        * ``test.tour``: Is there a need for tour (phantom browser)?
            * if ``yes`` - write something;
            * if ``no`` - leave blank

    * ``js`` variables:
        * ``js.name_underscored``: name of file
            * e.g.: ``name_of_js``
    
    * ``css`` variables:
        * ``css.name_underscored``: name of file
            * e.g.: ``name_of_css``
    
* For correct work you need to define ``copyright`` and ``addon`` variables in ``.ini``-file (according to ``.ini`` syntax). 
      e.g.:

            [variables]
            ;###
            ;### copyright
            ;###
            copyright.name = John Doe
            copyright.github = johnnydoey
            copyright.year = 2019
            ;###
            ;### addon
            ;###
            addon.version = 12
            addon.category = eCommerce
            addon.technical_category = pos
            addon.upstream = pos-addons
            addon.name = Name For Testing
            addon.technical_name = web_module_things
            addon.summary = little description of what module can do
            addon.description = It can be very big, or should be very big, but at least it must be bigger than little
            addon.dependency = mail, model, base

* Ways to create config-file: 
    * Manual: create file with extension ``.ini`` (e.g. ``config.ini``) and content it similar to an example above
    * Interactive: create addon-template with ``mr.bob`` with keys:
        * ``--remember-answers`` -- for storing answers in ".mrbob.ini" (example below)
        * ``-O /path/to/directory`` -- for creating addon-template and config-file in ``/path/to/directory``, otherwise it will be created in the current directory (example below)

# Usage

CAUTION: it is recommended to backup or vcs commit your current directory before running these commands, so you can easily see what has been generated and/or changed.
      
Create a new addon and the config-file (``.mrbob.ini``) in the target directory:

            mrbob bobtemplates.itpp.odoo:addon --remember-answers -O /path/to/directory

Now go to the newly created addon directory (``/path/of/directory/{addon.technical_name}``) and create the template (in e.g. ``model``) with config-file:

            mrbob bobtemplates.itpp.odoo:model --config ../.mrbob.ini

Tip: read the ``mr.bob`` user guide.

# Useful links 

* mr.bob readthedocs: https://mrbob.readthedocs.io/en/latest/index.html
* pypi page: https://pypi.python.org/pypi/bobtemplates.odoo
* code repository: https://github.com/acsone/bobtemplates.odoo
* report issues at: https://github.com/acsone/bobtemplates.odoo/issues
