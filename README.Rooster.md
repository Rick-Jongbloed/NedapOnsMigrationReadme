# **README – Nedap Ons API Endpoint Migratie (Rooster Connector)**

Deze README beschrijft de wijzigingen die nodig zijn om de **Nedap Ons Rooster connector**
te upgraden naar de nieuwe **Nedap Ons v0 API-endpoints**.

Alle wijzigingen worden **per script afzonderlijk** uitgevoerd via  
**Ctrl + H → Replace → Replace All**.

---

## **💡 Misschien beter om de laatste versie van de koppeling te plaatsen?**

Het is mogelijk **sneller** om:
1. Een **compare** te doen van de huidige scripts met de nieuwste versie
2. De **laatste versie van de source connector** te plaatsen (de nieuwe endpoints zijn daar al in verwerkt)

**Let op bij het overnemen van de nieuwe versie:**
- Vergeet niet ook de **configuratie template** mee te nemen
- Er is een nieuwe optie toegevoegd voor **expertise profiles (deskundigheden)**
- **Zet deze optie uit** als deze niet wordt gebruikt

---

# **1. Wijzigingen per script**

---

## **1.1 persons.ps1**

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
6. Druk **Ctrl + H** om Replace te openen.
7. Zoek:

   ```
   /t/teams/x-stream-connect/
   ```

8. Replace met:

   ```
   /v0/xstream/teams/
   ```

9. Replace All
10. Druk **Ctrl + H** om Replace te openen.
11. Zoek:

   ```
   /t/employees/x-stream-connect/
   ```

12. Replace met:

   ```
   /v0/xstream/employees/
   ```

13. Replace All
14. Druk **Ctrl + H** om Replace te openen.
15. Zoek:

   ```
   /t/employees/$($user.id)/planned_visits?valid_from=$script:strStartDatetime&valid_to=$script:strStopDatetime
   ```

16. Replace met:

   ```
   /v0/plannen_roosteren/planned_visits/by_employee_id/$($user.id)?from=$script:strStartDatetime&to=$script:strStopDatetime
   ```

17. Replace All
18. **Apply**

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
