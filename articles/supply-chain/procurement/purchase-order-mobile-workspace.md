---
title: Area di lavoro Approvazione ordine fornitore
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Approvazione ordine fornitore, in cui è possibile visualizzare gli ordini fornitore ed effettuare le relative operazioni. Ad esempio, è possibile approvare o rifiutare un ordine fornitore.
author: GalynaFedorova
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b0bdcb2f6db95ae061e786365d22cdf74643d09e
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811814"
---
# <a name="purchase-order-approval-mobile-workspace"></a>Area di lavoro Approvazione ordine fornitore

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Approvazione ordine fornitore**. Questa area di lavoro consente di visualizzare gli ordini fornitore ed effettuare le relative operazioni. Ad esempio, è possibile approvare o rifiutare un ordine fornitore.
 
## <a name="overview"></a>Panoramica 
Gli ordini fornitore che richiedono l'approvazione devono passare attraverso un flusso di lavoro di approvazione. Il flusso di lavoro può includere vari passaggi che richiedono l'esecuzione di operazioni da parte di una o più persone. Ad esempio, una persona potrebbe dover completare un'attività o approvare l'ordine fornitore. 

L'area di lavoro mobile **Approvazione di ordine fornitore** consente di visualizzare in modo semplice e rispondere agli ordini fornitore dal dispositivo mobile. Questa area di lavoro consente inoltre di effettuare le stesse azioni del flusso di lavoro che è possibile effettuare dal client Web.

## <a name="prerequisites"></a>Prerequisiti
I prerequisiti variano a seconda della versione di Supply Chain Management che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Prerequisiti si utilizza Supply Chain Management 
Se nell'organizzazione è stato distribuito Supply Chain Management, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Approvazione ordine fornitore**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Prerequisiti se si usa Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva
Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti. 

<table>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementare l'articoloo KB 4017918.</td>
<td>Amministratore di sistema</td>
<td>l'articoloo KB 4017918 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Approvazione ordine fornitore</strong>. Per implementare l'articolo KB 4017918, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Applicare il pacchetto distribuibile</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Pubblicare l'area di lavoro mobile <strong>Approvazione ordine fornitore</strong>.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app per dispositivi mobili
Scaricare e installare l'app Finance and Operations per dispositivi mobili:

- [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile

1. Avviare l'app sul dispositivo mobile.
2. Immettere il proprio URL Microsoft Dynamics 365.
3. La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
4. Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

![Area di lavoro Approvazione ordine fornitore nell'elenco delle aree di lavoro disponibili.](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>Visualizzare gli ordini assegnati all'utente
1. Sul dispositivo mobile, selezionare l'area di lavoro **Approvazione ordine fornitore**.
2. Selezionare **Ordini assegnati all'utente** per visualizzare tutti gli ordini fornitore per cui all'utente è stato richiesto di eseguire azioni del flusso di lavoro di approvazione dell'ordine fornitore.
3. Selezionare un ordine. Nella pagina **Dettagli ordine**, sarà possibile visualizzare le informazioni e le righe dell'intestazione dell'ordine. È inoltre possibile trovare le linee guida all'attività del flusso di lavoro.
4. Selezionare **Distribuzioni contabili** per aprire la pagina **Distribuzione contabile intestazione**.
5. Tornare alla pagina **Dettagli ordine** e selezionare una riga. Dai dettagli della riga ordine, è possibile esplorare le distribuzioni contabili specifiche della riga.

## <a name="complete-an-action-on-the-purchase-order"></a>Completare un'azione sull'ordine fornitore
Dopo avere visualizzato l'ordine fornitore assegnato all'utente e letto le istruzioni relative al flusso di lavoro, s è pronti per eseguire un'azione.

1. Sul dispositivo mobile, selezionare l'area di lavoro **Approvazione ordine fornitore**.
2. Selezionare **Ordini assegnati all'utente** per visualizzare tutti gli ordini fornitore per cui all'utente è stato richiesto di eseguire azioni del flusso di lavoro di approvazione dell'ordine fornitore.
3. Selezionare un ordine e visualizzare la pagina dei dettagli.
4. Selezionare **Azioni** per visualizzare le azioni disponibili. Le azioni disponibili variano a seconda dell'attività assegnata all'utente.

    | Azione di attività    | Azione approvazione  |
    |----------------|------------------|
    | Completata       | Approva          |
    | Restituita         | Rifiuta           |
    | Richiedi modifica | Richiedi modifica   |
    | Delegata       | Delegata         |

5. Selezionare l'azione appropriata.
6. Nella pagina **Completa attività**, immettere un commento. Se si seleziona l'azione **Delega**, è necessario selezionare un utente a cui delegare l'attività.
7. Selezionare **Fine**. Dopo aver aggiornato l'area di lavoro, l'ordine fornitore non sarà più in elenco. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
