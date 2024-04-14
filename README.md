# DotNetEnglishP3
Dépôt de l’étudiant Seynabou DIOP pour le projet 3 du parcours Développeur Back-End .NET. Afin d'être au plus proche d'une situation professionnelle réelle, le code dans ce dépôt est en anglais.

Ce projet possède une base de données intégrée qui sera créée lorsque l’application sera exécutée pour la première fois. Pour la créer correctement, vous devez satisfaire aux prérequis ci-dessous et mettre à jour les chaînes de connexion pour qu’elles pointent vers le serveur MSSQL qui est exécuté sur votre PC en local.

**Prérequis** : MSSQL Developer doit être installé avec Microsoft SQL Server Management Studio (SSMS).

MSSQL : https://www.microsoft.com/fr-fr/sql-server/sql-server-downloads

SSMS : https://docs.microsoft.com/fr-fr/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16

*Remarque : les versions antérieures de MSSQL Server devraient fonctionner sans problèmes, mais elles n’ont pas été testées.

*Dans le projet P3AddNewFunctionalityDotNetCore, ouvrez le fichier appsettings.json.*

Vous avez la section ConnectionStrings qui définit les chaînes de connexion pour les 2 bases de données utilisées dans cette application.

      "ConnectionStrings":
      {    
        "EhodBDD": "Server=localhost\\MSSQLSERVER01;Database=EhodBoutiqueEnLigne;Trusted_Connection=True;MultipleActiveResultSets=true",
        "EhodVLUtilisateurs": "Server=localhost\\MSSQLSERVER01;Database=Identity;Trusted_Connection=True;MultipleActiveResultSets=true"
      }
  
**EhodBDD** - chaîne de connexion à la base de données de l’application.

**EhodVLUtilisateurs** - chaîne de connexion à la base de données des utilisateurs. Il s’agit d’une base de données indépendante, car une organisation utilise généralement plusieurs applications différentes. Au lieu
de laisser chaque application définir ses propres utilisateurs (et plusieurs identifiants et mots de passe différents pour un seul utilisateur), une organisation peut disposer d’une base de données utilisateur unique et utiliser des autorisations et des rôles pour définir les applications auxquelles l’utilisateur a accès. De cette façon, un utilisateur peut accéder à toutes les applications de l’organisation avec le même identifiant et le même mot de passe, mais il n’aura accès qu’aux bases de données et aux actions définies dans la base de données des utilisateurs.

Il existe des versions différentes de MSSQL (veuillez utiliser MSSQL pour ce projet et non une autre base de données). Lorsque vous configurez le serveur de base de données, diverses options modifient la configuration de sorte que les chaînes de connexion définies peuvent ne pas fonctionner.

Les chaînes de connexion définies dans le projet sont configurées pour MSSQL Server Standard 2019. L’installation n’a pas créé de nom d’instance, le serveur est donc simplement désigné par « . », qui désigne l’instance par défaut de MSSQL Server fonctionnant sur la machine actuelle. Pendant l’installation, c’est l’utilisateur intégré de Windows qui est configuré dans le serveur MSSQL par défaut.


**Ajouts au Projet**
Ce projet a été enrichi de plusieurs fonctionnalités et améliorations, notamment :    

+ Tests Unitaires pour la Validation des Modèles : 
   Des tests unitaires ont été ajoutés pour valider les modèles de données. Cela garantit que les données saisies par l'utilisateur sont correctement validées avant d'être traitées par l'application.

+Internationalisation : 
  L'internationalisation a été implémentée pour prendre en charge plusieurs langues dans l'application. Les messages d'erreur et autres textes statiques ont été externalisés dans des fichiers de ressources pour permettre une traduction facile. La prise en charge de la langue wolof a été ajoutée.

+Emplacement des Messages d'Erreurs Personnalisés  :  
   Les messages d'erreur personnalisés ont été déplacés dans des fichiers de ressources dédiés pour une gestion plus efficace. Egalement leur emplacement a été gérée pour qu'ils soient situés au niveau des champs concernés.