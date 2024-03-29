---
title: DBA modello
description: Una distinta base (DBA) modello fornisce un elenco standardizzato di componenti relativi a un oggetto sui quali vengono eseguiti regolarmente interventi di assistenza.
author: sorenva
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdda8ffaaf4e5696b286273fd5ad770de5349b48
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678152"
---
# <a name="template-boms"></a>DBA modello

[!include [banner](../includes/banner.md)]

Una distinta base (DBA) modello è un elenco standardizzato di componenti relativi a un oggetto sui quali vengono eseguiti regolarmente interventi di assistenza. I componenti inclusi nella DBA modello rappresentano i singoli sottocomponenti dell'oggetto assistenza. Applicando una DBA modello a un oggetto assistenza, è possibile mantenere un record dei sottocomponenti che sono stati sostituiti nell'oggetto assistenza.

Per applicare un DBA modello a un contratto di assistenza o un ordine di assistenza è necessario collegarla a una relazione di oggetto assistenza.

> [!NOTE]
> È possibile utilizzare solo una DBA modello con un oggetto assistenza.

## <a name="create-a-template-bom"></a>Creare una DBA modello

Nella tabella seguente vengono fornite informazioni sui vari metodi utilizzabili per creare una DBA modello.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Metodo</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Produzione</p></td>
<td><p>La DBA modello è basata su un ordine di produzione. Questa opzione è applicabile solo se si opera in un ambiente di produzione. Questa opzione è applicabile solo se si opera in un ambiente di produzione e consente di disporre sempre di un elenco aggiornato e dettagliato dei componenti che costituiscono un articolo.</p></td>
</tr>
<tr class="even">
<td><p>Articolo BOM</p></td>
<td><p>La DBA modello è basata su una DBA articolo. La DBA articolo, a differenza della DBA di produzione, è un elenco statico dei componenti che costituiscono un articolo.</p></td>
</tr>
<tr class="odd">
<td><p>Modello esistente</p></td>
<td><p>Il modello è basato su una DBA modello esistente.</p></td>
</tr>
<tr class="even">
<td><p>Manuale</p></td>
<td><p>Se si sa quali pezzi di ricambio vengono in genere sostituiti in un oggetto assistenza, è possibile creare la DBA modello manualmente. Questo metodo contribuisce a garantire che i componenti inclusi nel modello riflettano gli effettivi fabbisogni del luogo di lavoro.</p></td>
</tr>
</tbody>
</table>

## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>Applicazione della DBA modello a un contratto di assistenza o a un ordine di assistenza

La DBA modello può essere applicata a un contratto di assistenza, un ordine di assistenza o entrambi. Il contratto di assistenza riguarda in genere una relazione a lungo termine con un cliente. Lo storico delle sostituzioni registrato nella DBA assistenza rappresenta un insieme di dati utili ai fini del contratto di assistenza.

È inoltre possibile applicare una DBA modello a un ordine di assistenza per registrare lo storico dell'assistenza eseguita su un oggetto assistenza.

## <a name="copy-the-history-of-a-service-bom"></a>Copia dello storico di una DBA assistenza

È possibile copiare lo storico di una riga di DBA assistenza da un contratto di assistenza a un altro. Copiando lo storico assistenza tra i contratti di assistenza è possibile mantenere il record delle sostituzioni per un articolo.

### <a name="example"></a>Esempio

È stato impostato un contratto di assistenza triennale per l'automobile di un cliente. Durante tale periodo, il cliente si abitua al buon servizio fornito dalla società. Di conseguenza, alla scadenza del contratto il cliente desidera impostarne uno nuovo. A questo punto è possibile negoziare un contratto più favorevole per la società. Poiché il record dei componenti sostituiti può rivelarsi utile in futuro, lo storico della DBA assistenza viene copiato nel nuovo contratto.

## <a name="modify-the-template-bom"></a>Modifica delle DBA modello

Se la DBA modello non è stata collegata a un oggetto assistenza, è possibile modificarla o eliminare righe al suo interno. Una volta che la DBA modello è stata collegata a un oggetto assistenza, è possibile modificare solo la versione locale della DBA. Per duplicare l'impostazione di una versione locale della DBA modello, è possibile creare una nuova DBA modello in base alla versione locale. Per ulteriori informazioni, consultare [Modificare una DBA assistenza](modify-service-bom.md).

Se si sostituisce un articolo incluso nella DBA, è possibile registrare la sostituzione nella riga DBA in Designer DBA. Facoltativamente, è possibile creare una riga di ordine di assistenza per l'oggetto di sostituzione. Se viene creata una riga di ordine di assistenza, è possibile fatturare l'articolo di sostituzione. Se non si crea una riga di ordine di assistenza per una sostituzione, la registrazione della sostituzione viene mantenuta per tenere traccia dello storico dell'oggetto assistenza.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>Modifica della modalità di visualizzazione delle informazioni nella riga DBA

È possibile modificare il modo in cui le informazioni sulla riga DBA vengono visualizzate per tutte le DBA modello e assistenza. Le modifiche vengono applicate a tutte le DBA modello e assistenza, incluse quelle collegate agli oggetti assistenza.

## <a name="set-up-number-sequences-for-template-boms"></a>Impostazione di sequenze numeriche per le DBA modello

Per utilizzare le DBA modello, è necessario impostare due sequenze numeriche. Impostare una sequenza numerica per la DBA modello e una per il numero di riga dello storico DBA.

> [!NOTE]
> Le sequenze numeriche vengono utilizzate per allocare gli identificatori ai record che li richiedono. Prima di poter assegnare una sequenza numerica a una DBA modello o a un numero di riga dello storico DBA, è necessario impostare i codici delle sequenze numeriche.

## <a name="set-up-number-sequences"></a>Imposta sequenze numeriche

1. Nella pagina elenco **Sequenze numeriche** creare le sequenze numeriche per le DBA modello e il numero di riga dello storico DBA.
1. Selezionare **Gestione dei servizi** \> **Impostazione** \> **Parametri di gestione dei servizi**.
1. Selezionare **Sequenze numeriche**, quindi selezionare un codice di sequenza numerica per i riferimenti alle sequenze numeriche creati nel modulo **Sequenze numeriche** .
1. Chiudere il modulo per salvare le modifiche.

> [!NOTE]
> Il numero di riga dello storico DBA viene utilizzato dal sistema per associare le transazioni nello storico DBA a un contratto o un ordine di assistenza. Il numero non viene visualizzato nell'interfaccia utente.

## <a name="see-also"></a>Vedere anche

[Creare una DBA modello](create-template-bom.md)

[Gestire le DBA modello per le relazioni di oggetti](manage-template-boms-on-object-relations.md)

[Modificare una DBA assistenza](modify-service-bom.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
