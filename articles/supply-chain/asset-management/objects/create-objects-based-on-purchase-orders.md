---
title: Creare cespiti in base agli ordini fornitore
description: In questo articolo viene descritto come è possibile creare un elenco degli articoli cespite che è possibile utilizzare come base per creare i cespiti per i processi di gestione in Gestione cespiti.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccd14493aac6484dc54ccf51ae159a071c8697a5
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015611"
---
# <a name="create-assets-based-on-purchase-orders"></a>Creare cespiti in base agli ordini fornitore

[!include [banner](../../includes/banner.md)]

 

In questo articolo viene descritto come è possibile creare un elenco degli articoli cespite che è possibile utilizzare come base per creare i cespiti per i processi di gestione in Gestione cespiti. A seconda degli articoli cespite, è possibile visualizzare un elenco di righe ordine fornitore create per tali articoli. Lo scopo di questa funzionalità è creare facilmente un cespite in Gestione cespiti in base a un ordine fornitore.

Innanzitutto, vengono impostati gli articoli da utilizzare per creare i cespiti da un ordine fornitore in **Articoli cespite**. Dopo la creazione di una riga ordine fornitore, creare i cespiti in **Cespiti in sospeso**. È possibile decidere a quale fase dell'ordine fornitore il cespite deve essere creata.


## <a name="select-asset-items"></a>Selezionare articoli cespite

1. Fare clic **Gestione cespiti** > **Impostazione** > **Cespiti** > **Articoli**.
2. Fare clic su **Nuovo** per creare un nuovo articolo cespite.
3. Nel campo **Numero articolo**, selezionare l'articolo. Quando si lascia il campo, il nome dell'articolo viene automaticamente inserito nel campo **Nome prodotto**.
4. Nella Scheda dettaglio **Generale**, selezionare un tipo di cespite per l'articolo.
5. Selezionare il produttore e il modello del cespite per l'articolo.
6. Salvare l'articolo.


## <a name="create-assets-from-pending-assets"></a>Creare cespiti dai cespiti in sospeso

1. Seleziona **Gestione cespiti** > **Cespiti** > **Cespiti in sospeso**.
2. Vedrete un elenco aggiornato di ordini fornitore in base agli articoli selezionati **Elementi cespite**.
3. È possibile filtrare lo stato degli ordini fornitore per selezionare a quale stato del ciclo di vita il cespite deve essere creato. Per esempio, è possibile creare cespiti solo quando un'entrata prodotti è stata registrata in un ordine fornitore.
4. Selezionare il collegamento **Numero di riferimento** in una riga ordine fornitore per visualizzare informazioni dettagliate sull'articolo.
5. Per modificare le dimensioni visualizzate nella Scheda dettaglio **Dimensioni inventariali**, fare clic sul pulsante **Visualizza dimensioni** e selezionare le opzioni desiderate.
6. Se si desidera creare un cespite in base a una riga di ordine fornitore, selezionare la casella di controllo nella colonna **Contrassegna** per la riga nella pagina elenco e fare clic su **Crea cespiti**. Verrà visualizzato un messaggio in cui viene comunicato l'ID del cespite.
7. Selezionare il cespite nell'elenco **Tutti i cespiti** e fare clic sul pulsante **Modifica** per aggiungere ulteriori informazioni sul cespite.
8. In **Cespiti in sospeso**, se si desidera eliminare una riga poiché non si desidera creare un cespite, selezionare la casella di controllo nella colonna **Contrassegna** per la riga e clic su **Elimina cespiti in sospeso**. Verrà visualizzato un messaggio in cui viene comunicato l'ID del cespite. Non si stanno eliminando l'ordine fornitore o l'ordine cliente, solo il record da cui è possibile creare un cespite in **Gestione cespiti**.

>[!NOTE]
>Tutte le dimensioni prodotto (dimensione, colore, configurazione e così via.) verranno trasferite automaticamente agli attributi del cespite. Le dimensioni di tracciabilità (numero di serie) sono archiviate direttamente nel cespite quando il cespite è creato.


## <a name="find-pending-assets"></a>Trovare cespiti in sospeso

È possibile eseguire un **Conteggio cespiti in sospeso** per verificare i cespiti in sospeso. Ad esempio, questa funzione può essere utilizzata per la ricezione di una notifica ogni volta che un cespite in sospeso è pronto per essere creato come cespite.

1. Selezionare **Gestione cespiti** > **Periodico** > **Cespiti** > **Conteggio cespiti in sospeso**.
2. Fare clic **OK** per eseguire il processo e aggiornare l'elenco **Cespiti in sospeso**.
3. È possibile impostare il processo per l'esecuzione come processo batch, ad esempio, una volta ogni giorno.

**Attenzione:** Se i dati vengono modificati in un ordine fornitore *dopo* aver creato un cespite in base all'articolo pertinente, le modifiche non verranno riflesse nel cespite.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]