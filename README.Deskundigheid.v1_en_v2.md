# **README – Nedap Ons API Endpoint Migratie (Deskundigheidsconnector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Deskundigheidsconnector**
te upgraden naar de **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + F → (uitvouwen) Replace → Replace All**.

---

# **1. Wijzigingen per script**

---

## **1.1 employees-account-create.ps1**  
*(HelloID PowerShell v1 en v2)*

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
*(HelloID PowerShell v1 en v2)*

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

## **1.3 import.ps1 (alleen PowerShell v2)**

Dit script is alleen van toepassing **indien er een import-script is geplaatst** in de
HelloID PowerShell v2-connector.

### **1.3.1 Employees – x-stream connect**

1. Open `import.ps1`.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek:

   ```
   /t/employees/x-stream-connect/
   ```

4. Replace met:

   ```
   /v0/xstream/employees/
   ```

5. Replace All  
6. **Apply**

---

### **1.3.2 Contracts – x-stream connect**

1. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
2. Ctrl + F → zoek:

   ```
   /t/payroll/contracts/x-stream-connect/
   ```

3. Replace met:

   ```
   /v0/xstream/contracts/
   ```

4. Replace All  
5. **Apply**

---

# **2. Controle**

* Controleer dat er geen oude `/t/` endpoints meer in de aangepaste scripts voorkomen.  
* **Test de deskundigheidsconnector via de business rule logica met een testmedewerker**:
  - account create  
  - account update  
  - (indien van toepassing) import  

Dit bevestigt dat de deskundigheidsconnector de nieuwe v0-endpoints correct gebruikt.
