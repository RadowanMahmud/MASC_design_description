## MASC Web Interface
MASC web interafce is mainly based on django and java. The way it works is, we first collect  the jar file from MASC core with all the latest changes and updates that are need in order to properly integrate the web interface. Once the jar is ready it is stored in a particular location. The django app further utilizes this jar to carry out other tasks.

The django app is mainly divided into small modules. Some of the main modules are MASC Lab, MASC Engine, Tool Profiling, Plugins, Configuration Manager.

### DESIGN
The jar mainly acts as back end for the web interface, where as the django app plays the role of both the front end and the back end. When the user runs a specific task the django app utilizes the jar with appropriate commands and parameters and once the operation of the jar is finished it collects the results and stores them for further usage.

 #### Database
 We have used SQLite as the primary data source for the web interface. Datas like  configuration file related infos, plugin related infos, history of the privious ran processes etc are stored in the database. The main models are
 1. Process Log
 2. Property List (Configuration List)
 3. SOurce Code
 4. Plugins
 5. Tool Profile
 6. Reports

 #### Configuration Manager
 The user uploads a configuration file. It is stored in a particular location at the server. The path and file related informations are saved in the database. The user cann visualize and also update the contents of this files. This data is also used by other modules such as MASC Lab, MASC Engine, Tool profile. COnfigurations are the key to run MASC. So MASc web has introduced this interface using which users will be able to easily run any mutations according to their needs.

 #### MASC Lab
 MASC Lab can be labled as the playground for beginners exploring MASC> Users can test their configurations and see the mutations. MASC Lab only utilizes the MAIN Scope of MASC. The way it works is, users select a configuration , they get the option to update the configurations once they are happy with it MASC core is ran that is the jar is ran with specific parameters given in the configuration. The results are generated. The django app parses this results and displays them to the users. The user can also download the mutated codes. In that case the web interafce compresses this codes and makes them available to the users. This part uses the previously discussed configurations managers datas to indicate the user selected configuration.


#### MASC Engine
As mentioned before