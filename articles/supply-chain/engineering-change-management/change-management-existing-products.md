---
title: Abilitare la gestione delle modifiche in prodotti esistenti
description: In questo argomento viene descritto come abilitare la gestione delle modifiche per i prodotti esistenti. Descrive anche i casi in cui la tua capacità di abilitare la gestione delle modifiche è limitata.
author: t-benebo
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 45c5774ac1f6db5845d6be6bf2f5d8f99063ea07
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488204"
---
# <a name="enable-change-management-on-existing-products"></a>Abilitare la gestione delle modifiche in prodotti esistenti

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come abilitare la gestione delle modifiche per i prodotti esistenti. Descrive anche i casi in cui la tua capacità di abilitare la gestione delle modifiche è limitata.

Quando si abilita la gestione delle modifiche per un prodotto esistente, è possibile creare versioni di quel prodotto e tenere traccia delle modifiche apportate allo stesso nel corso dell'intero ciclo di vita. Pertanto, è possibile tenere traccia di tali modifiche utilizzando ordini di modifica. Per abilitare la gestione delle modifiche, è necessario convertire i prodotti pertinenti in *articoli di progettazione* (noti anche come prodotti di progettazione). I prodotti di progettazione sono prodotti con versione e gestiti tramite la gestione delle modifiche. Viene fornita una procedura guidata relativa al processo di conversione.

## <a name="turn-on-the-feature-in-your-system"></a>Attiva la funzionalità nel tuo sistema

Per utilizzare questa funzionalità, è necessario completare le seguenti attività:

1. Abilitare la funzionalità Gestione delle modifiche di progettazione e la relativa chiave di configurazione come descritto in [Panoramica di Gestione delle modifiche di progettazione](product-engineering-overview.md).
1. Attivare la funzionalità *Abilita gestione modifiche in prodotti esistenti* in Gestione funzionalità. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="restrictions-and-limitations"></a>Restrizioni e limitazioni

Non tutti i tipi di prodotto possono essere convertiti in tutti gli altri tipi. Si applicano le seguenti restrizioni e limitazioni:

- Quando si converte un prodotto in un prodotto di progettazione, rimane un *prodotto*. Non diventa una *rappresentazione generale prodotto*.
- Quando si converte una rappresentazione generale prodotto che ha un insieme specifico di dimensioni, tali dimensioni vengono mantenute dopo la modifica. Ad esempio, se si converte una rappresentazione generale prodotto che ha la dimensione di tipo dimensione, manterrà questa dimensione.

Pertanto, se si dispone di un prodotto specifico, è possibile modificarlo solo in un prodotto di progettazione che non tiene traccia della dimensione del prodotto nelle transazioni (ovvero, la dimensione della versione non viene utilizzata). Per ulteriori informazioni su questi problemi, vedere le altre sezioni in questo argomento.

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>Preparare la conversione creando tutte le categorie di prodotti di progettazione necessarie

Una *categoria di prodotto di progettazione* deve essere assegnata a ogni prodotto di progettazione. Questa assegnazione verrà eseguita quando si esegui la procedura guidata **Convertire in prodotto di progettazione**. Le categorie di prodotti di progettazione devono esistere per tutti i prodotti standard pertinenti *prima* di poter convertire quei prodotti.

La categoria di prodotti di progettazione fornisce una base per la creazione di un prodotto di progettazione e stabilisce una serie di criteri e valori predefiniti. Gli attributi di progettazione e i loro valori predefiniti (come definiti per la categoria di progettazione) vengono applicati anche al prodotto di progettazione risultante. È possibile modificare i valori degli attributi e/o aggiungere altri attributi di progettazione al prodotto risultante, se necessario.

La categoria di prodotti di progettazione deve corrispondere al prodotto a cui viene assegnata. Ad esempio, il tipo di prodotto e il gruppo di dimensioni devono corrispondere sia al prodotto che alla relativa categoria di prodotti di progettazione. Per ulteriori informazioni, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).

> [!IMPORTANT]
> La procedura guidata **Convertire in prodotto di progettazione** può convertire il prodotto solo in prodotti di progettazione in cui non si tiene traccia della versione nelle transazioni. Quindi, l'opzione **Tenere traccia delle versioni nelle transazioni** deve essere impostata su *No* per le categorie di prodotti di progettazione create per convertire i prodotti esistenti.

Per ulteriori informazioni su come creare categorie di prodotti di progettazione, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>Eseguire la procedura guidata Convertire in prodotto di progettazione

La procedura guidata **Convertire in prodotto di progettazione** consente di convertire uno o più prodotti esistenti in prodotti di progettazione. Converte i prodotti in prodotti di progettazione (prodotti con versione) in cui non si tiene traccia della versione nelle transazioni (ovvero, la dimensione della versione non viene utilizzata). Una volta completata la conversione, è possibile gestire i prodotti utilizzando Gestione modifiche di progettazione.

La conversione è permanente. Pertanto, non sarà possibile annullarla in seguito. 

Ogni prodotto di progettazione convertito continuerà a essere rilasciato nelle stesse aziende in cui è stato rilasciato il prodotto originale. Tuttavia, la distinta base di progettazione e gli itinerari non verranno rilasciati automaticamente a tali aziende.

Attenersi ai passaggi seguenti per eseguire la procedura guidata **Convertire in prodotto di progettazione** e convertire un prodotto in un prodotto di progettazione.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nella griglia, selezionare la caselle di controllo di ogni prodotto che si desidera convertire.
1. Nel riquadro Azioni, nella scheda **Progettazione**, nel gruppo **Gestione modifiche di progettazione** selezionare **Convertire in prodotto di progettazione** per aprire la procedura guidata.
1. La prima pagina della procedura guidata è la **pagina iniziale**. Se non si conosce il processo di conversione, leggere attentamente le informazioni in questa pagina. Quando si è pronti, selezionare **Avanti**.
1. La pagina **Selezionare i dettagli dei prodotti da convertire** mostra ogni prodotto selezionato prima di aprire la procedura guidata. Esaminare l'elenco. Utilizzare i pulsanti **Nuovo** e **Elimina** nella barra degli strumenti per aggiungere o rimuovere prodotti come necessario.
1. Utilizzare i seguenti campi nella parte superiore della griglia per assegnare valori predefiniti a ogni prodotto elencato (sarà possibile modificare questi valori per singoli prodotti dopo il completamento della conversione). I valori predefiniti non verranno assegnati ai prodotti per i quali è già stato assegnato un valore pertinente.

    - **Categoria di prodotti di progettazione predefinita** - Selezionare una categoria di prodotti di progettazione iniziale da assegnare a ogni prodotto elencato. La categoria selezionata verrà applicata solo ai prodotti con essa compatibili.
    - **Versione predefinita** - Immettere la versione del prodotto iniziale da assegnare a ogni prodotto elencato. Ogni prodotto di progettazione ha almeno una versione di progettazione.
    - **Stato predefinito del ciclo di vita** - Selezionare lo stato del ciclo di vita del prodotto iniziale da assegnare a ogni prodotto elencato.
    - **La distinta base corrente sarà parte del prodotto di progettazione** - Selezionare questa casella di controllo se la distinta base corrente di ogni prodotto elencato deve essere utilizzata come distinta base per il prodotto di progettazione.

    Per ulteriori informazioni sulle impostazioni del prodotto, vedere il passaggio successivo.

1. Esaminare ogni prodotto elencato nella griglia e valutare in che misura i valori predefiniti assegnati si applicano ai prodotti. Per ogni riga, esaminare le seguenti informazioni e impostare i campi pertinenti:

    - **Numero prodotto** - Il numero di prodotto.
    - **Nome prodotto** - Il nome del prodotto.
    - **Categoria di progettazione** - Selezionare la categoria di prodotti di progettazione a cui il prodotto deve appartenere dopo la conversione. Per ogni prodotto deve già esistere una categoria appropriata, come descritto nella sezione precedente di questo argomento. È necessario assegnare una categoria a ogni prodotto.
    - **Versione** - Immettere la versione del prodotto da assegnare al prodotto dopo la conversione. Ad esempio, si potrebbe selezionare un numero che rientra nella sequenza numerica già utilizzata dalla categoria. Ogni versione di progettazione memorizza i dati rilevanti per la progettazione specifici per quella versione. Per ulteriori informazioni, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).
    - **Stato del ciclo di vita del prodotto** - Selezionare lo stato del ciclo di vita del prodotto in cui deve trovarsi il prodotto dopo la conversione. Lo stato del ciclo di vita del prodotto consente di determinare quali transazioni sono consentite per una data versione di progettazione. Per ulteriori informazioni, vedere [Stati e transazioni del ciclo di vita del prodotto](product-lifecycle-state-transactions.md).
    - **Con distinta base** - Una casella di controllo selezionata indica che il prodotto ha una distinta base. L'impostazione di questa casella di controllo può aiutare a decidere come impostare la casella di controllo **La distinta base corrente sarà parte del prodotto di progettazione**.
    - **La distinta base corrente sarà parte del prodotto di progettazione** - Selezionare questa casella di controllo se la distinta base corrente del prodotto deve essere utilizzata come distinta base per il prodotto di progettazione. Quella distinta base verrà quindi gestita mediante Gestione modifiche di progettazione. Se il prodotto non dispone di una distinta base o se si preferisce creare manualmente una distinta base per il prodotto convertito in un secondo momento, deselezionare questa casella di controllo.
    - **Con errori** - Una casella di controllo selezionata indica che la configurazione del prodotto presenta uno o più errori. Ad esempio, il tipo di prodotto o il gruppo di dimensioni potrebbe non corrispondere nella categoria. I prodotti con errori verranno ignorati e non verranno convertiti.

1. Al termine, selezionare **Convalida** nella barra degli strumenti per convalidare la configurazione del prodotto. Per ogni riga, la casella di controllo **Con errori** verrà aggiornata per indicare lo stato del prodotto. Modificare i valori fino a quando la configurazione di ogni prodotto è priva di errori.
1. Quando tutti i prodotti sono impostati correttamente, selezionare **Avanti** per continuare.
1. La pagina **Conferma selezione** mostra il numero di prodotti che non hanno errori nella loro configurazione e sono quindi pronti per la conversione. Mostra anche il numero di prodotti che verranno ignorati a causa di errori. Per eseguire la conversione come processo batch, impostare l'opzione **Esegui in batch** su *Sì*.
1. Selezionare **Fine** per applicare le impostazioni e iniziare a convertire i prodotti in prodotti di progettazione.

> [!NOTE]
> Se il sistema è configurato per accettare manualmente i prodotti prima che vengano rilasciati, è necessario accettare ogni prodotto convertito utilizzando la pagina **Rilasci di prodotti aperti** nelle società appropriate. Per ulteriori informazioni, vedere [Esaminare e accettare il prodotto prima di rilasciarlo nell'azienda locale](engineering-scenarios.md#accept).
