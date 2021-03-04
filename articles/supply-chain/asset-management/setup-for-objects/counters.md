---
title: Misure dei cespiti
description: Nell'argomento viene descritto come creare tipi di misure dei cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCounterPart, EntAssetObjectCounterLookup, EntAssetCounterType, EntAssetObjectCounterTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: adadb1df7b41488fad496f937ecbc24e0761e42d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431256"
---
# <a name="counters"></a>Contatori

[!include [banner](../../includes/banner.md)]

Nell'argomento viene descritto come creare tipi di contatore in Gestione cespiti. I tipi di contatore vengono utilizzati per effettuare le registrazioni di contatore, ad esempio, in relazione al numero di ore di produzione, oppure della quantità prodotta nei cespiti. I tipi di cespiti sono correlati ai tipi di contatore. Questo significa che un contatore può essere utilizzato per un cespite solo se è impostato per il tipo utilizzato per il cespite.

Prima di effettuare le registrazioni di contatore, creare innanzitutto i tipi di contatore da utilizzare in **Contatori**. A questo punto, è possibile creare le registrazioni di contatore in **Contatori**. 

I contatori possono essere utilizzati nei piani di manutenzione. Una riga del piano di manutenzione può essere di tipo "Contatore", ad esempio, in relazione al numero di ore di produzione o la quantità prodotta. 

Una registrazione di contatore può essere aggiornata manualmente oppure automaticamente in base alle ore di produzione o la quantità prodotta. Un contatore può essere impostato per utilizzare uno dei tre metodi di aggiornamento (selezionato nel campo **Aggiornamento** in **Contatori**):
  
- Manuale: è necessario registrare manualmente i valori di contatore.  
- Ore di produzione - il contatore viene aggiornato automaticamente in base al numero di ore di produzione.  
- Quantità di produzione - il contatore viene aggiornato automaticamente in base alla quantità prodotta.  

>[!NOTE]
>Se la quantità prodotta viene utilizzata, *tutti* gli articoli registrati vengono inclusi nella registrazione del contatore, la quantità idonea nonché la quantità difettosa. È sempre possibile effettuare registrazioni manuali di contatori, se necessario.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Creare i tipi di contatore per le registrazioni dei contatori dei cespiti

1. Selezionare **Gestione cespiti** > **Impostazioni** > **Tipi di cespite** > **Contatori**.
2. Selezionare **Nuovo** per creare un tipo di contatore.
3. Immettere un ID nel campo **Contatore** e un nome di contatore nel campo **Nome**.
4. Nella Scheda dettaglio **Generale**, selezionare un'unità contatore nel campo **Unità**.
5. Nel campo **Aggiornamento**, selezionare il metodo di aggiornamento da utilizzare per il contatore.
6. Selezionare "Sì" sull'interruttore **Eredita valori contatore** se i cespiti figlio in una struttura dei cespiti devono ereditare automaticamente le registrazioni di contatore effettuate sul cespite padre.
7. Nel campo **Totale aggregato** selezionare il metodo di sommatoria da utilizzare per un contatore che utilizza questo tipo di contatore. "Somma" è la selezione predefinita utilizzata per aggiungere continuamente i valori registrati al valore totale. "Media" può essere utilizzato se un contatore è impostato per monitorare una soglia, ad esempio, in relazione alla temperatura, vibrazioni, o l'usura di un cespite. 
8. Nel campo **Scostamento sopra**, inserire il livello percentuale superiore per convalidare se le registrazioni manuali di contatore sono comprese in un determinato intervallo previsto. La convalida è basata su un aumento lineare nelle registrazioni di contatore esistenti.
9. Nel campo **Scostamento sotto**, inserire il livello percentuale inferiore per convalidare se le registrazioni manuali di contatore sono comprese in un determinato intervallo previsto. La convalida è basata su una riduzione lineare nelle registrazioni di contatore esistenti.
10. Nel campo **Tipo**, selezionare il tipo di messaggio (informazioni, avviso, errore) da visualizzare se gli scostamenti dall'intervallo definito si verificano quando si eseguono registrazioni manuali di contatore.
11. Nella Scheda dettaglio **Tipi di cespite**, aggiungere i tipi di cespite che devono poter utilizzare il contatore.
12. Nella Scheda dettaglio **Contatori di cespiti correlati**, aggiungere il contatore che si desidera aggiornare automaticamente questa il contatore viene aggiornato.


>[!NOTE]
>Un contatore correlato viene aggiornato automaticamente solo se il contatore correlato ha il tipo di cespite, a cui è correlato, nell'impostazione di contatore. Ad esempio: si supponga di impostare un contatore per "Ore di produzione" e aggiungere il tipo di cespite "Truck Engine". Quando quel contatore viene aggiornato, un contatore correlato "Oil" verrà anche aggiornato con gli stessi valori del contatore. L'impostazione in **Contatori** include l'impostazione in "Ore". Inoltre, nel contatore "Oil", il tipo di cespite "Truck Engine" deve essere aggiunto alla Scheda dettaglio **Tipi di cespite** per garantire la relazione di contatore. Vedere le schermate di seguito per un esempio dell'impostazione dei contatori Ore e Oil.

Quando i tipi di cespite vengono aggiunti a un tipo di contatore in **Contatori**, quel contatore viene aggiunto automaticamente ai tipi di cespite nella Scheda dettaglio **Contatori** in [Tipi di cespite](../setup-for-objects/object-types.md).

![Figura 1](media/071-setup-for-objects.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]