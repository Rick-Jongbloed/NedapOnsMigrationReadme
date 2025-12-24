# **README – Nedap Ons API Endpoint Migratie (Rooster Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Nedap Ons Rooster connector**
te upgraden naar de nieuwe **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + F → (uitvouwen) Replace → Replace All**.

---

# **1. Wijzigingen per script**

---

## **1.1 persons.ps1**

---

### **1.1.1 Shift assignments – starting between**

1. Open het script.
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.
3. Ctrl + F → zoek:

   ```
   /t/moves/shift_assignments/starting_between
   ```

4. Replace met:

   ```
   /v0/plannen_roosteren/shift_assignments/starting_between
   ```

5. Replace All
6. **Apply**

---

### **1.1.2 Teams – x-stream connect**

1. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.
2. Ctrl + F → zoek:

   ```
   /t/teams/x-stream-connect/
   ```

3. Replace met:

   ```
   /v0/xstream/teams/
   ```

4. Replace All
5. **Apply**

---

### **1.1.3 Employees – x-stream connect**

1. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.
2. Ctrl + F → zoek:

   ```
   /t/employees/x-stream-connect/
   ```

3. Replace met:

   ```
   /v0/xstream/employees/
   ```

4. Replace All
5. **Apply**

---

### **1.1.4 Planned visits per medewerker**

1. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.
2. Ctrl + F → zoek:

   ```
   /t/employees/$($user.id)/planned_visits?valid_from=$script:strStartDatetime&valid_to=$script:strStopDatetime
   ```

3. Replace met:

   ```
   /v0/plannen_roosteren/planned_visits/by_employee_id/$($user.id)?from=$script:strStartDatetime&to=$script:strStopDatetime
   ```

4. Replace All
5. **Apply**

---

## **1.2 departments.ps1**

---

### **1.2.1 Teams – x-stream connect**

1. Open het script.
2. Druk **Ctrl + F** en vouw het zoekvenster uit zodat *Replace* zichtbaar wordt.
3. Ctrl + F → zoek:

   ```
   /t/teams/x-stream-connect/
   ```

4. Replace met:

   ```
   /v0/xstream/teams/
   ```

5. Replace All
6. **Apply**

---

# **2. Controle**

* Controleer dat er geen oude `/t/` endpoints meer in de scripts voorkomen.
* **Test de Rooster connector door een import te doen en controleer daarna de wijzigingen in de snapshot data**.

Dit bevestigt dat de Rooster connector de nieuwe v0-endpoints correct gebruikt.
