# **README – Nedap Ons API Endpoint Migratie (Rooster Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Nedap Ons Rooster connector**
te upgraden naar de nieuwe **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + H → Replace → Replace All**.

---

# **1. Wijzigingen per script**

---

## **1.1 persons.ps1**

---

### **1.1.1 Shift assignments – starting between**

1. Open het script.
2. Druk **Ctrl + H** om Replace te openen.
3. Zoek:

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

1. Druk **Ctrl + H** om Replace te openen.
2. Zoek:

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

1. Druk **Ctrl + H** om Replace te openen.
2. Zoek:

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

1. Druk **Ctrl + H** om Replace te openen.
2. Zoek:

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
2. Druk **Ctrl + H** om Replace te openen.
3. Zoek:

   ```
   /t/teams/x-stream-connect/
   ```

4. Replace met:

   ```
   /v0/xstream/teams/
   ```

5. Replace All
6. **Apply**
