---
title: pascom Server 19
description: Mit dem pascom Release 19 stehen Ihnen eine Vielzahl an neuen Funktionen zur Verfügung.
weight: 995
---

## Highlights

{{< youtube eLfIiR32nEc >}}

### pascom Video Konferenzen 

55% der Kommunikation erfolgt visuell. Mit der nativen Videointegration von pascom ist das Starten einer Konferenz auf Ihrem Desktop oder Mobilgerät nur einen Klick entfernt. Sie benötigen weder zusätzliche Software noch können Probleme mit inkompatiblen Browsern auftreten.

![Video Konferenz](pascom-19-video-desktop-conference.png)

### pascom Web Konferenzen

Online Meetings, Remote Präsentationen und Support: Mit dem neuen pascom Web Client können pascom Nutzer ihre Kunden, Geschäftspartner und Stakeholder, direkt im bevorzugten Browser zur Teilnahme an Online Web Meetings einladen, ohne dass zusätzliche Software oder Hardware erforderlich ist. Der pascom Web Client ist mit allen führenden Webbrowsern kompatibel und ein hervorragendes Tool für Kundenservice und Kundenbindung. Profitieren Sie von einer sicheren, flexiblen und benutzerfreundlichen Videokonferenzlösung. 

![pascom Web Konferenzen](pascom-web-conferencing.png)

### pascom Screensharing

Ein Bild sagt mehr als tausend Worte. Die neue Screensharing Funktion steht auf allen Geräten und Plattformen zur Verfügung und stellt sicher, dass auch Außendienstmitarbeiter jederzeit Dokumente und Präsentationen mit Ihren Kollegen teilen können.

![Screensharing](pascom-screensharing.png)

### pascom Gruppen mit Audio, Video und Chat

Verbessern Sie die Teamzusammenarbeit mithilfe von Gruppen. Aufbauend auf unserem “on the fly” Gruppen-Chat ist es mit pascom 19 jetzt jedem Benutzer möglich, permanente Gruppen zu erstellen. Ermöglichen Sie Ihren Mitarbeitern sich mühelos per Chat, Audio oder Video austauschen.

![pascom Gruppen](pascom-collaboration-team-messaging.png)

## Wichtige Änderungen

{{% notice changes %}}  
In diesem Abschnitt werden die Änderungen erläutert, die Sie bei der Migration auf pascom 19 berücksichtigen müssen
{{% /notice %}}

* **Snom Pickups** wurden auf `DURCHWAHL|*8` Notation umgestellt. Siehe [Snom Tischtelefone]({{< ref "/endpoints/snom#tasten-belegen-über-das-web-ui" >}}).
* **Trunk Failover** (Ämterketten) ersatzlos gelöscht. Keine Migration und keine direkte Problemumgehung. Der Support kann bei Bedarf mit einem ausgehenden Skript helfen.  
* **IAX-Amtsleitungen** ersatzlos gelöscht.   
* **Swap** ist jetzt standardmäßig deaktiviert. Dadurch können virtualisierte Setups mit weniger als 1 GB Arbeitsspeicher beschädigt werden. Konfigurieren Sie in diesem Fall mehr Arbeitsspeicher.  
* **Anrufgruppen** werden automatisch in Teams umgewandelt. Die Anrufgruppenfunktion wurde entfernt, und stattdessen sollten Teams konfiguriert werden.  
* Portforwarding für **UDP 3478** ist Voraussetzung, andernfalls funktioniert **Video** nicht.
* **Beronet Gateways** müssen neu provisioniert werden.
* **pascom SOHO Server** ist nicht mehr kompatibel. Bitte führen Sie ein Hardware-Upgrade auf die [pascom Appliance]({{< ref "server/appliance" >}}) durch oder nutzen Sie die pascom.cloud.
* **Automatische Ämter Updates** werden für Telekom, peoplefone (DE, AT, CH), HFO, Sipgate Trunking, RKom, t-m-net, sipcallch, seabix, mnet, easybell und qsc/plusnet durchgeführt. Bitte prüfen Sie Ihr Amt nach dem Update.
* **Cronjob Skript (vorher/nachher)** wird nicht mehr unterstützt
* Ämter, bei denen eine **eigene Vorlage** vorhanden ist,  bekommen diese automatisch wieder zugewiesen. Eventuelle Anpassungen über eine generische Vorlage werden verworfen.


## Bekannte Probleme

{{% notice issues %}}
Diese Probleme sind uns bekannt und wir arbeiten bereits an einer Lösung
{{% /notice %}}

* Onsite Telekom Ämter funktionieren nur wenn ein Outbound Proxy genutzt wird. Wählen Sie hierzu statt "default / NAT" das entsprechende Schnittstelle im Amt aus.

## Release 19.08 (24.06.2020)

**Auf einen Blick**

* Gelegentliche Probleme mit eingeschränkter Funktionalität bei Mobile Clients behoben

**ÄNDERUNGEN**

- [MD-12411] XMPP error on unpair a mobile client

## Release 19.07 (10.06.2020)

**Auf einen Blick**

* Vendor Provisioning für Snom und Yealink
* Anzeigenamen für Geräte 
* Anlegen von Geräten verbessert
* Rufnummernanzeige bei Snom DECT Gateways verbessert
* Transfers mit Yealink und Grandstreams optimiert
* Probleme mit nicht angezeigten Anrufen bei Abwürfen über Aktionen behoben
* Sprache der Roaming-Ansagen ist nun richtig
* QR Code für Mobile Client Pairing bleibt wieder für den konfigurierten Zeitraum gültig
* Probleme mit Sonderzeichen im Anzeigenamen der Benutzer behoben

**ÄNDERUNGEN**

- [MD-8349] - Improve "add device" ui workflow and add clean, translated device descriptions
- [MD-11718] - Revokable provisioning urls
- [MD-11752] - Integrate vendor provisionig service for snom phones
- [MD-11928] - Push correctly resolved number to mobile apps
- [MD-11941] - CSUI shows 'Subscription paired' after moving back from mypascom
- [MD-11955] - Introduce Display Name for devices
- [MD-11958] - Status of pascom support access button in CSUI is always off
- [MD-12043] - Refactor and cleanup xmppserver internal apis and spring dependencies
- [MD-12130] - Replace apache with nginx in pbx instances
- [MD-12142] - Missing call activity after drop via action when condition is used
- [MD-12163] - Optimize xmpp API to use device id instead of name
- [MD-12165] - Apache not started after reload via certmanager
- [MD-12184] - Beronet trunk shows anonymous for incoming calls
- [MD-12186] - Snom M700 handset shows %23 instead of # and number during calls
- [MD-12229] - User can't connect client because of broken db entries in 009ext_extension
- [MD-12239] - Can't delete connector profile because operation is not permitted
- [MD-12262] - CallerID not updated after transfer with some Yealink and Grandsteam phones
- [MD-12263] - Switch to adoptopenjdk openJ9 jvm for more efficiency
- [MD-12273] - Show proper busy text instead of technical cause code on yealink phones
- [MD-12286] - Wrong prompt language when roaming to a location
- [MD-12289] - Console error if you hover over the weblient while the fadeout animation is running
- [MD-12291] - Improve webclient chat
- [MD-12297] - QR code/pairing not valid for more than ~ 60 seconds
- [MD-12299] - Additional account in SIP trunk doesn't apply trunk template
- [MD-12301] - Restrict webclient also for legacy perpetual licenses, named users
- [MD-12302] - Web client states that there is no dial-in number in error messages
- [MD-12303] - Web client can use more licenses than allowed
- [MD-12307] - Trunk Transport option has no effect
- [MD-12312] - Reduce strain on consul servers by restricting csd leadership to fewer machines
- [MD-12317] - Privilege escalation through cron jobs
- [MD-12318] - Improve user wizard desktop phone page, add vendor provisioning support
- [MD-12325] - Improve number in SIP trunk from header
- [MD-12333] - PJSIP header doesn't appear in sip traffic when set via team action
- [MD-12335] - Create a device and assign it to a user or location within the same webform
- [MD-12338] - Telekom SIP trunk Clip no screening is not working
- [MD-12339] - OpenVPN service crashes, is not restarted automatically
- [MD-12340] - Change Snom M700 provisioning template
- [MD-12345] - Can not upload and restore big backups into pbx instance
- [MD-12348] - Enforce trunk templates on each pbx update
- [MD-12351] - Deactivate sip 302 redirect for easybell trunk template
- [MD-12352] - Change sipcall.ch trunk template for CLIP no screening
- [MD-12353] - Improve mute button handling in web client
- [MD-12356] - QR code on instance UI can be used for multiple pairings
- [MD-12358] - Broken hint for *74 call forwardings
- [MD-12359] - Remove broken/unnecessary swap creation logic in md-xmppserver patchscript
- [MD-12384] - Can't leave full screen mode in web client with Safari

## Release 19.06 (28.04.2020)

**Auf einen Blick**

* pascom Web Client für Web-Konferenzen
* Gigaset DECT N870 Gateway wird unterstützt
* Ämter Vorlagen werden nun automatisch bei Updates aktualisiert
* Chat-History kann wieder beschränkt und aufgeräumt werden
* Systemsprache ist in der Instanz konfigurierbar
* Connector Performance wurde verbessert

**ÄNDERUNGEN:**

- [MD-11661] - Snom M700 provisioning restarts all multicell senders
- [MD-11960] - Payload data has wrong key
- [MD-12033] - Fax extension invalid after change via connector
- [MD-12055] - Auto created Peoplefone trunk during setup has wrong options
- [MD-12069] - Delete contact in roster (favorite) if related phonebook entry gets deleted
- [MD-12092] - Fix warnings in various jobs
- [MD-12107] - Show correct language when adding a trunk from a template
- [MD-12126] - Change mnet template pjsip options
- [MD-12144] - Instance web UI shows wrong phone state
- [MD-12155] - Improve outbound proxy, ensure to resolve internal alias ip numbers
- [MD-12159] - Php segfault because of protobuf version incompatiblity
- [MD-12161] - Different container versions are confusing CSUI version checks
- [MD-12170] - Loader pattern is invalid
- [MD-12181] - Handle SIP AOC info requests, fix dropped calls on rkom trunks
- [MD-12182] - Can't delete group participants or leave group
- [MD-12206] - Rtc media handles locking and cleanup
- [MD-12213] - Show one provisioning URL per host-name
- [MD-12236] - Stop to enforce opus for desktop client calls, fallback to alaw for trunk calls
- [MD-12242] - Lost calls after 30 minutes on outbound proxy due to session timers
- [MD-5675] - Increase Connector Performance, Step 1
- [MD-8427] - Cleanup dialplan loop warnings on apply telephony
- [MD-10779] - Unify system language, web ui language and prompts into one data model
- [MD-11169] - Rate limit API requests
- [MD-11358] - Managed, updateable, sip trunk profiles
- [MD-11455] - Implement Gigaset N870 DECT multicell system
- [MD-11925] - Add more instance level metrics to prometheus
- [MD-12027] - Cleanup chat in event stream
- [MD-12062] - Update Seabix logo in trunk template
- [MD-12116] - Xmpp resource loader could be more efficient
- [MD-12156] - Use python3 for installation process
- [MD-12157] - Upgrade go to 1.13.X
- [MD-12175] - Remove php proto generated files from git repo
- [MD-12216] - Enhance PushManager to lower priority for chat messages pushed to android devices
- [MD-12224] - Reduce idle cpu consumption in the xmppserver by reducing modules, ports
- [MD-12244] - Add a parameter for video publisher soft limit
- [MD-12252] - Change sip host in plusnet template and migrate it automatically
- [MD-12269] - Raise asterisk open file limit

## Release 19.05 (11.03.2020)

**Auf einen Blick**

* Outbound Proxy für Ämter eingeführt.
* Allgemeine Verbesserungen bei Ämtern (z. B. bei Umleitungen, Halten, Transfer).
* Vodafone NGN Trunk Unterstützung über Outbound Proxy (onsite).
* Analytics optimiert (unter anderem Teamansicht).
* Migration von Analytics läuft nun stabiler.
* Anzeige beim Heranholen und Transferieren auf Hardwaregeräten verbessert.
* Abwerfen eines Anrufes erzeugt in jedem Fall wieder eine Call Activity.


**ÄNDERUNGEN:**

- [MD-10987] - Improve Peoplefone trunk anonymous call behavior
- [MD-11541] - Broken Analytics/Grafana after fresh installations in rare cases
- [MD-11707] - Do not show warning messages during loading in CSUI
- [MD-11835] - Update xmpsserver http client
- [MD-11858] - Consul register again deleted instance
- [MD-11867] - Clean up db-schema file
- [MD-11868] - Disable yealink subscribe_register because not supported in pjsip
- [MD-11939] - Rename label for number of extension digits in trunk
- [MD-11971] - Don't add any options to generic SIP trunk
- [MD-12006] - Can't upload wav to default MoH
- [MD-12035] - Analytics can't handle dots properly
- [MD-12053] - Missing audio after outbound redirections
- [MD-12058] - Missing English silence/1 prompts
- [MD-11861] - API improvement for queue live stats
- [MD-12095] - pascom Analytics: Add counter for waiting users/agents on live dashboard
- [MD-12036] - Improve performance and restrict amount of shown teams in analytics
- [MD-12086] - Update linux kernel to 4.15
- [MD-12078] - Add container memory details (caches, buffers) to prometheus metrics
- [MD-8596] - Monitor asterisk trunk connectivity
- [MD-11914] - Update Seabix Trunk Template
- [MD-12056] - Update asterisk to 16.8.0
- [MD-12083] - Restrict default trunk codec list to alaw with ptime 20 to avoid re-invites
- [MD-11985] - Update Java 11 AdoptOpenJDK JRE/JDK
- [MD-12046] - No ringback tone with Telekom advanced template
- [MD-11708] - Prohibit sip call push in GSM only mode
- [MD-12060] - Remove hard upper memory limit from all container image descriptor
- [MD-12074] - Replace apache mod_php with php fpm
- [MD-11635] - Allow to hangup multiple channels by sending base.Hangup
- [MD-12103] - Phone status unavailable if connected via UDP interface
- [MD-12088] - Missing call activity after drop in external/before action
- [MD-11779] - Subscription valid until info in instance shows negative amount of days
- [MD-11846] - Correctly handle callerid and connectedline updates in pjsip
- [MD-12073] - Improve overlay cleanup on instance update
- [MD-11948] - SIP outbound proxy for pascom 19 pjsip trunks
- [MD-12099] - Outbound proxy support for vodafone NGN trunks
- [MD-12040] - Set ptime 20 for physical and virtual fax devices
- [MD-11935] - Hide sip peer in display of snom phones
- [MD-11980] - Update Kamailio to version 5.3.x

## Release 19.04 (03.02.2020)

**Auf einen Blick**

* Migrationsprobleme bei Ämtern mit leeren SIP Optionen behoben.
* TCP Ämter funktionieren wieder problemlos.


**ÄNDERUNGEN:**

- [MD-11973] - Apply telephony broken if trunk account contains no options
- [MD-12041] - All incoming calls on tcp trunks rejected

## Release 19.03 (29.01.2020)

**Auf einen Blick**

* Generische Geräte können nun provisioniert werden
* Beronet Gateways und Ämter funktionieren wieder
* Die Snom Basis-Konfiguration verwendet ab sofort XML-Format
* SIP-Header können wieder manuell angepasst werden 
* PJSIP-Header für Ämter werden nun direkt in den Account-Optionen des Amtes konfiguriert, nicht mehr in Skripten (z. B. def_outbound)
* Externe und intere Ruftöne (via Alert-info-header) sind nun nutzbar
* Durchsagegruppen (Intercom) funktionieren wieder
* Aastra/Mitel DECT Handsets zeigen bei laufenden Anrufen keine fehlerhafte Registrierung mehr an
* Grandstream Gateways mit neuer MAC werden ordnungsgemäß angelegt
* Migrationsprobleme mit Grafana (fehlende Weiterleitung und kaputter Login) wurden behoben 
* Die Mail-to-Fax Konfiguration kann nun zwischen SSL, StartTLS und Plain unterscheiden
* Pickup in Verbindung mit TAPI funktioniert nun auch mit mehreren Leitungen
* Modifizierte Snom Basis-Konfigurationen migrieren "Nebenstelle"-Tasten auf "BLF" um Pickup zu ermöglichen
* Auf verschiedenen Snom und Yealink Geräten werden pascom-Logos als Hintergrund provisioniert
* QSC/Plusnet Provider Template berichtigt
* T-M-Net Provider Template hinzugefügt
* magenta.at Provider Template hinzugefügt

**ÄNDERUNGEN:**

- [MD-11087] - Optimize Snom M700 config
- [MD-11721] - Easybell contact header
- [MD-11829] - Plusnet QSC trunk has wrong options in pascom 19
- [MD-11832] - Remove swap from grafana in pascom 19
- [MD-11968] - Increase maxlength of external_group_number input
- [MD-11847] - Remove 'type' column in team overview
- [MD-11856] - Mitel Aastra DECT shows that its unregistered
- [MD-11927] - Automatically configure lxc soft memory limit
- [MD-11952] - CSUI shows no error if FQDN is missing
- [MD-11863] - Asterisk opens a lot of tcp connections, saturates kamailio
- [MD-11919] - Kamailio does not rewrite Supported: header correctly
- [MD-11924] - Wrong context in sip_ipdevice.conf
- [MD-11892] - Grandstream HT802 ATA gateway (with new MAC) created as phone
- [MD-11812] - Grafana of instance not accessible after update sometimes
- [MD-11722] - Improve mail to fax configuration
- [MD-11720] - Add language selector to instance wizard admin and account pages
- [MD-11659] - Pickup is broken in multiline tapi setup
- [MD-8588] - Auto-provision logos on supported Snom and Yealink phones
- [MD-10822] - Multidial on trunks with direct transfer fails when external device is called
- [MD-11853] - Improve layout of pascom logo in login + setup view
- [MD-11762] - Update asterisk to 16.6.1
- [MD-11814] - Optimize pascom.cloud janus video traffic
- [MD-11857] - Better CLIP handling for trunks
- [MD-11230] - Simple generic provisioning
- [MD-11842] - Allow to set pjsip headers via script
- [MD-11931] - Migration to 19.X fails if broken vcard exists
- [MD-11849] - Can't use PUI menu on a Yealink phone,
- [MD-11855] - Can't create new team after importing backup of 17.12
- [MD-10725] - Improve trunk inbound anonymous handling
- [MD-11810] - Berofix SIP to ISDN trunk not working with pascom 19
- [MD-11962] - Change sip trunk template of Deutsche Telefon
- [MD-11588] - T-M-NET SIP-Provider Integration
- [MD-11658] - magenta.at sip trunk template
- [MD-11667] - Update web applications to angular 8
- [MD-11714] - Configure asterisk local_net and fake external address in pascom.cloud
- [MD-11926] - Store systemd journal on disk instead of tmpfs
- [MD-11979] - Logrotate and restart pbx apache once per night
- [MD-11850] - Snom BLF pickup is broken (pascom 19)
- [MD-11949] - Pickup from a queue doesn't work via notification
- [MD-11633] - Use XML based provisioning templates for Snom phones
- [MD-12009] - Xmpp migration fails if there is no events after mdarchive migration

## Release 19.02 (22.11.2019)

**Auf einen Blick**

- Anrufe auf dem Mobile Client können wieder zuverlässig angenommen werden.
- Let's Encrypt Zertifikate werden wieder ausgestellt.

**ÄNDERUNGEN:** 

- [MD-11874] - Internal calls softphone to mobile can't be answered
- [MD-11876] - Port let's encrypt to 19
- [MD-11866] - Configure QOS/TOS in asterisk pjsip


## Release 19.01 (21.11.2019)

**Auf einen Blick**

- Yealink BLF-Tasten zeigen wieder den richtigen Status.
- Migrationsprobleme in Verbindung mit Rufgruppen und Aktionen behoben.
- Journal der Yealink-Telefone berücksichtigten wieder die Amtsvorwahl beim Zurückwählen.
- Mikrofon wird bei externen Anrufen zuverlässig stumm geschaltet.
- Halten und Zurückholen bei mehreren Anrufen verbessert.

**ÄNDERUNGEN:** 

- [MD-11818] - Can't change password via client
- [MD-11819] - Invalid image.json configuration file for cs-proxy
- [MD-11823] - Error invalid wire type in xmpp log
- [MD-11831] - Mobile icon missing if user deactivates mobile in follow me
- [MD-11813] - Improve UI for creating the queue
- [MD-11843] - Redial on hardware phones is broken if trunk has 0 prefix
- [MD-11844] - Adapt Seabix trunk template
- [MD-11851] - Call Specific actions are broken for softphone calls
- [MD-11833] - Unreliable Yealink BLF
- [MD-11828] - Incorrect phone call data after the pickup
- [MD-11824] - pascom 19 migration bug if action of type "c" (callgroup) exists
- [MD-11821] - Error on restarting pbx containers
- [MD-11834] - Consul template service is not started in the cs-proxy container
- [MD-11380] - Export more instance level metrics to prometheus

## Release 19.00 (04.11.2019)

**Auf einen Blick**

- Kontakte/Kontaktliste überarbeitet.
- Neue Suchfunktion mit Smartfilter.
- Interaktive Anrufobjekte während einem Telefonat.
- Video und Screensharing Funktion.
- pascom Gruppen. Permanente Audio,- Video und Screensharing Gruppen.
- Asterisk Update auf Version 16 LTS.
- Zugriff auf RTP Statistiken.
- Ämtertemplates geändert auf die pjsip Syntax.



