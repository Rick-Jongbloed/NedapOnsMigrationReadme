# **README – Nedap Ons API Endpoint Migratie (Employees Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Employees connector**
te upgraden naar de **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + F → (uitvouwen) Replace → Replace All**.

---

# **1. Wijzigingen per script**

---

## **1.1 employees-account-create.ps1**

1. Open het script.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek:

   ```
   /t/
   ```

4. Replace met:

   ```
   /v0/administration/
   ```

5. Replace All  
6. **Apply**

---

## **1.2 employees-account-update.ps1**

1. Open het script.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek:

   ```
   /t/
   ```

4. Replace met:

   ```
   /v0/administration/
   ```

5. Replace All  
6. **Apply**

---

# **2. Controle**

* In elk script hoort **exact één wijziging** plaats te vinden.
* Controleer dat het endpoint correct is vervangen.
* **Test de Employees connector via de force grant account en force update acties op een Nedap Ons medewerker**

Dit bevestigt dat de Employees connector de nieuwe v0-endpoints correct gebruikt.
