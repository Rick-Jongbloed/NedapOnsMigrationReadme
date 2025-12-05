# **README – Nedap Ons API Endpoint Migratie (Users Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Users connector** te upgraden naar de nieuwe **Nedap Ons v0 API-endpoints**.

De Users connector bevat de volgende scriptcategorieën:

* **Account create**
* **Account update**
* **Permission List script (role)**
* **Permission AllInOne script (role)**
* **Permission script Grant (defaultscope)**
* **Permission script Update (defaultscope)**
* **Permission script Revoke (defaultscope)**
* **Resource script**

Voor alle permissiescripts geldt:

1. **Eerst vervangen:**
   `/t/authorization/` → `/v0/authorization/`
2. **Daarna vervangen:**
   `/t/` → `/v0/administration/`

Alle vervangingen worden **per script afzonderlijk** gedaan via Ctrl + F → Replace All.

---

# **1. Scripts per categorie**

## **1.1 Account create**

* `users-account-create.ps1`

## **1.2 Account update**

* `users-account-update.ps1`

## **1.3 Permission List script (role)**

* `users-permission-role-list.ps1`

## **1.4 Permission AllInOne script (role)**

* `users-permission-role.ps1`

## **1.5 Permission script Grant (defaultscope)**

* `users-permission-defaultscope-grant.ps1`

## **1.6 Permission script Update (defaultscope)**

* `users-permission-defaultscope-update.ps1`

## **1.7 Permission script Revoke (defaultscope)**

* `users-permission-defaultscope-revoke.ps1`

## **1.8 Resource script**

* `users-resource.ps1`

---

# **2. Wijzigingen per script**

---

## **2.1 users account create.ps1**

1. Open het script.
2. Ctrl + F → zoek op:

   ```
   /t/
   ```
3. Vervang met:

   ```
   /v0/administration/
   ```
4. Replace All.
5. **Apply.**

---

## **2.2 users account update.ps1**

Zelfde stappen:

1. Open het script.
2. Ctrl + F → zoek `/t/`
3. Replace met `/v0/administration/`
4. Replace All
5. **Apply**

---

## **2.3 users permission role list.ps1**

**Permission List script (role)**

1. Open het script.
2. **Eerst:**

   * Ctrl + F → zoek `/t/authorization/`
   * Replace met `/v0/authorization/`
   * Replace All
3. **Daarna:**

   * Ctrl + F → zoek `/t/`
   * Replace met `/v0/administration/`
   * Replace All
4. **Apply**

---

## **2.4 users permission role.ps1**

**Permission AllInOne script (role)**

1. Open het script.
2. **Eerst:** `/t/authorization/` → `/v0/authorization/` (Replace All)
3. **Daarna:** `/t/` → `/v0/administration/` (Replace All)
4. **Apply**

---

## **2.5 users permission defaultscope grant.ps1**

**Permission script Grant (defaultscope)**

1. Open het script.
2. **Eerst:** `/t/authorization/` → `/v0/authorization/`
3. **Daarna:** `/t/` → `/v0/administration/`
4. Replace All
5. **Apply**

---

## **2.6 users permission defaultscope update.ps1**

**Permission script Update (defaultscope)**

1. Open het script.
2. **Eerst:** `/t/authorization/` → `/v0/authorization/`
3. **Daarna:** `/t/` → `/v0/administration/`
4. Replace All
5. **Apply**

---

## **2.7 users permission defaultscope revoke.ps1**

**Permission script Revoke (defaultscope)**

1. Open het script.
2. **Eerst:** `/t/authorization/` → `/v0/authorization/`
3. **Daarna:** `/t/` → `/v0/administration/`
4. Replace All
5. **Apply**

---

## **2.8 users resource.ps1**

**Resource script**

1. Open het script.
2. Ctrl + F → zoek op: `/t/`
3. Replace met: `/v0/administration/`
4. Replace All
5. **Apply**

*(Geen authorization-stap tenzij dit script onverwacht een authorization-call bevat.)*

---

# **3. Controle**

* Controleer dat alle endpoints correct zijn omgezet.
* **Test de Users connector via de business rule logica met een testmedewerker**:

Dit bevestigt dat de connector alle nieuwe v0-endpoints correct gebruikt.
