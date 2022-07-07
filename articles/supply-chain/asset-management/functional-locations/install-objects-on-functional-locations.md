---
title: Installare cespiti nelle unità funzionali
description: In questo articolo viene illustrato come installare cespiti nelle unità funzionali in Gestione cespiti.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationObjectChange, EntAssetFunctionalLocationObjectInstall, EntAssetFunctionalLocationObject
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3ae571f4ad7210b31d212b0472610b36dc5c488b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016074"
---
# <a name="install-assets-on-functional-locations"></a>Installare cespiti nelle unità funzionali

[!include [banner](../../includes/banner.md)]

 

Dopo aver creato le strutture di unità funzionali, sarà necessario installare i cespiti nelle unità funzionali pertinenti. In questo articolo viene illustrato come installare cespiti in tali unità funzionali in Gestione cespiti. Per informazioni sulla modalità di creazione dei cespiti, vedere [Introduzione ai cespiti](../objects/introduction-to-objects.md).

Se è stata creata una struttura di cespiti, l'intera struttura di cespiti deve essere installata in un'unità funzionale. Di conseguenza, solo i cespiti padre (cespiti di primo livello che non hanno cespite padre) possono essere selezionati in un'unità funzionale. Tutti i cespiti correlati figlio (cespiti secondati) verranno anche installati nell'unità funzionale. Quando si installano i cespiti in un'unità funzionale, le dimensioni finanziarie dell'unità funzionale possono essere trasferite automaticamente a essi, in base alle impostazioni del tipo di unità funzionale selezionato per l'unità funzionale. Per ulteriori informazioni su come impostare i tipi di unità funzionale, vedere [Tipi di unità funzionali](../setup-for-functional-locations/functional-location-types.md).

> [!NOTE]
> È possibile impostare i tipi di cespite nel tipo di unità funzionale utilizzato per una unità funzionale. In questo caso, quando si installano i cespiti nella unità funzionale, solo i cespiti padre con lo stesso tipo di cespite vengono visualizzati nell'elenco di cespiti che possono essere installati nell'unità funzionale.

Dopo aver installato i cespiti in un'unità funzionale, è possibile sostituire un cespite padre o una struttura di cespiti in base alle esigenze. Come quando si installano i cespiti, selezionare un cespite padre da sostituire. Tutti i cespiti figlio correlati vengono anche sostituiti. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>Installare una struttura di cespiti in una unità funzionale

1. Seleziona **Gestione cespiti** \> **Unità funzionali** \> **Tutte le unità funzionali** o **Unità funzionali attive**.
2. Selezionare l'unità funzionale in cui installare un cespite.
3. Selezionare **Installa cespite**.

    Nella sezione **Attributi** verrà visualizzato un elenco dei requisiti di attributi cespite impostati nel tipo di unità funzionale selezionato per l'unità funzionale. Gli attributi hanno solo scopo informativo. Il sistema non convalida gli attributi rispetto agli attributi cespite impostati nel cespite che si installa. Tale operazione di convalida va fatta dopo la selezione di un cespite nel campo **Cespite**.

4. Nel campo **Cespite**, selezionare il cespite padre per installare. Tutti i cespiti correlati figlio vengono inclusi automaticamente nell'installazione.

    Nella sezione **Attributi cespiti** a destra dell'elenco cespiti sono indicati gli attributi cespite correlati al cespite selezionato.

5. Nel campo **Validità**, selezionare la data e l'ora da cui è valida l'installazione del cespite. Dopo tale data e l'ora, i costi del cespite e dei cespiti secondari correlati verranno correlati alla unità funzionale.

    > [!NOTE]
    > Gli attributi cespite impostati sul cespite vengono aggiunti alla sezione **Attributi**. Ad esempio, il requisito di attributo **Peso** è stato aggiunto come requisito sia per il cespite che per la unità funzionale. Se il cespite ha requisiti di attributi dello stesso tipo dell'unità funzionale, i valori dei requisiti di attributi del cespite verranno immessi nei campi **Valore**. Di conseguenza, è possibile convalidare i valori del cespite rispetto ai requisiti di attributi impostati per l'unità funzionale. I requisiti di attributo impostati per l'unità funzionale vengono contrassegnate con un segno di spunta.

6. Selezionare **OK**.

    > [!NOTE]
    > Per modificare l'installazione di un cespite installandolo in una nuova unità funzionale, effettuare i passaggi da 1 a 6 di questa procedura. Quando si installa un cespite in una nuova unità funzionale, il cespite è disinstallato automaticamente da quella precedente. Tutte le richieste di interventi di manutenzione o ordini di lavoro attivi creati per il cespite prima di installarlo in una nuova unità funzionale **non** vengono trasferiti automaticamente nella nuova unità funzionale. Se tali richieste di intervento di manutenzione e ordini di lavoro sono ancora necessari per il cespite, è necessario ricrearli manualmente dopo che il cespite viene installato nella nuova ubicazione.

7. Per visualizzare un elenco di tutti i cespiti, inclusi i cespiti secondari, installati nell'unità funzionale, selezionare l'unità funzionale nella pagina **Tutte le unità funzionali** e selezionare **Cespiti**.
8. Per visualizzare l'elenco delle richieste di intervento di manutenzione attive, gli ordini di lavoro attivi, ovvero le registrazioni di problemi correlati ai cespiti installati in un'unità funzionale, selezionare l'unità funzionale nella pagina **Tutte le unità funzionali** e quindi **Richieste**, **Ordini di lavoro** o **Errori**.

> [!NOTE]
> Quando i dati correlati al cespite vengono modificati, vengono aggiornati automaticamente nella unità funzionale in cui il cespite è installato. Questo aggiornamento automatico riguarda le modifiche alle richieste di intervento di manutenzione, ordini di lavoro, alle registrazioni di problemi del cespite, alle registrazioni di tempi di fermo per la manutenzione e alle registrazioni delle misure del cespite.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>Creare automaticamente un solo cespite in una unità funzionale

È possibile impostare fasi di unità funzionale e tipi di unità funzionali per gestire la creazione automatica di *un solo* cespite in una unità funzionale. Il cespite ottiene lo stesso ID e nome dell'unità funzionale. Questa funzionalità può risultare utile quando ci si occupa della manutenzione di un cespite grande e statico, ad esempio un edificio.

Prima di creare automaticamente un cespite in una unità funzionale, i seguenti dati di impostazione devono essere disponibili:

- Creare un tipo di unità funzionale per gestire la creazione automatica di un cespite. Nel campo **Tipo di cespite**, selezionare un tipo di cespite. Per ulteriori informazioni, vedere [Tipi di unità funzionali](../setup-for-functional-locations/functional-location-types.md).
- Creare uno stato del ciclo di vita delle unità funzionali per gestire la creazione automatica di un cespite. Impostare l'opzione **Crea cespite** su **Sì**. Per ulteriori informazioni, vedere [Stati del ciclo di vita delle unità funzionali](../setup-for-functional-locations/functional-location-stages.md).

Dopo che i dati di impostazione sono disponibili, si è pronti a creare un cespite.

1. Nella pagina **Tutte le unità funzionali**, verificare che l'unità funzionale in cui si desidera creare automaticamente il cespite utilizza il tipo di unità funzionale creato a questo scopo.
2. Selezionare l'unità funzionale nell'elenco.
3. Selezionare **Aggiorna stato dell'unità funzionale** e quindi selezionare lo stato del ciclo di vita creato a questo scopo. Un solo cespite verrà installato automaticamente nell'unità funzionale. Il cespite ha lo stesso ID e nome dell'unità funzionale.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]