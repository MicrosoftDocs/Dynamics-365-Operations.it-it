---
title: Cespiti in entrata e in uscita
description: Viene descritta la procedura per la registrazione dei cespiti in entrata e in uscita in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6dfadf6824c6a3df7be9b3b6f3d9f5dd2749e34
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018073"
---
# <a name="inbound-and-outbound-assets"></a>Cespiti in entrata e in uscita

[!include [banner](../../includes/banner.md)]

 

Se la società effettua i processi di riparazione o i processi di manutenzione sui cespiti ricevuti da altri ubicazioni o clienti, Gestione cespiti può tenere traccia sia dei cespiti in entrata che stanno per arrivare che dei cespiti in uscita che vengono restituiti.

> [!NOTE]
> Se si desidera utilizzare gli stati del ciclo di vita in entrata e in uscita per gestire i cespiti in arrivo e in restituzione, è necessario impostare gli stati del ciclo di vita delle richieste di intervento di manutenzione e i modelli del ciclo di vita per supportare tali azioni. Per ulteriori informazioni, vedere [Richieste di intervento di manutenzione](../setup-for-maintenance-requests/requests.md).

L'impostazione di Gestione cespiti determina se è possibile lavorare con i cespiti in entrata e in uscita.

## <a name="register-assets-as-inbound"></a>Registrare cespiti come in entrata

1. Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Richieste di intervento di manutenzione attive**.
2. Selezionare la richiesta di intervento di manutenzione.
3. Selezionare **Aggiorna stato della richiesta di intervento di manutenzione**.
4. Selezionare **In entrata** (o un altro stato del ciclo di vita creato per i cespiti in entrata), quindi **OK**.

![Registrare cespiti come in entrata](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Registrare i cespiti in entrata come ricevuti

1. Selezionare **Gestione cespiti** \> **Comune** \> **In entrata/In uscita** \> **Cespiti in entrata**.
2. Selezionare il cespite o la richiesta di intervento di manutenzione.
3. Selezionare **Ricevi cespiti**.
4. Nel campo **Ricevuto** immettere la data e l'ora. Selezionare **OK**. Il record verrà rimosso dalla pagina elenco **Cespiti in entrata**.

![Registrare i cespiti in entrata come ricevuti](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Registrare cespiti come in uscita

Dopo aver completato il processo di riparazione o manutenzione, è possibile registrare il cespite come restituito.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Richieste di intervento di manutenzione attive**.
2. Selezionare la richiesta di intervento di manutenzione.
3. Selezionare **Aggiorna stato della richiesta di intervento di manutenzione**.
4. Selezionare **In uscita** (o un altro stato del ciclo di vita creato per i cespiti in uscita), quindi **OK**.

## <a name="register-outbound-assets-as-delivered"></a>Registrare i cespiti in uscita come consegnati

1. Selezionare **Gestione cespiti** \> **Comune** \> **In entrata/In uscita** \> **Cespiti in uscita**.
2. Selezionare il cespite o la richiesta di intervento di manutenzione.
3. Selezionare **Consegna cespiti**.
4. Nel campo **Consegnato** immettere la data e l'ora. Selezionare **OK**. Il record verrà rimosso dalla pagina elenco **Cespiti in uscita**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]