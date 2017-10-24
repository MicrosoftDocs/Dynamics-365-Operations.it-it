---
title: Area di lavoro mobile Approvazioni fatture
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Approvazioni fatture. Questa area di lavoro fornisce un elenco di fatture assegnate all'utente mediante il processo del flusso di lavoro di intestazione della fattura fornitore.
author: abruer
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: 190f48f4d5e304902b701f74f2cbefcbe7b36b15
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="invoice-approvals-mobile-workspace"></a>Area di lavoro mobile Approvazioni fatture

[!include[banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Approvazioni fatture**. Questa area di lavoro fornisce un elenco di fatture assegnate all'utente mediante il processo del flusso di lavoro di intestazione della fattura fornitore. 

Questa area di lavoro mobile può essere utilizzata con l'app mobile Microsoft Dynamics 365 for Unified Operations.

## <a name="overview"></a>Panoramica

L'area di lavoro mobile **Approvazioni fatture** consente a funzionari e responsabili della contabilità fornitori di visualizzare le fatture che sono state loro assegnate durante il processo del flusso di lavoro di intestazione della fattura fornitore. È possibile visualizzare informazioni sulle fatture e persino i dettagli di distribuzione e riga, che consentono di prendere decisioni di approvazione informate. Nell'area di lavoro, è possibile spostare la fattura nel processo del flusso di lavoro. 

## <a name="prerequisites"></a>Prerequisiti

Per poter utilizzare questa area di lavoro mobile è necessario soddisfare i seguenti requisiti.

<table>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) deve essere distribuito nell'organizzazione.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="../deployment/deploy-demo-environment.md">Distribuire un ambiente di dimostrazione</a>.
</td>
</tr>
<tr class="even">
<td>L'area di lavoro mobile <strong>Approvazioni fatture</strong> deve essere pubblicata.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app mobile

Scaricare e installare l'app mobile Dynamics 365 for Unified Operations:

-   [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile

1.  Avviare l'app sul dispositivo mobile.
2.  Immettere il proprio URL Microsoft Dynamics 365.
3.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
4.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

    [![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>Approvare fatture tramite l'area di lavoro Approvazioni fatture
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Approvazioni fatture**.
2.  Selezionare la fattura assegnata dal processo del flusso di lavoro di intestazione della fattura fornitore.
3.  Nella pagina **Dettagli fattura**, rivedere le informazioni nell'intestazione della fattura, ad esempio informazioni sul fornitore e sulla data.
4.  Selezionare una riga della fattura per visualizzare informazioni più dettagliate nella visualizzazione **Dettagli riga fattura**.
5.  Nella visualizzazione **Dettagli riga fattura**, selezionare **Distribuzioni** per mostrare le distribuzioni riga. Qui, è possibile visualizzare la contabilità per la riga fattura. Le informazioni visualizzate includono le dimensioni finanziarie e il conto principale.
6.  Nella pagina **Dettagli fattura**, selezionare **Distribuzioni** per mostrare tutte le distribuzioni. Qui, è possibile visualizzare la contabilità per l'intera fattura. Le informazioni visualizzate includono le dimensioni finanziarie e i conti principali. 
7.  Selezionare **Allegati** per visualizzare tutti i file o note associati alla fattura.
8.  Nella pagina **Dettagli fattura**, selezionare l'azione del flusso di lavoro appropriata per completare il processo di revisione.
9.  Selezionare **Fine**.

