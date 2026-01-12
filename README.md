# **Nedap Ons API Endpoint Migratie - Instructies**

Deze repository bevat **migratie-instructies** voor het upgraden van **HelloID Nedap Ons connectors** naar de nieuwe **Nedap Ons v0 API-endpoints**.

---

## **📋 Overzicht**

Nedap heeft de API-structuur aangepast en nieuwe endpoints geïntroduceerd onder `/v0/`. Alle bestaande connectors die gebruik maken van de oude `/t/` endpoints moeten worden gemigreerd.

Deze repository bevat **stap-voor-stap instructies** voor elke connector om de wijzigingen door te voeren via **Find & Replace** operaties in de PowerShell scripts.

---

## **🔧 Beschikbare Migratie-instructies**

| Connector | README Bestand | Beschrijving |
|-----------|----------------|--------------|
| **Employees** | [README.Employee.v1_en_v2.md](README.Employee.v1_en_v2.md) | Migratie voor Employees connector (PowerShell v1 en v2) |
| **Users** | [README.Users.v1.md](README.Users.v1.md) | Migratie voor Users connector inclusief permissions |
| **Rooster** | [README.Rooster.md](README.Rooster.md) | Migratie voor Rooster connector (planning & roostering) |
| **Deskundigheid** | [README.Deskundigheid.v1_en_v2.md](README.Deskundigheid.v1_en_v2.md) | Migratie voor Deskundigheid connector |
| **Weekkaart** | [README.Weekkaart.v1_en_v2.md](README.Weekkaart.v1_en_v2.md) | Migratie voor Weekkaart connector |

---

## **🚀 Hoe te gebruiken**

1. **Selecteer de juiste README** voor de connector die je wilt migreren
2. **Open de connector scripts** in je HelloID omgeving
3. **Volg de instructies** stap-voor-stap:
   - Gebruik **Ctrl + H** voor Find & Replace
   - Voer de aangegeven replacements uit
   - Klik op **Replace All**
   - Klik op **Apply** om de wijzigingen op te slaan
4. **Test de connector** na migratie

---

## **⚠️ Belangrijke opmerkingen**

- **Backup eerst**: Maak altijd een backup van je huidige connector configuratie voordat je begint
- **Test na migratie**: Test de connector grondig na het doorvoeren van de wijzigingen
- **Configuratie templates**: Sommige connectors hebben nieuwe configuratie-opties; vergeet niet de configuratie template bij te werken
- **Alternatieve methode**: Voor de Rooster connector kan het sneller zijn om de laatste versie van de source connector te plaatsen in plaats van handmatig te migreren

---

## **📝 Algemene migratie-patronen**

Alle endpoint changes die in scope zijn:

| Oud endpoint | Nieuw endpoint | Connector(s) |
|-------------|----------------|--------------|
| `/t/` | `/v0/administration/` | Employees, Users, Deskundigheid, Weekkaart |
| `/t/` | `/v0/` | Users (permission-role-list) |
| `/t/authorization/` | `/v0/authorization/` | Users (permissions) |
| `/t/employees/x-stream-connect/` | `/v0/xstream/employees/` | Employees, Deskundigheid, Weekkaart, Rooster |
| `/t/teams/x-stream-connect/` | `/v0/xstream/teams/` | Rooster |
| `/t/payroll/contracts/x-stream-connect/` | `/v0/xstream/contracts/` | Employees, Deskundigheid, Weekkaart |
| `/t/moves/shift_assignments/starting_between` | `/v0/plannen_roosteren/shift_assignments/starting_between` | Rooster |
| `/t/employees/$($user.id)/planned_visits?valid_from=$script:strStartDatetime&valid_to=$script:strStopDatetime` | `/v0/plannen_roosteren/planned_visits/by_employee_id/$($user.id)?from=$script:strStartDatetime&to=$script:strStopDatetime` | Rooster |

**Let op**: 
- Bij **Users permissions** altijd eerst `/t/authorization/` vervangen, daarna `/t/`
- Sommige endpoints hebben ook **parameter-wijzigingen**: `valid_from`/`valid_to` → `from`/`to`
- Sommige endpoints hebben **path-wijzigingen**: `/employees/{id}/planned_visits` → `/planned_visits/by_employee_id/{id}`

---

## **📞 Support**

Voor vragen over deze migratie-instructies, neem contact op met het Tools4ever support team.

---

**Laatste update:** Januari 2026
