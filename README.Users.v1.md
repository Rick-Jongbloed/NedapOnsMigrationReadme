# **README – Nedap Ons API Endpoint Migratie (Users Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Users connector**
te upgraden naar de nieuwe **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + F → (uitvouwen) Replace → Replace All**.

Voor **alle permissiescripts** geldt altijd:

1. **Eerst vervangen:**  
   `/t/authorization/` → `/v0/authorization/`
2. **Daarna vervangen:**  
   `/t/` → `/v0/administration/`

---

# **1. Wijzigingen per script**

---

## **1.1 users-account-create.ps1**

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

## **1.2 users-account-update.ps1**

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

## **1.3 users-permission-role-list.ps1**  
**Permission List script (role)**

1. Open het script.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek:

   ```
   /t/authorization/
   ```

4. Replace met:

   ```
   /v0/authorization/
   ```

5. Replace All  
6. Ctrl + F → zoek:

   ```
   /t/
   ```

7. Replace met:

   ```
   /v0/administration/
   ```

8. Replace All  
9. **Apply**

---

## **1.4 users-permission-role.ps1**  
**Permission AllInOne script (role)**

1. Open het script.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek `/t/authorization/` → replace met `/v0/authorization/` → Replace All  
4. Ctrl + F → zoek `/t/` → replace met `/v0/administration/` → Replace All  
5. **Apply**

---

## **1.5 users-permission-defaultscope-grant.ps1**  
**Permission script Grant (defaultscope)**

1. Open het script.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek `/t/authorization/` → replace met `/v0/authorization/` → Replace All  
4. Ctrl + F → zoek `/t/` → replace met `/v0/administration/` → Replace All  
5. **Apply**

---

## **1.6 users-permission-defaultscope-update.ps1**  
**Permission script Update (defaultscope)**

1. Open het script.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek `/t/authorization/` → replace met `/v0/authorization/` → Replace All  
4. Ctrl + F → zoek `/t/` → replace met `/v0/administration/` → Replace All  
5. **Apply**

---

## **1.7 users-permission-defaultscope-revoke.ps1**  
**Permission script Revoke (defaultscope)**

1. Open het script.  
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.  
3. Ctrl + F → zoek `/t/authorization/` → replace met `/v0/authorization/` → Replace All  
4. Ctrl + F → zoek `/t/` → replace met `/v0/administration/` → Replace All  
5. **Apply**

---

## **1.8 users-resource.ps1**  
**Resource script**

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

*(Geen authorization-stap tenzij dit script onverwacht een authorization-call bevat.)*

---

# **2. Controle**

* Controleer dat alle endpoints correct zijn omgezet.  
* **Test de Users connector via een retry grant en force update account, retry grant en force update permission defaultscope en retry grant en force update permission role**.

Dit bevestigt dat de Users connector de nieuwe v0-endpoints correct gebruikt.
