---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (16 ottobre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d5f2aea5fcc81d0b4c1d8a392a3e56c888440a94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461611"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-16-2018"></a>Novità o modifiche in Dynamics 365 Talent - Core HR (16 ottobre 2018)

**Build 8.1.1067**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.

## <a name="allow-managers-to-update-time-off-requests"></a>Consentire ai responsabili di aggiornare le richieste di permesso

Può essere necessario aggiornare le richieste di permesso dei dipendenti dopo che sono state approvate tramite il flusso di lavoro. In molti casi il responsabile effettua questi aggiornamenti per conto del dipendente. Questa nuova funzionalità offre la possibilità ai responsabili di aggiornare o annullare le richieste di permesso per conto dei dipendenti. Questa possibilità è controllata dal parametro **Lavoro svolto per conto di** che può essere impostato nella pagina **Parametri Risorse umane**. 
 
## <a name="allow-hr-to-update-time-off-requests"></a>Consentire alle Risorse umane di aggiornare le richieste di permesso

Analogamente alla funzionalità descritta in precedenza, le richieste di permesso dei dipendenti possono essere aggiornate dalle Risorse umane dopo che sono state in precedenza approvate tramite il flusso di lavoro. Questa funzionalità consente agli utenti delle Risorse umane di aggiornare le richieste di permesso. Questa possibilità viene attivata nell'area di lavoro **Persone** e nella pagina **Lavoratore**, utilizzando una nuova opzione denominata **Visualizza tempo libero**. Su tali pagine gli utenti delle Risorse umane potranno visualizzare le richieste e aggiornare le transazioni relative ai permessi, analogamente a come i responsabili possono eseguire queste azioni.

I diritti di sicurezza che controllano l'accesso a questa funzionalità sono:
- Diritti: gestire i processi di congedo e assenza specifici del lavoratore.
- Privilegio: gestire le richieste di congedo e assenza per tutti i lavoratori.

## <a name="other-changes"></a>Altre modifiche
I seguenti aggiornamenti sono stati effettuati in questa versione:
- Modifiche alle azioni di assunzione dei lavoratori in modo che non siano più "bloccate" nello stato **Flusso di lavoro completato**.
- È ora possibile creare il record di impiego senza una data di inizio impiego.
- La data di registrazione di Dynamics 365 Talent per un corso tenuto in Dipendente self-service applica ora la differenza del fuso orario alla data.
- I file di Excel possono essere importati più volte senza alcun errore utilizzando **Dipendenti**.

## <a name="known-issue"></a>Problema noto

- **Problema**: quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** sono inattivi. 
- **Soluzione alternativa:** prima di aprire la pagina dell'allegato, verificare che le schede dettaglio della pagina **Lavoratore** siano chiuse. Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli allegati saranno abilitati. Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.
