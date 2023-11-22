# gestion_utilisateurs

Je souhaite ajouter une fonctionnalité à notre projet de gestion des biens immobiliers. Pour ce faire, nous allons développer cela dans ce repository avant de l'intégrer dans le projet principal une fois qu'elle sera opérationnelle.

Pour cette fonctionnalité, nous aurons besoin de deux tables : 'users', qui aura des attributs tels que name, email, password, rôle (admin, user), et 'Utilisateurs', qui aura les mêmes attributs avec une clé étrangère faisant référence à la table 'users'. Un 'user' avec le rôle admin peut gérer plusieurs 'utilisateurs', mais un 'utilisateur' n'est géré que par un 'user'. Par gestion, on entend la réalisation des opérations CRUD. Nous aurons également une déclencheur (trigger) au niveau de la base de données qui nous permettra d'ajouter ou de mettre à jour la table 'users' en se basant sur la table 'utilisateurs'. La suppression d'un 'utilisateur' entraînera une suppression en cascade de tout ce qui lui est lié.

En ce qui concerne les autorisations, nous devrons utiliser les politiques (policies) :

Le CRUD d'un 'user' ne peut être effectué que par lui-même ou par l'admin qui l'a créé.
L'accès aux vues permettant de gérer les utilisateurs doit être sécurisé (seuls les utilisateurs avec un rôle d'admin peuvent y accéder).
