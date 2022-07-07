---
title: Valutazione della condizione
description: In questo articolo viene descritto come creare un modello e una registrazione di valutazione delle condizioni di un cespite in Gestione cespiti.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c43424a0955d7a046186e8a4120c050990df6060
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015058"
---
# <a name="condition-assessment"></a>Valutazione della condizione

[!include [banner](../../includes/banner.md)]

 

In questo articolo viene descritto come creare un modello e una registrazione di valutazione delle condizioni di un cespite in Gestione cespiti. La valutazione delle condizioni viene eseguita a intervalli regolari e l'obiettivo principale è di creare e gestire i dati di condizione sui cespiti. Visto da una prospettiva di manutenzione preventiva, è importante monitorare le informazioni come la condizione attuale e la durata rimanente. Inoltre, se si effettua la valutazione delle condizioni a intervalli regolari, sarà possibile monitorare e confrontare le condizioni dei macchinari nella fabbrica.

Valutazione delle condizioni può essere utilizzata per misurare e monitorare molte condizioni nelle attrezzature. Esempio: È possibile misurare le vibrazioni del macchinario. Dopo la registrazione delle misure delle vibrazioni in Gestione cespiti dei vari tipi di attrezzature, è possibile eseguire la ricerca dell'ultima valutazione registrata e visualizzare le misure delle vibrazioni.

Valutazione delle condizioni viene creata sui cespiti. Si deve configurare un modello di valutazione delle condizioni per un tipo di cespite prima di eseguire la procedura di valutazione delle condizioni. Motivo per utilizzare i modelli per la valutazione delle condizioni è evitare la variazione dei dati di condizione per cespiti simili. La sequenza per la configurazione e l'utilizzo della valutazione delle condizioni in Gestione cespiti è: Innanzitutto si impostano i modelli necessari per la valutazione delle condizioni. A questo punto, associare i modelli con i tipi di cespite nel modulo **Tipi di cespite**. Infine, è possibile creare registrazioni di valutazione delle condizioni di un cespite nel modulo **Cespite**.

## <a name="create-a-condition-assessment-template"></a>Creare un modello di valutazione delle condizioni

1. Selezionare **Gestione cespiti** > **Impostazione** > **Tipi di cespite** > **Valutazione delle condizioni**.
2. Selezionare **Nuovo** per creare un nuovo modello.
3. Nel campo **Modello**, digitare un ID per il modello.
4. Nel campo **Nome** immettere un nome per il modello.
5. Nella Scheda dettaglio **Righe di valutazione condizione** aggiungere le righe necessarie per la valutazione delle condizioni, inclusa la selezione del tipo di condizione e dell'unità di misura appropriati.
6. Nella Scheda dettaglio **Tipi di cespite**, aggiungere i tipi di cespite che devono utilizzare il modello di valutazione delle condizioni.
7. Nei campi **Righe** e **Tipi di cespite** nel gruppo **Dettagli** nella parte superiore della schermata, vedrete il numero di righe di valutazione e i tipi di cespit correlati al modello di valutazione delle condizioni selezionato.


## <a name="create-condition-assessment-registration-on-an-asset"></a>Creare una registrazione di valutazione delle condizioni per un cespite

1. Seleziona **Gestione cespiti** > **Cespiti** > **Tutti i cespiti**.
2. Nell'elenco, selezionare il cespite per cui si desidera creare una valutazione delle condizioni.
3. Nella scheda **Generale** fare clic su **Valutazione delle condizioni**.
4. Fare clic su **Nuovo** per creare una nuova registrazione.
5. Selezionare la data per la valutazione delle condizioni nel campo **Data**.
6. Selezionare il nome del lavoratore che ha eseguito la registrazione di valutazione prezzo nel campo **Lavoratore**.
7. Nel campo **Righe**, vengono visualizzati il numero delle righe di valutazione configurate per la valutazione delle condizioni.
8. Selezionare un modello per la valutazione delle condizioni nel campo **Modello**. Il nome del modello viene automaticamente inserito nel campo **Nome** e le righe di registrazione correlate vengono immesse nella Scheda dettaglio **Righe di valutazione condizione**.
9. È possibile inserire note relative alla valutazione delle condizioni selezionata nella Scheda dettaglio **Note**.
10. Per ciascuna riga di valutazione delle condizioni, inserire i dati di misura nel campo **Valore**.
11. È possibile inserire un commento riguardante la riga registrazione selezionata nella Scheda dettaglio **Righe di valutazione condizione** > campo **Commenti**. Se si aggiunge un commento su una riga, la casella di controllo **Commento** verrà selezionata automaticamente.

Dopo avere effettuato una registrazione di valutazione delle condizioni di un cespite, è possibile stampare un report della valutazione delle condizioni.

>[!NOTE]
>È anche possibile registrare la valutazione delle condizioni in un ordine di lavoro (**Gestione cespiti** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** > **Valutazione delle condizioni**).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]