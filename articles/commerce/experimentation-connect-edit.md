---
title: Collegare un esperimento e modificare varianti
description: In questo argomento viene descritto come connettere un esperimento in un servizio di terze parti a Dynamics 365 Commerce e come modificare varianti per l'esperimento.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 030640ba8907ae52c198ac96ad2c243b533d8c53
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "4413596"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Collegare un esperimento e modificare varianti

In questo argomento viene descritto come collegare un esperimento in Commerce e apportare modifiche alle varianti in modo che siano in linea con l'ipotesi. 

Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in argomenti separati.

[ ![Percorso utente per sperimentazione - Collegamento e modifica](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Dopo che hai [configurato l'esperimento](experimentation-setup.md) in un servizio di terze parti, collegherai l'esperimento in Dynamics 365 Commerce e modificherai le varianti dell'esperimento.

## <a name="planning-considerations"></a>Considerazioni sulla pianificazione

Prima di collegare l'esperimento in Commerce, dovrai prendere alcune decisioni che influiscono sul modo in cui Commerce gestisce i contenuti.

### <a name="determine-the-scope-of-your-experiment"></a>Determinare l'ambito dell'esperimento
Quando colleghi un esperimento, ti viene chiesto di definire l'ambito dell'esperimento. Gli esperimenti sono definiti come ambito **parziale** o ambito **intero**.
- Scegli **parziale** se desideri condurre un esperimento su una parte specifica di una pagina. Se selezioni questa opzione, devi identificare i moduli inclusi nell'esperimento. Le modifiche apportate a parti della pagina o del frammento predefinito non correlate all'esperimento vengono sincronizzate automaticamente tra le varianti.
- Scegli **intero** se desideri condurre un esperimento su un'intera pagina o un frammento. Vengono create copie distinte della pagina o del frammento predefinito. Non sarà necessario selezionare quali moduli sono inclusi nell'esperimento perché l'intera superficie di modifica è disponibile per la modifica. È possibile aggiungere, eliminare o riordinare i moduli come necessario. Tuttavia, se vengono apportate modifiche alla pagina o al frammento predefinito a cui è associato l'esperimento, tali modifiche devono essere sincronizzate manualmente in tutte le varianti.

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> Se associ l'esperimento a una pagina che utilizza un layout, puoi definire l'ambito dell'esperimento solo come **intero**.

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a>Decidere se pianificare quando l'esperimento deve essere pubblicato
Se desideri pianificare quando l'esperimento deve essere pubblicato sul tuo sito live, assicurati che il contenuto che desideri associare all'esperimento sia disponibile in un gruppo di pubblicazione *prima* di collegare l'esperimento. 

Per ulteriori informazioni sui gruppi di pubblicazione, fai riferimento a [Utilizzare i gruppi di pubblicazione](publish-groups.md).


## <a name="connect-your-experiment"></a>Collegare l'esperimento
Per collegare l'esperimento, avvierai la procedura guidata **Collega l'esperimento**. Questa procedura guidata ti guida attraverso i passaggi necessari per collegare l'esperimento. Al termine della procedura guidata, l'esperimento risulta collegato, le varianti sono state create e sono pronte per essere modificate.

Per iniziare la connessione dell'esperimento in Creazione di siti Web di Commerce seguire questi passaggi.

1. Per avviare la procedura guidata **Connetti esperimento**, selezionare **Esperimenti** nel riquadro di spostamento a sinistra, quindi selezionare **Connetti**. In alternativa, è possibile accedere alla procedura guidata da una pagina o da un editor di frammenti modificandolo e selezionando **Connetti esperimento** sulla barra dei comandi.

    > [!NOTE]
    > Una pagina può essere collegata solo a un esperimento alla volta. Per collegare una pagina a un altro esperimento, elimina prima l'esperimento a cui la pagina è attualmente collegata.

1. Scegli la pagina o il frammento su cui desideri eseguire l'esperimento.
1. Imposta l'ambito della sperimentazione su **parziale** o **intero**, in base alla scelta che hai fatto nella sezione [Determinare l'ambito dell'esperimento](#determine-the-scope-of-your-experiment) vista sopra.
    > [!NOTE]
    > Il flag della funzionalità **Sperimenta su pagine o frammenti** deve essere abilitato se desideri sperimentare su una pagina o su un frammento intero. Per ulteriori informazioni, fai riferimento all'argomento [Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md):
    
1. Nel passaggio finale della procedura guidata, seleziona **Genera varianti e chiudi la procedura guidata**. Le varianti vengono create per l'esperimento. 

## <a name="edit-your-variations"></a>Modificare le varianti
Quando chiudi la procedura guidata, vengono create le varianti. 

Successivamente, modificherai le varianti in modo che riflettano le scelte che devi verificare nell'ipotesi dell'esperimento. Scegli una delle seguenti procedure che corrisponde all'ambito scelto per l'esperimento nella sezione [Determinare l'ambito dell'esperimento](#determine-the-scope-of-your-experiment) vista sopra.

### <a name="edit-variations-for-experiments-with-partial-scope"></a>Modificare le varianti per esperimenti con ambito parziale
Segui questi passaggi se hai definito l'ambito dell'esperimento come **parziale** nella procedura guidata **Collega l'esperimento**.

1. Nella visualizzazione dell'editor, utilizza il menu a discesa delle varianti sotto la barra dei comandi per modificare ogni variante in base all'ipotesi originale. Puoi anche stabilire una variante di base o controllo lasciando invariata una delle varianti.
1. Seleziona il modulo su cui sperimentare, seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi all'esperimento**.

### <a name="edit-variations-for-experiments-with-entire-scope"></a>Modificare varianti per esperimenti con ambito intero
Se hai definito l'ambito dell'esperimento come **intero** nella procedura guidata **Collega l'esperimento**, nella visualizzazione dell'editor utilizza il menu a discesa delle varianti sotto la barra dei comandi per modificare ogni variante in base all'ipotesi originale. 

> [!NOTE]
> In entrambi i casi, puoi anche stabilire una variante di base o controllo lasciando invariata una delle varianti.

## <a name="previous-step"></a>Passaggio precedente
[Configurare un esperimento](experimentation-setup.md) 


## <a name="next-step"></a>Passaggio successivo
[Visualizzare un esperimento in anteprima e pubblicarlo](experimentation-preview-publish.md)
