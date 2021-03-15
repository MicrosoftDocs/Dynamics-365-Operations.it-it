---
title: Assegnare ruoli utente per il leasing
description: In questo argomento vengono descritti i ruoli di sicurezza utilizzati in Leasing cespiti. Spiega inoltre come assegnare gli utenti a quei ruoli.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: df23e219f5bd859b0072785dfd5f7a0ec63f540e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995395"
---
# <a name="assign-lease-user-roles"></a>Assegnare ruoli utente per il leasing

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i ruoli di sicurezza utilizzati in Leasing cespiti. Spiega inoltre come assegnare gli utenti a quei ruoli.

Tre ruoli utente differenziano l'accesso in Leasing cespiti. Un ruolo è appropriato per mantenere i leasing, uno è appropriato per visualizzare i leasing e uno è appropriato per svolgere le funzioni di addetto al leasing. Ogni ruolo dispone di autorizzazioni specifiche per tutte le pagine di leasing e ciascuno consente agli utenti di visualizzare, creare, modificare o eliminare i leasing, in base alle loro mansioni lavorative.

| Ruolo           | descrizione |
|----------------|-------------|
| Gestire leasing | Gli utenti in questo ruolo possono aggiungere, modificare, eliminare e visualizzare i leasing. Questo ruolo è progettato per gli utenti giornalieri le cui attività includono la creazione e la registrazione di voci di giornale mensili e l'aggiunta di nuovi leasing. Questo ruolo fornisce l'accesso a tutte le funzionalità di Leasing cespiti. |
| Visualizzare leasing     | Gli utenti in questo ruolo possono solo visualizzare i record di leasing, gli scadenziari ed eseguire report. Non possono creare nuovi leasing, modificare i leasing esistenti o creare scritture contabili a fronte di leasing. Il ruolo è progettato per gli utenti che devono solo visualizzare i leasing, le pianificazioni dei leasing e le transazioni che si verificano a fronte di tali leasing. |
| Addetto al leasing    | Gli utenti in questo ruolo possono solo creare nuovi leasing. Non possono modificare o eliminare leasing esistenti, visualizzare pianificazioni leasing o registrare scritture contabili di leasing. Questo ruolo è progettato per gli utenti che lavorano con capacità di immissione dati. |

Attieniti alla seguente procedura per assegnare gli utenti ai ruoli utilizzati in Leasing cespiti.

1. Passa ad **Amministrazione sistema \> Sicurezza \> Assegna utenti a ruoli**.
2. Seleziona il ruolo **Mantenere il leasing**, **Addetto al leasing** o **Visualizzare il leasing**, quindi seleziona **Assegna/escludi utenti manualmente**.
3. Seleziona l'utente a cui assegnare il ruolo, quindi seleziona **Assegna a ruolo**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]