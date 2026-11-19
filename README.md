# SEG3502 — Laboratoire 9

Cette API convertit des températures entre Celsius et Fahrenheit. Spring Security vérifie les identifiants à chaque requête avec HTTP Basic. Les deux comptes sont configurés en mémoire.

## Démarrage

Avec Java 21, ouvrir un terminal à la racine du projet et lancer `./gradlew bootRun` (Windows : `gradlew.bat bootRun`).

## Vérification

Dans un deuxième terminal, exécuter les commandes suivantes.

```bash
API=http://localhost:8080/temperature-converter

# 200 et 122.0
curl -i -u user1:pass1 "$API/celsius-fahrenheit/50"

# 200 et 50.0
curl -i -u user2:pass2 "$API/fahrenheit-celsius/122"

# 401 sans identifiants
curl -i "$API/celsius-fahrenheit/50"

# 401 avec un mot de passe incorrect
curl -i -u user1:incorrect "$API/fahrenheit-celsius/122"
```
