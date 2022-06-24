---
title: Stornare la registrazione del giornale di registrazione
description: Questo articolo descrive le funzionalità che consentono di stornare i voucher dall'elenco delle transazioni dei voucher o dai giornali finanziari.
author: kweekley
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bec7d5d0dd64a2d89b00e2aa630a4fe670feaa2b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868404"
---
# <a name="reverse-journal-posting"></a>Stornare la registrazione del giornale di registrazione

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritte le funzionalità di Microsoft Dynamics 365 Finance che consentono di stornare un intero giornale di registrazione o stornare uno o più giustificativi dell'elenco delle transazioni giustificativi indipendentemente dall'origine. 

Prima di poter utilizzare una delle funzionalità descritte in questo articolo, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro **Gestione funzionalità** per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:
 - Modulo: Contabilità generale
 - Nome funzione: **Storno di massa per più documenti**

## <a name="reversing-journals"></a>Storno dei giornali di registrazione

È possibile stornare singolarmente le righe del giornale di registrazione. Con lo storno della registrazione del giornale di registrazione, è inoltre possibile stornare un intero giornale finanziario. Per stornare un giornale di registrazione: 

- Filtrare i giornali di registrazione pubblicati e aprire la visualizzazione **Righe** nel giornale di registrazione.
- Selezionare il menu **Storna** nella parte superiore della pagina.
- Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate.
- Selezionare **Sì** per utilizzare le date di transazione esistenti o **No** per immetterne una nuova. In alcuni casi, il periodo della transazione originale potrebbe essere chiuso ed è necessario immettere una nuova data di transazione per lo storno.
- Se si seleziona **No**, immettere una data di transazione per lo storno. 
- Immettere un commento che si desidera aggiungere alla transazione di storno.
- Selezionare il pulsante **Storna**.

Le transazioni saranno stornate. 

Se il giustificativo contiene più di 100 righe, il processo di storno verrà eseguito utilizzando il processo batch. È possibile esaminare i risultati visualizzando i commenti nel processo batch. Tutte le transazioni che non vengono stornate sono elencate nello storico dei processi batch.

Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente. I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare con il motivo per cui non possono essere stornati. Selezionare **OK** per chiudere la finestra di dialogo.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Storno di giustificativi dall'elenco delle transazioni giustificativi. 

È inoltre possibile stornare i giustificativi dall'**elenco transazioni per giustificativo** in tutti i giornali di registrazione secondari . Inoltre, è possibile stornare più di un giustificativo per volta. 

Per stornare uno o più giustificativi: 

- Selezionare **Storna intero giornale di registrazione nel menu** a discesa nella parte superiore della pagina.
- Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate.
- Selezionare **Sì** per utilizzare le date di transazione esistenti o **No** per immetterne una nuova. In alcuni casi, il periodo della transazione originale potrebbe essere chiuso ed è necessario immettere una nuova data di transazione per lo storno.
- Se si seleziona **No**, immettere una data di transazione per lo storno. 
- Immettere un commento per descrivere la transazione di storno.
- Selezionare il pulsante **Storna**.

Le transazioni saranno stornate. 

Se il giustificativo include più di 100 righe, il processo di storno verrà eseguito utilizzando il processo batch. È possibile esaminare i risultati visualizzando i commenti nel processo batch. Tutte le transazioni che non vengono stornate sono riportate nello storico dei processi batch.

Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente. I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare insieme al motivo. Selezionare **OK** per chiudere la finestra di dialogo.

Le transazioni possono essere stornate solo se soddisfano le regole business per lo storno. I pagamenti fornitore non possono essere stornati utilizzando la funzionalità descritta in questo articolo. I pagamenti fornitore devono essere stornati tramite i passaggi elencati in [Stornare un pagamento fornitore](../accounts-payable/reverse-vendor-payment.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
