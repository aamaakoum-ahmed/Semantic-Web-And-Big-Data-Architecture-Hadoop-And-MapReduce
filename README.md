[description.md](https://github.com/user-attachments/files/25372201/description.md)
[description.md](https://github.com/user-attachments/files/25372204/description.md)
**CSC 5003 – Semantic Web And Big Data Architecture
TELECOM SudParis** 
---





**https://www-inf.telecom-sudparis.eu/COURS/CSC5003/Supports/?page=exercices/hadoop\_mapreduce\&wrap=true**



**expertise acquise :**

\[x] Configuration d'un environnement Hadoop/SBT sous Docker.

\[x] Développement de Mappers/Reducers en Scala.

\[x] Gestion des dépendances avec build.sbt.

\[x] Résolution des erreurs de Classpath et de chemins HDFS.

\[x] Compréhension de l'orchestration YARN



**Mode Opératoire:**

Repartir sur une base propre avec Debian 12 sous Docker est une excellente idée. 

C'est beaucoup plus flexible pour apprendre.

Voici comment installer Java proprement sur Debian. 

On va installer l'OpenJDK 17 (la version stable actuelle la plus recommandée).



apt install -y openjdk-17-jdk



\# Pour eviter l'erreur "command not found" il faut dire a Debian 12 ou se trouve java

echo 'export JAVA\_HOME=$(readlink -f /usr/bin/java | sed "s:/bin/java::")' >> ~/.bashrc

echo 'export PATH=$PATH:$JAVA\_HOME/bin' >> ~/.bashrc

source ~/.bashrc



\# Pourquoi ??

Gestionnaire de paquets (apt) : on a les contrôles de tout.

Persistance : En modifiant le .bashrc, les commandes java (et plus tard jps) fonctionneront à chaque fois qu'on ouvert le terminal.



Téléchargement et décompression Hadoop

wget https://downloads.apache.org/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz

tar -xvzf hadoop-3.3.6.tar.gz

mv hadoop-3.3.6 /opt/Hadoop   # Déplacement vers un dossier plus simple



echo 'export JAVA\_HOME=/usr/lib/jvm/java-17-openjdk-amd64' >> ~/.bashrc

echo 'export HADOOP\_HOME=/opt/hadoop' >> ~/.bashrc

echo 'export PATH=$PATH:$HADOOP\_HOME/bin:$HADOOP\_HOME/sbin' >> ~/.bashrc

source ~/.bashrc  # Appliquer les changements immédiatement





**Rappel:** 

Action                          Commande Hadoop

Créer un dossier                hadoop fs -mkdir /data

Lister                          hadoop fs -ls /

Uploader                        hadoop fs -put README.txt /data

Lire                            hadoop fs -cat /data/README.txt

Supprimer                       hadoop fs -rm /data/README.txt

