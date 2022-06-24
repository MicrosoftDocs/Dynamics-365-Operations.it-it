---
title: DBA cespiti
description: In questo articolo vengono descritte le distinte base (DBA) dei cespiti in Gestione cespiti
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 71b861ec31e704e001aab29245b9e24ce8beb0de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882781"
---
# <a name="asset-boms"></a>DBA cespiti

[!include [banner](../../includes/banner.md)]

 

In questo articolo vengono descritte le distinte base (DBA) dei cespiti in Gestione cespiti La **DBA cespiti** mostra un elenco di tutti gli articoli (pezzi di ricambio e altri articoli) utilizzati in un cespite durante la sua intera vita. Quando si crea un nuovo cespite, è necessario valutare la possibilità di configurare una DBA per il cespite come parte della procedura di impostazione. In questo modo, è possibile tenere traccia dello storico degli articoli per il cespite dalla data di creazione.

Dopo aver completato un processo di manutenzione e aver registrato il consumo di articoli in un ordine di lavoro, è possibile tenere traccia del consumo di pezzi di ricambio e altri articoli utilizzati nel cespite. Questa funzionalità consente di gestire un record di consumo articoli completo per tutti i cespiti. Ad esempio, è possibile utilizzare il record per monitorare se un pezzo di ricambio specifico viene sostituito spesso, o per tenere traccia dei pezzi di ricambio o altri articoli attualmente utilizzati in un cespite.

> [!NOTE]
> In un ordine di lavoro, il consumo di articoli può includere sia i pezzi di ricambio che altri articoli supplementari, ad esempio, lubrificanti, i bulloni e le guarnizioni.

Una DBA cespiti può essere aggiornata automaticamente in base all'impostazione specificata in Gestione cespiti. Se uno stato del ciclo di vita dell'ordine di lavoro è stato creato per la gestione degli ordini di lavoro finiti o completati e se l'opzione **Aggiorna DBA cespiti** per quello stato del ciclo di vita dell'ordine di lavoro è **Sì** nella pagina **Stati del ciclo di vita dell'ordine di lavoro**, tutti gli articoli utilizzati nell'ordine di lavoro verranno aggiornati automaticamente nella pagina **DBA cespiti** quando l'ordine di lavoro viene aggiornato a quello stato del ciclo di vita. 


È inoltre possibile aggiornare manualmente un DBA cespiti creando nuove righe articolo nella pagina **DBA cespiti**.

Nella pagina **DBA cespiti**, è possibile tenere traccia dello storico dei pezzi di ricambio per i cespiti dopo che il consumo articoli viene registrato in un ordine di lavoro. Per utilizzare questa funzionalità, è necessario selezionare i gruppi di articoli da utilizzare per la registrazione dei pezzi di ricambio nella pagina **Gruppi di articoli pezzi di ricambio**.

Per utilizzare la funzionalità DBA cespiti, è innanzitutto necessario impostare i gruppi di articoli di pezzi di ricambio richiesti. Quindi, se si desidera che la DBA cespiti venga aggiornata automaticamente quando un ordine di lavoro è stato completato, è possibile impostare uno stato del ciclo di vita dell'ordine di lavoro per gestire tale aggiornamento. 


## <a name="set-up-spare-parts-item-groups"></a>Impostare gruppi di articoli di pezzi di ricambio

L'impostazione di storico dei pezzi di ricambio si basa sui gruppi di articoli creati nel modulo **Gestione articoli e magazzino**. In Gestione cespiti, è necessario impostare i gruppi di articoli in modo che sia possibile tenere traccia dello storico dei pezzi di ricambio per gli articoli nei gruppi di articoli selezionati.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespite** \> **Gruppi di articoli pezzi di ricambio**.
2. Selezionare **Nuovo** per impostare un gruppo di articoli.
3. Nel campo **Gruppo di articoli**, selezionare il gruppo. Il nome del gruppo verrà immesso automaticamente nel campo **Nome**.

## <a name="view-and-update-asset-boms"></a>Visualizzare e aggiornare le DBA cespiti

Dopo la registrazione del consumo di articoli in un ordine di lavoro, è possibile visualizzare il consumo articoli registrato nella pagina **DBA cespiti**.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Cespiti attivi**. Selezionare il cespite dall'elenco e quindi selezionare **DBA cespiti**.

    > [!NOTE]
    > Per visualizzare tutte le registrazioni del consumo articoli in tutti i cespiti, selezionare **Gestione cespiti** \> **Richieste di informazioni** \> **Cespiti** \> **DBA cespiti**.

2. Seleziona **Aggiorna DBA cespiti**. È possibile aggiungere i cespiti, i tipi di cespite e le risorse all'aggiornamento, secondo le esigenze, selezionando **Seleziona**. Selezionare **OK** per avviare l'aggiornamento. È inoltre possibile impostare la funzione di aggiornamento come processo batch.
3. Se si desidera visualizzare ulteriori informazioni correlate agli articoli, è possibile aggiungere le dimensioni inventariali. Selezionare **Inventario** \> **Visualizzazione dimensioni** e quindi selezionare le caselle di controllo relative alle dimensioni che si desidera visualizzare. Per gestire questa impostazione per tutti i cespiti nella pagina **DBA cespiti**, impostare l'opzione **Salva impostazione** su **Sì**.
4. Per ottenere una panoramica di dove in Gestione cespiti l'articolo nella riga selezionata viene utilizzato in relazione ai cespiti, ai valori predefiniti di tipo di processo, pezzi di ricambio e ordini di lavoro, selezionare **Articolo utilizzato in**. 
5. Se si desidera visualizzare solo le righe articolo attive, selezionare **Visualizza** \> **Corrente**. Per visualizzare tutte le righe articolo, incluse le righe in cui la data di scadenza è precedente alla data corrente, selezionare **Visualizza** \> **Tutti**.

> [!NOTE]
> Dopo aver completato un ordine di lavoro, se alcuni articoli o pezzi di ricambio relativi al cespite correlato sono scaduti o sono stati sostituiti da altri articoli o pezzi di ricambio, si consiglia di aggiornare di conseguenza la DBA cespiti.

## <a name="create-a-new-item-line-in-an-asset-bom"></a>Creare una nuova riga articolo in una DBA cespiti

È possibile creare manualmente righe articolo per i cespiti.

1. Nella pagina **DBA cespiti**, selezionare **Nuovo**.
2. Nel campo **Cespite**, selezionare il cespite per cui aggiungere una riga dell'articolo.
3. Immettere un numero di riga sequenziale nel campo **Numero riga**.
4. Nel campo **Validità** immettere una data di inizio per l'articolo.
5. Se l'articolo scadrà, nel campo **Scadenza**, immettere una data di fine.
6. Nel campo **Numero articolo**, selezionare l'articolo. Il nome verrà immesso automaticamente nel campo **Nome prodotto**.
7. Nel campo **Quantità** immettere la quantità usata. Il campo **Unità** viene aggiornato automaticamente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]