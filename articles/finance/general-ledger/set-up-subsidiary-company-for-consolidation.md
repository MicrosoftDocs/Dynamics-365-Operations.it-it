---
title: Impostare una persona giuridica affiliata per il consolidamento
description: Questo argomento spiega come lavorare con i grafici dei conti per le società di consolidamento.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: fbec5ad8fa5e17b75859c07ee64a66c9568c97d3d18b6a7616a64303d3a33f10
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727961"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>Impostare una persona giuridica affiliata per il consolidamento

[!include [banner](../includes/banner.md)]

La procedura di preparazione dei conti di una persona giuridica affiliata per il consolidamento dipende in parte da quanto la struttura del piano dei conti della persona giuridica affiliata riflette il piano dei conti della persona giuridica consolidata.

Prima di avviare il consolidamento come parte della chiusura di un periodo, completare le attività preparatorie della chiusura, senza tuttavia chiudere i conti della persona giuridica affiliata fino al completamento del consolidamento. Per ulteriori informazioni sulle chiusure di periodi, vedi [Chiudere la contabilità generale a fine periodo](close-general-ledger-at-period-end.md) e [Chiudere l'anno fiscale](tasks/close-fiscal-year.md).

> [!NOTE]
>  Ti consigliamo di utilizzare Management Reporter per Microsoft Dynamics 365 Finance per combinare i risultati finanziari per più persone giuridiche in un formato consolidato. Management Reporter ti consente di creare report finanziari consolidati tra persone giuridiche, utilizzare Excel per importare dati di consolidamento da altre origini e convertire gli importi in un numero qualsiasi di valute di reporting senza dover eseguire il processo di consolidamento in Dynamics 365 Finance.

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>Associare i conti principali dell'affiliata ai conti principali della consolidata

Se il piano dei conti della persona giuridica affiliata non riflette il piano dei conti della persona giuridica consolidata, è possibile associare i conti principali dell'affiliata ai conti principali della consolidata.

1. Nell'*entità giuridica affiliata*, vai a **Contabilità generale \> Impostazione** \> **Piano dei conti \> Piano dei conti**.
2. Seleziona un piano dei conti. Nella Scheda dettaglio **Conti principali**, seleziona un conto principale, quindi seleziona **Modifica**.
3. Seleziona ciascun conto principale dell'affiliata che deve essere mappato a un conto principale consolidato. Nella Scheda dettaglio **Generale**, nel campo **Conto di consolidamento** immetti il conto nella persona giuridica consolidata in cui devono essere trasferiti il saldo o le transazioni del conto principale dell'affiliata. È possibile immettere lo stesso conto principale della consolidata per più conti dell'affiliata.

    > [!NOTE]
    > Se i tipi di conto principale dei conti dell'affiliata che vengono associati sono diversi dai tipi di conto principale dei conti nella persona giuridica consolidata, i valori dei conti con un tipo di conto principale **Totale** verranno sovrascritti durante il consolidamento.

4. Preparare report e rendiconti finanziari per la persona giuridica consolidata basati su dimensioni finanziarie. Attenersi alla seguente procedura per mappare le dimensioni finanziarie utilizzate nei conti delle filiali per le dimensioni finanziarie nella persona giuridica consolidata:

    1. Nell'*entità giuridica affiliata*, vai a **Contabilità generale \> Impostazione \> Dimensioni finanziarie \> Dimensioni finanziarie**, seleziona una dimensione finanziaria e quindi seleziona **Valori dimensione finanziaria**.
    2. Seleziona il valore della dimensione finanziaria per il mapping a un valore di dimensione finanziaria diverso nella persona giuridica consolidata.
    3. Nella Scheda dettaglio **Generale**, nel campo **Dimensione gruppo**, immettere la dimensione finanziaria nella persona giuridica consolidata. Durante il consolidamento, la dimensione finanziaria verrà assegnata a transazioni e saldi che utilizzano la dimensione finanziaria selezionata nella persona giuridica affiliata. Le dimensioni finanziarie immesse in questo campo devono essere utilizzate nella persona giuridica consolidata. La dimensione finanziaria utilizzata può essere assegnata come dimensione finanziaria del gruppo a numerose dimensioni finanziarie dell'affiliata.

5. Se stai eseguendo un consolidamento online, segui questi passaggi per assicurarti che i trasferimenti avvengano come desideri:

    1. Nell'*entità giuridica consolidata*, vai a **Contabilità generale \> Periodico \> Consolida \> Consolida \[Esporta in\]** per aprire la pagina **Consolida \[ online\]**.
    2. Nella scheda **Criteri** selezionare la casella di controllo **Utilizza conto di consolidamento**.
    3. Nella scheda **Dimensioni finanziarie**, seleziona le dimensioni finanziarie appropriate.
    4. Per ciascuna dimensione finanziaria che selezioni, immetti un numero nel campo **Ordine segmento** per indicare l'ordine in cui devono essere visualizzate le dimensioni.

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>Mantenere lo stesso piano dei conti nelle persone giuridiche affiliata e consolidata

I conti principali nella persona giuridica affiliata potrebbero avere gli stessi numeri di conto e la stessa struttura per il piano dei conti dei conti principali della persona giuridica consolidata. In questo caso, non è necessario associare manualmente i conti principali dell'affiliata ai conti principali nella persona giuridica consolidata.

Prima di iniziare il consolidamento, segui questi passaggi.

1. Nell'*entità giuridica consolidata*, vai a **Contabilità generale \> Periodico \> Consolida \> Consolida \[Esporta in\]** per aprire la pagina **Consolida \[ online\]**.
2. Seleziona la casella di controllo **Utilizza conto di consolidamento**. Il trasferimento delle transazioni e dei saldi nel conto appropriato verranno effettuato automaticamente durante il consolidamento.

> [!NOTE]
> Se i conti non corrispondono, il consolidamento verrà interrotto e verrà visualizzato un messaggio.

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>Creare un piano dei conti per la persona giuridica consolidata, in base a un piano dei conti esistente

Puoi eseguire il consolidamento anche se nella persona giuridica consolidata non è stato ancora creato un piano dei conti.

- Se è stata pianificata la struttura dei conti da utilizzare nella persona giuridica consolidata, è possibile mappare i conti dell'affiliata alla struttura.
- Se non esegui alcun mapping per i conti dell'affiliata, i conti della persona giuridica consolidata verranno creati automaticamente quando i dati dell'affiliata verranno trasferiti nella persona giuridica consolidata. Questi conti sono basati sul conto principale. I dati successivi vengono accumulati nei conti nella persona giuridica consolidata con lo stesso numero di conto dei conti dell'affiliata.

Indipendentemente dall'esecuzione del mapping dei conti, deselezionare la casella di controllo **Utilizza conto di consolidamento** nella pagina **Consolida** nella persona giuridica consolidata prima di effettuare questo tipo di consolidamento.

> [!NOTE]
> Puoi utilizzare questo metodo per creare un piano dei conti nella persona giuridica consolidata dal piano dei conti in una delle persone giuridiche affiliate. Per ulteriori informazioni, vedi [Gruppi di conti di consolidamento e conti di consolidamento aggiuntivi](../budgeting/consolidation-account-groups-consolidation-accounts.md). Quindi assegna un principio di conversione del consolidamento appropriato a ciascun conto principale consolidato ed esegui il consolidamento per tutte le entità giuridiche affiliate.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]