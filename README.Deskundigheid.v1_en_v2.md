# **README – Nedap Ons API Endpoint Migratie (Deskundigheidsconnector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Deskundigheidsconnector**
te upgraden naar de **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + H → Replace → Replace All**.

---

# **1. Wijzigingen per script**

---

## **1.1 deskundigheden-account-create.ps1**  
*(HelloID PowerShell v1 en v2)*

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/
   ```

4. Replace met:

   ```
   /v0/administration/
   ```

5. Replace All  
6. Klik op de **preview knop** om te controleren of de wijzigingen correct zijn doorgevoerd
7. **Apply**

---

## **1.2 deskundigheden-account-update.ps1**  
*(HelloID PowerShell v1 en v2)*

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/
   ```

4. Replace met:

   ```
   /v0/administration/
   ```

5. Replace All  
6. Klik op de **preview knop** om te controleren of de wijzigingen correct zijn doorgevoerd
7. **Apply**

---

## **1.3 import.ps1 (alleen PowerShell v2)**

Dit script is alleen van toepassing **indien er een import-script is geplaatst** in de
HelloID PowerShell v2-connector.

1. Open `import.ps1`.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/employees/x-stream-connect/
   ```

4. Replace met:

   ```
   /v0/xstream/employees/
   ```

5. Replace All  
6. **Apply**

7. Druk **Ctrl + H** om Replace te openen.  
8. Zoek:

   ```
   /t/payroll/contracts/x-stream-connect/
   ```

9. Replace met:

   ```
   /v0/xstream/contracts/
   ```

10. Replace All  
11. **Apply**
