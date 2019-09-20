---
title: Estendere Talent utilizzando PowerApps e Microsoft Flow - Scenari di esempio
description: In questo argomento vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 for Talent che utilizzano Microsoft PowerApps e Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 0b455a8194f58b41a349f004ceda8183c7ee3f7c
ms.sourcegitcommit: 9f94eff93d29bc27352569824e00bbccc2f961b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2019
ms.locfileid: "1781444"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a>Estendere Talent utilizzando PowerApps e Microsoft Flow - Scenari di esempio

In questo argomento vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 for Talent che utilizzano Microsoft PowerApps e Microsoft Flow. È possibile importare il pacchetto di soluzioni associato a ogni esempio nell'ambiente di PowerApps. È quindi possibile utilizzare i pacchetti come riferimento o punto di partenza per implementare scenari applicabili all'organizzazione.

> [!IMPORTANT]
> Se si desidera utilizzare i modelli e l'app descritti in questo argomento "così come sono", testarli per assicurarsi che coprano tutti gli scenari specifici dell'implementazione.


## <a name="prerequisites"></a>Prerequisiti

- Per importare pacchetti, gli utenti devono disporre dell'autorizzazione **Creazione ambiente**.
- Per esportare o importare app, gli utenti devono disporre di una licenza di PowerApps Piano 2 o una licenza di valutazione di PowerApps Piano 2.

## <a name="flow--form-connect"></a>Flusso – Connessione a modulo

Il modello **Flusso – Connessione a modulo** può essere utilizzato per leggere i dati in Microsoft Forms e archiviarli in un'entità Common Data Service.

Questo modello può essere esteso in modo da poterlo utilizzare per altri scenari. Di seguito sono riportati alcuni esempi.

- Acquisire valutazioni di candidati.
- Acquisire risultati da questionari di corsi.
- Compilare una libreria di domande di colloqui per gli amministratori delle Risorse umane.
- Acquisire la valutazione del colloquio di un candidato

In Microsoft Dynamics 365: Attract, i moduli possono essere visualizzati nel portale Candidato e i candidati possono immettere i dettagli. I moduli possono anche essere incorporati come attività in un modello posizioni lavorative.

Quando un candidato invia un modulo, Microsoft Flow lo acquisisce, legge i dati e li archivia nell'entità Common Data Service.

Per scaricare il modello **Flusso – Connessione a modulo** e Custom Entity Structure, andare a [Flusso – Connessione a modulo](https://go.microsoft.com/fwlink/?linkid=2081988) nell'Area download Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a>Iniziare ed estrarre parametri passati a PowerApps

Il modello **Iniziare ed estrarre parametri passati a PowerApps** può essere utilizzato come punto di partenza per qualsiasi scenario di PowerApps specifico di Attract. Include tutti i parametri predefiniti passati da Attract, come **Domanda di lavoro**, **ID candidato** e **JobID**.

Questo modello può essere utilizzato per recuperare un modulo di valutazione dei candidati, di modo che un responsabile delle assunzioni possa visualizzare la valutazione di un candidato.

Le app create tramite PowerApps possono essere incorporate nel modello posizioni lavorative in Attract.

Per scaricare il modello **Iniziare ed estrarre parametri passati a PowerApps** e Custom Entity Structure, andare a [Iniziare ed estrarre parametri passati a PowerApps](https://go.microsoft.com/fwlink/?linkid=2081991) nell'Area download Microsoft.

## <a name="integration-with-office-365"></a>Integration with Office 365

L'app **Integration with Office 365** può essere utilizzata per estrarre informazioni sui team per gli utenti registrati da Microsoft Office 365. Questa app fa riferimento ai lavoratori in Talent per estrarre informazioni relative all'ora di entrata e all'ora di uscita e registrazioni delle eccezioni. Le informazioni sull'ora di entrata e quella di uscita sono archiviate nelle entità Common Data Service personalizzate. Si presuppone che queste informazioni siano immesse da sistemi di terze parti via l'integrazione.

Questa app può essere estesa in modo da essere utilizzata per altri scenari. Ad esempio, per visualizzare informazioni sulle ferie del team, eventi di calendario e qualsiasi evento specifico del team.

Per scaricare l'app **Integration with Office 365** e Custome Entity Structure, andare a [Integrazione con Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) nell'Area download Microsoft.

## <a name="flow--email-notification"></a>Flusso – Notifica tramite posta elettronica

Il modello **Flusso – Notifica tramite posta elettronica** può essere utilizzato per scenari di notifica tramite posta elettronica. Può essere utilizzato per inviare messaggi di posta elettronica di notifica a candidati che il team di assunzione non seleziona durante una qualsiasi fase del processo di selezione.

Questo modello può essere esteso per tenere traccia delle modifiche alla fase di candidatura durante il processo di selezione e per inviare notifiche al team di assunzione e al candidato.

In genere per le entità archiviate in Common Data Service, i flussi possono essere configurati per inviare notifiche per eventi che si verificano in Core HR, Attract o Dynamics 365 Talent: Onboard.

Per scaricare il modello **Flusso – Notifica tramite posta elettronica**, andare a [Flusso – Notifica tramite posta elettronica](https://go.microsoft.com/fwlink/?linkid=2082103) nell'Area download Microsoft.

## <a name="flow--sql-connect-and-execute"></a>Flusso – Connessione a SQL ed esecuzione

Il modello **Flusso – Connessione a SQL ed esecuzione** esegue la connessione a Microsoft SQL Server e consente l'esecuzione delle query SQL.

Sebbene questo modello sia progettato per leggere e aggiornare le tabelle SQL, può essere esteso in modo da essere utilizzato per altri scenari. Ad esempio, per compilare una tabella di gestione temporanea in Common Data Service con record di SQL Server e per sincronizzarla periodicamente utilizzando un push incrementale di SQL Server.

Per scaricare il modello **Flusso – Connessione a SQL ed esecuzione** e Custom Entity Structure, andare a [Flusso – Connessione a SQL ed esecuzione](https://go.microsoft.com/fwlink/?linkid=2081789) nell'Area download Microsoft.

## <a name="flow--sharepoint-integration"></a>Flusso – Integrazione di SharePoint

Il modello **Flusso – Integrazione di SharePoint** può essere utilizzato per leggere dati in un elenco di Microsoft SharePoint, confrontare l'elenco con valori di campi per qualsiasi entità Common Data Service e inviare i risultati del confronto in forma di messaggio di posta elettronica di notifica. 

Un'organizzazione potrebbe avere un insieme di competenze che richiede urgentemente. Queste competenze possono essere archiviate in SharePoint come elenco di SharePoint. Quando un candidato si candida a una mansione per la quale è elencato un insieme di competenze, se è presente una corrispondenza significativa tra le competenze del candidato e quelle archiviate in SharePoint, viene inviato un messaggio di posta elettronica di notifica. In questo modo, le posizioni urgenti vengono coperte più rapidamente in quanto le notifiche consentono ai selezionatori di contattare e assumere i candidati nell'intera organizzazione.

Questo modello può essere esteso di modo che sia possibile utilizzarlo per qualsiasi scenario che comporta l'integrazione di SharePoint.

Per scaricare il modello **Flusso – Integrazione di SharePoint**, andare a [Flusso – Integrazione di SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) nell'Area download Microsoft.

## <a name="referral-app"></a>Referral App
È possibile utilizzare Referral App per aggiungere candidati a un pool di talenti condiviso. Il referente può immettere **Nome**, **Cognome**, **E-mail** e **URL Linkedln** quando invia un candidato. I metadati di origine del candidato vengono quindi completati con le informazioni del referente.

È possibile incorporare questa app in Dipendente self-service (ESS) per inviare referenze oppure è possibile utilizzarla come collegamento ipertestuale nel portale aziendale ed eseguirla come applicazione autonoma.

Per scaricare **Referral App**, accedere a [Soluzione di estensibilità Dynamics 365 for Talent: Referral App](http://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) nell'Area download Microsoft. È possibile importare questa app e personalizzarla per aggiungere altre funzionalità.

## <a name="additional-resources"></a>Risorse aggiuntive

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migrare app tra tenant e ambienti](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
