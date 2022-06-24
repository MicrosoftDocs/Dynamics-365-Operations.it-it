---
title: Tipi di unità funzionale
description: In questo articolo viene illustrato come creare tipi di unità funzionale in Gestione cespiti.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01c8276d77f7655659cab13f3c520d7c171e3cfd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879223"
---
# <a name="functional-location-types"></a>Tipi di unità funzionale

[!include [banner](../../includes/banner.md)]

 

In questo articolo viene illustrato come creare tipi di unità funzionale in Gestione cespiti. I tipi di unità funzionali vengono utilizzati per gestire i requisiti per le unità funzionali, incluse le procedure per installare i cespiti in una unità funzionale. È possibile impostare i tipi di cespite, i piani di manutenzione, gli attributi di unità funzionali e i requisiti di attributi cespiti da utilizzare in una unitù funzionale che utilizza il tipo di unità funzionale specifico. Quando si crea una unità funzionale, il tipo di unità funzionale è obbligatorio.

>[!NOTE] 
>Per utilizzare le unità funzionali, è necessario creare una unità funzionale predefinito da utilizzare solo a scopo di creare nuovi cespiti. Per l'unità funzionale predefinito, è necessario creare un tipo di unità funzionale predefinito molto semplice che consente a più cespiti di essere installati sulla unità funzionale predefinita. Per ulteriori informazioni su come impostare le unità funzionali, vedere [Creare unità funzionali](../functional-locations/create-functional-locations.md).

## <a name="create-a-default-functional-location-type"></a>Creare un tipo di unità funzionale predefinito

In questa procedura viene illustrato come creare un tipo di unità funzionale predefinito da utilizzare per una unità funzionale predefinita.

1. Selezionare **Gestione cespiti** > **Impostazione** > **Unità funzionali** > **Tipi di unità funzionali**.
2. Selezionare **Nuovo** per creare un nuovo tipo di unità funzionale.
3. Inserire un IDdel tipo di unità funzionale nel campo **Tipo di unità funzionale**, ad esempio, "Standard" e un nome nel campo **Nome**.
4. Selezionare un modello del ciclo di vita nel campo **Modello del ciclo di vita unità funzionale**.
5. Selezionare "Sì" sull'interruttore **Più cespiti** per consentire a più cespiti siano installati su una unità funzionale (l'unità funzionale predefinita) utilizzando questo tipo.

Ora il tipo di unità funzionale predefinito da utilizzare solo per una unità funzionale predefinita è creato. Non è consigliabile aggiungere altri requisiti o restrizioni a questo tipo di unità funzionale predefinito.


## <a name="create-functional-location-types"></a>Creare tipi di unità funzionali

1. Selezionare **Gestione cespiti** > **Impostazione** > **Unità funzionali** > **Tipi di unità funzionali**.
2. Selezionare **Nuovo** per creare un nuovo tipo di unità funzionale.
3. Inserire un ID del tipo di unità funzionale nel campo **Tipo di unità funzionale** e un nome nel campo **Nome**.
4. Selezionare un modello del ciclo di vita nel campo **Modello del ciclo di vita unità funzionale**. Per ulteriori informazioni sugli stati del ciclo di vita e sui modelli del ciclo di vita delle unità funzionali, vedere [Stati del ciclo di vita delle unità funzionali](../setup-for-functional-locations/functional-location-stages.md).
5. Selezionare "Sì" sull'interruttore **Più cespiti** se deve essere possibile diversi cespiti siano installati su una unità funzionale utilizzando questo tipo di unità funzionale. Se si seleziona "No", è possibile installare *un solo* cespite in una unità funzionale utilizzando questo tipo di unità funzionale.
6. Selezionare "Sì" sull'interruttore **Aggiorna dimensione cespiti** se si desidera che i cespiti installati su una unità funzionale di questo tipo utilizzino automaticamente le dimensioni finanziarie correlate alla unità funzionale. Ciò significa che si modificano le dimensioni nel modulo [Creare unità funzionali](../functional-locations/create-functional-locations.md) e l'unità funzionale usa un tipo con questo interruttore impostato su "Sì", le dimensioni finanziarie viene aggiornata automaticamente in tutti i cespiti installati in quella unità funzionale.
7. Il campo **Tipo di cespite** viene utilizzato se si desidera creare automaticamente *un solo* cespite per l'unità funzionale con lo stesso ID e nome dell'unità funzionale che si sta creando. Ad esempio, questo può essere importante se si crea una unità funzionale statica, ad esempio edifici o una conduttura. In tal caso, selezionare il tipo di cespite si desidera utilizzare per il cespite creato automaticamente. Tenere presente che se si effettua una selezione in questo campo, l'interruttore **Più cespiti** deve essere impostato su "No".
8. Nella Scheda dettaglio **Tipi di cespite**, selezionare i tipi di cespite per essere correlati al tipo di unità funzionale. Fare clic **Aggiungi riga** e selezionare i tipi di cespite. Se si aggiunge i tipi di cespite qui, solo i cespiti che usano quei tipi di cespite possono essere installati in una unità funzionale che usa questo tipo di unità funzionale. Se non si seleziona un tipo di cespite nella Scheda dettaglio **Tipi di cespite**, tutti i tipi di cespite possono essere installati.
9. Nella Scheda dettaglio **Piani di manutenzione**, selezionare i piani di manutenzione che devono essere impostati automaticamente nelle nuove unità funzionali che usano questo tipo di unità funzionale. Fare clic **Aggiungi riga** e selezionare i piani di manutenzione. Se si aggiunge i piani di manutenzione di cespite qui, solo questi piani possono essere usati in una unità funzionale che usa questo tipo di unità funzionale.
10. Nella Scheda dettaglio **Requisiti attributi cespite**, impostare gli attributi cespite che devono essere impostati automaticamente nelle nuove unità funzionali che usano questo tipo di unità funzionale. Fare clic **Aggiungi riga** e selezionare l'attributo. Questi requisiti di attributi fungono da linee guida. Non vengono convalidati in base agli attributi impostati per un cespite (**Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti** > selezionare un cespite nella pagina elenco > scheda **Generale** > pulsante **Attributi** ). I requisiti di attributo vengono visualizzati quando si installano i cespiti nelle unità funzionali.
11. Nella Scheda dettaglio **Tipi consentiti**, selezionare i tipi di unità funzionali che devono essere validi per i tipi di unità funzionali secondari correlati a un tipo di unità funzionale padre, che utilizza il tipo di unità funzionale selezionato.
12. Nella Scheda dettaglio **Attributi**, selezionare gli attributi dell'unità funzionale che devono essere impostati automaticamente nelle nuove unità funzionali che usano questo tipo di unità funzionale. Fare clic **Aggiungi riga** e selezionare l'attributo.


>[!NOTE] 
>Nella Scheda dettaglio **Generale**, è possibile ottenere una panoramica del numero di tipi di cespite, i piani di manutenzione, i requisiti di attributo cespite, tipi consentiti, gli attributi e le unità funzionali impostate per il tipo di unità funzionale. Nel campo **Unità funzionali** viene visualizzato il numero di unità funzionali che utilizzano il tipo di unità funzionale. È possibile utilizzare il pulsante **Copia** per copiare le impostazioni da un tipo di unità funzionale al tipo di unità funzionale selezionato.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]