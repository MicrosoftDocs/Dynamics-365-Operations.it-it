---
title: Risoluzione dei problemi con il modulo doppia scrittura nelle app Finance and Operations
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo doppia scrittura nelle app Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172762"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Risoluzione dei problemi con il modulo doppia scrittura nelle app Finance and Operations

[!include [banner](../../includes/banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo **doppia scrittura** nelle app Finance and Operations.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Non è possibile caricare il modulo doppia scrittura in un'app Finance and Operations

Se non si riesce ad aprire la pagina **Doppia scrittura** selezionando il riquadro **Doppia scrittura** nell'area di lavoro **Gestione dei dati**, il servizio di integrazione dei dati è probabilmente inattivo. Creare un ticket di supporto per richiedere il riavvio del servizio di integrazione dei dati.

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a>Errore quando si tenta di creare un nuovo mapping di entità

**Credenziali richieste per risolvere il problema:** amministratore del tenant Azure AD

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di configurare una nuova entità per la doppia scrittura:

*Il codice dello stato della risposta non indica l'esito positivo: 401 (non autorizzato).*

Questo errore si verifica perché solo un amministratore del tenant Azure AD può aggiungere un nuovo mapping di entità.

Per risolvere il problema, accedere all'app Finance and Operations come amministratore del tenant Azure AD. È necessario anche andare in web.PowerApps.com e riconvalidare la tua connessione.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Errore quando si apre l'interfaccia utente a doppia scrittura

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di accedere alla doppia scrittura dall'area di lavoro **Gestione dei dati**:

*login.microsoftonline.com ha rifiutato di connettersi.*

Per risolvere il problema, accedere utilizzando una finestra InPrivate in Microsoft Edge, una finestra di navigazione in incognito in Chromium o una finestra di navigazione in incognito in Google Chrome. È inoltre necessario sbloccare o cancellare i cookie di terze parti.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Errore quando si collega l'ambiente per la doppia scrittura o si aggiunge un nuovo mapping di entità

**Credenziali richieste per risolvere il problema:** amministratore del tenant Azure AD

È possibile che si verifichi il seguente errore durante il collegamento o la creazione di mappe:

*Il codice dello stato della risposta non indica l'esito positivo: 403 (tokenexchange).<br> ID sessione: \<ID sessione\><br> ID attività radice: \<ID attività radice\>*

Questo errore può verificarsi se non si dispone di autorizzazioni sufficienti per collegare la doppia scrittura o creare mappe. È necessario usare un account amministratore del tenant Azure AD per collegare ambienti e aggiungere nuovi mapping di entità. Tuttavia, dopo l'impostazione, è possibile utilizzare un account non amministratore per monitorare lo stato e modificare i mapping.

## <a name="error-when-you-stop-the-entity-mapping"></a>Errore quando si interrompe il mapping dell'entità

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di interrompere i mapping di entità:

*\[Accesso negato\], \[{"stato": 403,"origine":"","messaggio":"Errore dello scambio di token: l'utente non è autorizzato ad accedere alla connessione dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Il server remoto ha restituito un errore: (403) Accesso negato.*

Questo errore si verifica quando l'ambiente Common Data Service collegato non è disponibile.

Per risolvere il problema, creare un ticket per il team di integrazione dei dati. Collegare la traccia di rete in modo che il team di integrazione dei dati possa contrassegnare le mappe come **Non in esecuzione** nel back-end.
