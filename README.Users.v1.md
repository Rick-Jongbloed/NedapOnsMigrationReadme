# **README – Nedap Ons API Endpoint Migratie (Users Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Users connector**
te upgraden naar de nieuwe **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + H → Replace → Replace All**.

---

# **1. STAP 1: Bepaal welke koppeling variant je hebt**

**LET OP:** Er zijn twee verschillende varianten van de Users koppeling. Het is belangrijk om eerst te bepalen welke variant je hebt voordat je begint met de migratie.

### **Detectiemethode:**
1. Open **users-account-create.ps1**
2. Druk **Ctrl + H** 
3. Type in het zoekveld: `/t/`
4. **Kijk naar het aantal resultaten** (wordt rechtsboven in het zoekvenster getoond)

### **Bepaal je variant:**

- **Als er 4 resultaten zijn** → Je hebt een **oude koppeling variant (2022-2024)**  
  ➜ **Ga naar sectie 2** voor de procedure

- **Als er minder resultaten zijn** → Je hebt de **normale/standaard variant**  
  ➜ **Ga naar sectie 3** voor de procedure

---

# **2. Procedure voor OUDE koppeling variant (2022-2024)**

Bij deze oude variant hebben de user scripts (create, update, delete) de default scope **in de usersscripts zelf** verwerkt, niet in losse permissiescripts.

### **Voor alle permissiescripts geldt:**

1. **Eerst vervangen:**  
   `/t/authorization/` → `/v0/authorization/`
2. **Daarna vervangen:**  
   `/t/` → `/v0/administration/`

---

Voor deze oude variant moet je bij de **users-account-create.ps1**, **users-account-update.ps1** en **users-account-delete.ps1** (indien aanwezig) scripts **dezelfde procedure** volgen als bij de defaultscope permissiescripts.

---

<details>
<summary>

## **2.1 users-account-create.ps1 (oude variant)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/authorization/
   ```

4. Replace met:

   ```
   /v0/authorization/
   ```

5. Replace All  
6. Zoek:

   ```
   /t/
   ```

7. Replace met:

   ```
   /v0/administration/
   ```

8. Replace All  
9. **Apply**

</details>

---

<details>
<summary>

## **2.2 users-account-update.ps1 (oude variant)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/authorization/
   ```

4. Replace met:

   ```
   /v0/authorization/
   ```

5. Replace All  
6. Zoek:

   ```
   /t/
   ```

7. Replace met:

   ```
   /v0/administration/
   ```

8. Replace All  
9. **Apply**

</details>

---

<details>
<summary>

## **2.3 users-account-delete.ps1 (oude variant)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/
   ```

4. Replace met:

   ```
   /v0/
   ```

5. Replace All  
6. **Apply**

</details>

---

## **2.4 Overige scripts (oude variant)**

**Voor de overige scripts volg je de standaard procedure uit [sectie 3](#33-users-permission-role-listps1)** (normale variant):
- 2.4.1 → Zie [sectie 3.3: users-permission-role-list.ps1](#33-users-permission-role-listps1)
- 2.4.2 → Zie [sectie 3.4: users-permission-role.ps1](#34-users-permission-roleps1)
- 2.4.6 → Zie [sectie 3.8: users-resource.ps1](#38-users-resourceps1)

---

# **3. Procedure voor NORMALE/STANDAARD variant**

Bij deze normale variant zijn de default scope functies in **losse permissiescripts** verwerkt.

### **Voor alle permissiescripts (niet user-account scripts) geldt:**

1. **Eerst vervangen:**  
   `/t/authorization/` → `/v0/authorization/`
2. **Daarna vervangen:**  
   `/t/` → `/v0/administration/`

---

<details>
<summary>

## **3.1 users-account-create.ps1**

</summary>

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
6. **Apply**

</details>

---

<details>
<summary>

## **3.2 users-account-update.ps1**

</summary>

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
6. **Apply**

</details>

---

<details>
<summary>

## **3.3 users-permission-role-list.ps1**  
**Permission List script (role)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/
   ```

4. Replace met:

   ```
   /v0/
   ```

5. Replace All  
6. **Apply**

</details>

---

<details>
<summary>

## **3.4 users-permission-role.ps1**  
**Permission AllInOne script (role)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/authorization/
   ```

4. Replace met:

   ```
   /v0/authorization/
   ```

5. Replace All  
6. Zoek:

   ```
   /t/
   ```

7. Replace met:

   ```
   /v0/administration/
   ```

8. Replace All  
9. **Apply**

</details>

---

<details>
<summary>

## **3.5 users-permission-defaultscope-grant.ps1**  
**Permission script Grant (defaultscope)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/authorization/
   ```

4. Replace met:

   ```
   /v0/authorization/
   ```

5. Replace All  
6. Zoek:

   ```
   /t/
   ```

7. Replace met:

   ```
   /v0/administration/
   ```

8. Replace All  
9. **Apply**

</details>

---

<details>
<summary>

## **3.6 users-permission-defaultscope-update.ps1**  
**Permission script Update (defaultscope)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/authorization/
   ```

4. Replace met:

   ```
   /v0/authorization/
   ```

5. Replace All  
6. Zoek:

   ```
   /t/
   ```

7. Replace met:

   ```
   /v0/administration/
   ```

8. Replace All  
9. **Apply**

</details>

---

<details>
<summary>

## **3.7 users-permission-defaultscope-revoke.ps1**  
**Permission script Revoke (defaultscope)**

</summary>

1. Open het script.  
2. Druk **Ctrl + H** om Replace te openen.  
3. Zoek:

   ```
   /t/authorization/
   ```

4. Replace met:

   ```
   /v0/authorization/
   ```

5. Replace All  
6. Zoek:

   ```
   /t/
   ```

7. Replace met:

   ```
   /v0/administration/
   ```

8. Replace All  
9. **Apply**

</details>

---

<details>
<summary>

## **3.8 users-resource.ps1**  
**Resource script**

</summary>

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
6. **Apply**

</details>