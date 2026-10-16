# TP2 — JPA / Hibernate : Gestion des salles

Application Java illustrant la persistance JPA avec Hibernate : gestion de **salles** et des **utilisateurs** qui leur sont affectés (relation `@ManyToOne`), avec DAO génériques, service métier et tests JUnit sur une base H2 en mémoire.

## Technologies

| Élément | Version |
| --- | --- |
| Java | 11 |
| Maven | wrapper du projet (`pom.xml`) |
| Hibernate / JPA | 5.6.15.Final / JPA 2.2 |
| Base de données | H2 2.1.214 (en mémoire) |
| Tests | JUnit 4.13.2 |

## Structure du projet

| Chemin | Contenu |
| --- | --- |
| `src/main/java/com/example/jpa/entities` | Entités JPA `Salle` et `Utilisateur` |
| `src/main/java/com/example/jpa/dao` | `GenericDao` (CRUD générique), `SalleDao`, `UtilisateurDao` |
| `src/main/java/com/example/jpa/service` | `ServiceGestion` — façade métier exposée aux tests |
| `src/main/resources/META-INF/persistence.xml` | Unité de persistance `gestionPU` (Hibernate + H2) |
| `src/test/java/com/example/jpa/test` | `ServiceGestionTest` — tests d'intégration JUnit |

## Modèle de données

| Entité | Champs |
| --- | --- |
| `Salle` | `id` (généré), `nom` (unique, obligatoire), `capacite` |
| `Utilisateur` | `id` (généré), `nom`, `email` (unique), `salle` (`@ManyToOne`) |

## Lancer les tests

```bash
mvn test
```

Résultat attendu :

```text
Tests run: 3, Failures: 0, Errors: 0, Skipped: 0
```

## Screenshots

### 1. Structure du projet

![Structure du projet](screenshots/01-structure.png)

### 2. `pom.xml`

![Dépendances Maven](screenshots/02-pom.png)

### 3. `persistence.xml`

![Unité de persistance gestionPU](screenshots/03-persistence.png)

### 4. Entité `Salle`

![Entité Salle](screenshots/04-salle.png)

### 5. Entité `Utilisateur`

![Entité Utilisateur](screenshots/05-utilisateur.png)

### 6. `GenericDao`

![DAO générique](screenshots/06-generic-dao.png)

### 7. `SalleDao`

![DAO Salle](screenshots/07-salle-dao.png)

### 8. `UtilisateurDao`

![DAO Utilisateur](screenshots/08-utilisateur-dao.png)

### 9. `ServiceGestion`

![Service métier](screenshots/09-service.png)

### 10. Test JUnit

![Test ServiceGestionTest](screenshots/10-test.png)

### 11. Exécution Maven

![Résultat de mvn test](screenshots/11-mvn-test.png)
