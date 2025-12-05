# **README – Nedap Ons API Endpoint Migratie (Employees Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Employees connector** te upgraden naar de **Nedap Ons v0 API-endpoints**.

De Employees connector bevat twee scripts waarin een endpoint vervangen moet worden:

* `account create.ps1`
* `account update.ps1`

In beide scripts wordt dezelfde aanpassing uitgevoerd.

---

# **1. Wijzigingen per script**

## **1.1 employees-account-create.ps1**

Voer de volgende stappen uit:

1. Open het script.
2. Druk **Ctrl + F** en vouw het zoekvenster uit.
3. Zoek op:

   ```
   /t/
   ```
4. Vervang met:

   ```
   /v0/administration/
   ```
5. Klik op **Replace All**.
6. **Sla het script op door op Apply te klikken.**

---

## **1.2 employees-account-update.ps1**

Voer dezelfde stappen uit:

1. Open het script.
2. Druk **Ctrl + F** en vouw het zoekvenster uit.
3. Zoek op:

   ```
   /t/
   ```
4. Vervang met:

   ```
   /v0/administration/
   ```
5. Klik op **Replace All**.
6. **Sla het script op door op Apply te klikken.**

---

# **2. Controle**

* In elk script hoort **exact één wijziging** plaats te vinden.
* Controleer dat het endpoint correct is vervangen.
* **Test de connector via de business rule logica met een testmedewerker** om te bevestigen dat de create- en update-actie de juiste v0-endpoint aanroept.
