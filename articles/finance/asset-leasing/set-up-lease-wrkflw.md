---
title: Configurare flussi di lavoro di approvazione del leasing
description: L'argomento spiega come configurare un flusso di lavoro di approvazione che verrà eseguito quando viene creato un nuovo leasing.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0e7280bbf60901266c81a0c89395c5183f991425
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881664"
---
# <a name="set-up-lease-approval-workflows"></a>Configurare flussi di lavoro di approvazione del leasing

[!include [banner](../includes/banner.md)]

L'argomento spiega come configurare un flusso di lavoro di approvazione che verrà eseguito quando viene creato un nuovo leasing. Per informazioni su come utilizzare il flusso di lavoro, vedi [Utilizza flussi di lavoro di approvazione del leasing](use-create-lease-wrkflw.md). 

1. Vai a **Leasing cespiti \> Imposta \> Flusso di lavoro di leasing**.
2. Nella pagina **Flusso di lavoro di leasing**, seleziona **Nuovo**.
3. Nella finestra di dialogo che appare, in **Tipo di flusso di lavoro**, seleziona il collegamento **Flusso di lavoro di leasing**.

    L'applicazione viene aperta. Dopo l'esecuzione, accedi ad Azure Active Directory (Azure AD) per essere reindirizzato all'applicazione del flusso di lavoro.

4. Trascina l'elemento **Approvazione flusso di lavoro leasing** nel flusso di lavoro.
5. Connetti un nodo da **Inizio** a **Approvazione flusso di lavoro leasing**. Quindi connetti **Approvazione flusso di lavoro leasing** a **Fine**.
6. Fai doppio clic su **Approvazione flusso di lavoro leasing**.
7. Seleziona **Proprietà** e poi in **Impostazioni di base**, immetti un nome per il flusso di lavoro.

    In questa pagina puoi anche impostare più parametri per il flusso di lavoro. Se hai attivato **Azioni automatiche**, il sistema eseguirà automaticamente un'azione specifica. Le notifiche possono essere inviate se specificate nella scheda **Notifiche**. Nella scheda **Impostazioni avanzate**, è possibile specificare un approvatore finale, impostare un limite di tempo e designare azioni specifiche che devono essere completate.

8. Al termine dell'impostazione dei parametri del flusso di lavoro, seleziona **Chiudi**.
9. Seleziona **Passaggio 1**, quindi seleziona **Proprietà**.
10. In **Impostazioni di base**, immetti un nome per il passaggio, crea una riga dell'oggetto per l'approvazione e specifica le istruzioni per l'approvazione.
11. Nella pagina **Assegnazione**, seleziona il tipo di assegnazione.
12. Per assegnare utenti specifici all'approvazione, seleziona **Utente**, seleziona gli utenti che approvano i leasing, quindi seleziona **Chiudi**.
13. Seleziona **Salva e chiudi** per creare il flusso di lavoro. Quindi, quando richiesto, seleziona **OK**.
14. Nella pagina **Crea flusso di lavoro**, seleziona **Chiudi**.
14. Seleziona il nuovo flusso di lavoro, quindi seleziona **Versioni**. Quindi seleziona **Rendi attivo** per verificare che il flusso di lavoro sia attivo.
15. Selezionare **Chiudi**. Viene visualizzata la nuova versione attiva.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
