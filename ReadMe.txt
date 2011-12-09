Getting started with Albero
==================

Install java version 1.5 or 1.6.

---------------
Installation
---------------
Install the Mysql database
Create a schema named "albero"
create a user named "albero" with a blank password

Run the following SQL script:
USE albero;
DROP TABLE IF EXISTS trees;
CREATE TABLE trees (code varchar(255), parser varchar(255), tree text);

Populate the database with a tree
INSERT INTO `trees`
        VALUES('demo', 'groovy',
        'tree(code:''demo''){model{isWerkend(''text'')};nodes{multipleChoiceQuestion(labelText:''Werkt het?'',answers:''isWerkend'',options:[''ja'',''nee''])};results{model{uitslag(''text'')};rules{rule{when isWerkend.is(''ja'');set''uitslag'',''eureka!!''};rule{when isWerkend.is(''nee'');set ''uitslag'',''leugenaar!''}}}}');
---------------
Usage
---------------

Unix / OSX
run gradlew jettyRun (to run in the embedden jetty containter)
run gradlew war (to create a war archive to deploy on different containers)

Windows
Unix / OSX
run gradlew.bat jettyRun (to run in the embedden jetty containter)
run gradlew.bat war (to create a war archive to deploy on different containers)

---------------
License
---------------

Albero is licensed under the Apache License, Version 2.0. You can find the
terms and conditions for use, reproduction, and distribution of Albero in the
LICENSE file in the distribution or at
http://www.apache.org/licenses/LICENSE-2.0.
