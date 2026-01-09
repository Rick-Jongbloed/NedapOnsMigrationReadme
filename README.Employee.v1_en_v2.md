# **README – Nedap Ons API Endpoint Migratie (Employees Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Employees connector**
te upgraden naar de **Nedap Ons v0 API-endpoints**.

Alle wijzigingen gelden voor zowel de **HelloID PowerShell v1** als **PowerShell v2** connectorversies.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + H → Replace → Replace All**.

---

# **1. Wijzigingen per script**

---

## **1.1 employees-account-create.ps1**  
*(PowerShell v1 en v2)*

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

## **1.2 employees-account-update.ps1**  
*(PowerShell v1 en v2)*

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

## **1.3 employees-account-delete.ps1**  
*(PowerShell v1 en v2)*

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

## **1.4 import.ps1 (alleen PowerShell v2)**

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
