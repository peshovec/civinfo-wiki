Civinfo wiki diged and visualized

update:docker-compose: bitnami based, x86

medawiki_data has to have 1001:1001

mariadb_data has to have 1001:1001

they are tarred to preserve permission and make easier to just download


prepopulated from civinfodump.xml

prepopulated with imported images from archive.org

if exposed on the default ports, interesting links are:

http://127.0.0.1:8880/wiki/Index

http://127.0.0.1:8880/wiki/Special:AllPages

update: civinfo-wiki.yaml podman rootless (and arm:) ) friendly

mediwiki and mariadb containers from their official images

mediawiki permission has to be 33:33

mariadb permission has to be 999:999

in LocalSettings.php (mediwiki volume) wgDBServer has to be changed accrodingly, e.g $wgDBserver = "127.0.0.1";

If mediawiki and maridb are deployed in a rootless podman pod

podman play kube ./civinfo-wiki.yaml will bring up working instance

optional: mysql database version can be upgarded

optional: mediawiki schema version can be upgraded (update.php inside the maintenance folder)

