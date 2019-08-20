---
title: Misure dei cespiti
description: Nell'argomento viene descritto come creare tipi di misure dei cespiti in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783385"
---
# <a name="asset-measures"></a>Misure dei cespiti

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Nell'argomento viene descritto come creare tipi di misure dei cespiti in Gestione cespiti. I tipi di misure dei cespiti vengono utilizzati per effettuare le registrazioni di misure per i cespiti, ad esempio, in relazione al numero di ore di produzione, oppure della quantità prodotta nei cespiti. I tipi di cespiti sono correlati ai tipi di misure dei cespiti. Questo significa che una misura dei cespiti può essere utilizzata per un cespite solo se la misura è impostata per il tipo utilizzato per il cespite.

Prima di effettuare le registrazioni di misure per i cespiti, creare innanzitutto i tipi di misura dei cespiti da utilizzare in **Contatori**. A questo punto, è possibile creare le registrazioni di misure per i cespiti **Misure dei cespiti**. 

Le misure dei cespiti possono essere utilizzate nei piani di manutenzione. Una riga del piano di manutenzione può essere di tipo "Contatore", ad esempio, in relazione al numero di ore di produzione o la quantità prodotta. 

Una registrazione di misure di un cespite può essere aggiornata manualmente oppure automaticamente in base alle ore di produzione o la quantità prodotta. Una misura dei cespiti può essere impostata per utilizzare uno dei tre metodi di aggiornamento (selezionato nel campo **Aggiornamento** in **Contatori**):
  
- Manuale: è necessario registrare manualmente i valori di misura dei cespiti.  
- Ore di produzione - il contatore viene aggiornato automaticamente in base al numero di ore di produzione.  
- Quantità di produzione - il contatore viene aggiornato automaticamente in base alla quantità prodotta.  

>[!NOTE]
>Se la quantità prodotta viene utilizzata, *tutti* gli articoli registrati vengono inclusi nella registrazione delle misure, la quantità idonea nonché la quantità difettosa. È sempre possibile effettuare registrazioni manuali di misure dei cespiti, se necessario.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Creare i tipi di contatore per le registrazioni dei contatori dei cespiti

1. Selezionare **Gestione cespiti** > **Impostazioni** > **Tipi di cespite** > **Contatori**.
2. Selezionare **Nuovo** per creare un nuovo tipo di misura dei cespiti.
3. Immettere un ID nel campo **Contatore** e un nome di contatore nel campo **Nome**.
4. Nella Scheda dettaglio **Generale**, selezionare un'unità di misura nel campo **Unità**.
5. Nel campo **Aggiornamento**, selezionare il metodo di aggiornamento da utilizzare per la misura dei cespiti.
6. Selezionare "Sì" sull'interruttore **Eredita valori contatore** se i cespiti figlio in una struttura dei cespiti devono ereditare automaticamente le registrazioni di misura dei cespiti effettuate sul cespite padre.
7. Nel campo **Totale aggregato** selezionare il metodo di sommatoria da utilizzare per una misura dei cespiti che utilizza questo tipo di misura. "Somma" è la selezione predefinita utilizzata per aggiungere continuamente i valori registrati al valore totale. "Media" può essere utilizzato se una misura dei cespiti è impostata per monitorare una soglia, ad esempio, in relazione alla temperatura, vibrazioni, o l'usura di un cespite. 
8. Nel campo **Scostamento sopra**, inserire il livello percentuale superiore per convalidare se le registrazioni manuali di misura del cespite sono comprese in un determinato intervallo previsto. La convalida è basata su un aumento lineare nelle registrazioni di misura del cespite esistenti.
9. Nel campo **Scostamento sotto**, inserire il livello percentuale inferiore per convalidare se le registrazioni manuali di misura del cespite sono comprese in un determinato intervallo previsto. La convalida è basata su una riduzione lineare nelle registrazioni di misura del cespite esistenti.
10. Nel campo **Tipo**, selezionare il tipo di messaggio (informazioni, avviso, errore) da visualizzare se gli scostamenti dall'intervallo definito si verificano quando si eseguono registrazioni manuali di misura del cespite.
11. Nella Scheda dettaglio **Tipi di cespite**, aggiungere i tipi di cespite che devono poter utilizzare la misura.
12. Nella Scheda dettaglio **Misure dei cespiti correlate**, aggiungere le misure dei cespiti che si desidera vengano aggiornate automaticamente questa misura viene aggiornata.


>[!NOTE]
>Una misura dei cespiti correlata viene aggiornata automaticamente solo se la misura correlata ha il tipo di cespite, a cui è correlata, nell'impostazione di misura dei cespiti. Ad esempio: Si supponga di impostare una misura dei cespiti per "Ore di produzione" e aggiungere il tipo di cespite "Truck Engine". Quando quella misura del cespite viene aggiornata, un contatore correlato "Oil" verrà anche aggiornato con gli stessi valori di misura del cespite. L'impostazione in **Contatori** include l'impostazione in "Ore". Inoltre, nella misura del cespite "Oil", il tipo di cespite "Truck Engine" deve essere aggiunto alla Scheda dettaglio **Tipi di cespite** per garantire la relazione di misura del cespite. Vedere schermate di seguito per un esempio dell'impostazione delle misure Ore e Oil.

Quando i tipi di cespite vengono aggiunti a un tipo di misura dei cespiti in **Contatori**, quella misura viene aggiunta automaticamente ai tipi di cespite nella Scheda dettaglio **Contatori** in [Tipi di cespite](../setup-for-objects/object-types.md).

![Figura 1](media/071-setup-for-objects.png)


