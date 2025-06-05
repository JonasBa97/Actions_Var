# Variablen in GitHub-Actions und Jenkins

## Unterschiede GitHub Actions vs. Jenkins bei Variablen

- GitHub Actions verwendet `env:` auf verschiedenen Ebenen (global, job, step).
- Jenkins nutzt `environment {}` global oder in einzelnen Stages.
- GitHub Actions erlaubt einfache Nutzung von Secrets über `${{ secrets.NAME }}`, Jenkins über `credentials()`.

## Vor- und Nachteile von Secrets

| Tool            | Vorteile                              | Nachteile                          |
|-----------------|---------------------------------------|------------------------------------|
| GitHub Actions  | Einfach zu konfigurieren, sicher      | Keine Vorschau, nur über UI        |
| Jenkins         | Flexibel mit verschiedenen Typen      | Komplexere Einrichtung             |

## Anwendung von `set-output` und `credentials()`

- `set-output`: Ideal für Übergabe von Werten zwischen Steps in GitHub Actions.
- `credentials()`: Praktisch in Jenkins für API-Keys, Tokens, Passwörter – sicher und auditierbar.
