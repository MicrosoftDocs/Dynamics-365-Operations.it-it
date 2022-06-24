---
title: Collegare un esperimento e modificare varianti
description: In questo articolo viene descritto come connettere un esperimento in un servizio di terze parti a Dynamics 365 Commerce e come modificare varianti per l'esperimento.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: dcdbd61976402ddd719ece184a86692fbc7c628d
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942824"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Collegare un esperimento e modificare varianti

In questo articolo viene descritto come collegare un esperimento in Commerce e apportare modifiche alle varianti in modo che siano in linea con l'ipotesi. 

Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in articoli separati.

[ ![Percorso utente sperimentazione - Connessione e modifica.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Dopo che hai [configurato l'esperimento](experimentation-setup.md) in un servizio di terze parti, collegherai l'esperimento in Dynamics 365 Commerce e modificherai le varianti dell'esperimento.

## <a name="connect-your-experiment"></a>Collegare l'esperimento
Per collegare l'esperimento, avvierai la procedura guidata **Collega l'esperimento**. Questa procedura guidata ti guida attraverso i passaggi necessari per collegare l'esperimento. Al termine della procedura guidata, l'esperimento risulta collegato, le varianti sono state create e sono pronte per essere modificate.

Per iniziare la connessione dell'esperimento in Creazione di siti Web di Commerce seguire questi passaggi.

1. Per avviare la procedura guidata **Connetti esperimento**, selezionare **Esperimenti** nel riquadro di spostamento a sinistra, quindi selezionare **Connetti**. In alternativa, è possibile accedere alla procedura guidata da una pagina o da un editor di frammenti modificandolo e selezionando **Connetti esperimento** sulla barra dei comandi.

    > [!NOTE]
    > - Una pagina può essere collegata solo a un esperimento alla volta. Per collegare una pagina a un altro esperimento, elimina prima l'esperimento a cui la pagina è attualmente collegata.
    > - Puoi sperimentare solo su pagine con un layout personalizzato. Se la tua pagina ha un layout preimpostato, convertila prima in un layout personalizzato. Puoi farlo andando alla pagina e selezionando **Converti in layout personalizzato** sulla barra dei comandi. Per ulteriori informazioni sui layout, vedi [Layout preimpostati e personalizzati](templates-layouts-overview.md#preset-and-custom-layouts). 

1. Se ti stai connettendo a un esperimento dalla scheda **Esperimenti** nel riquadro di navigazione a sinistra, seleziona il nome dell'esperimento dall'elenco visualizzato.
1. Seleziona la pagina o il frammento su cui desideri eseguire l'esperimento.
1. Nel passaggio finale della procedura guidata, seleziona **Genera varianti e chiudi la procedura guidata**. Le varianti vengono create per l'esperimento. 

> [!NOTE]
> Se desideri pianificare quando l'esperimento deve essere pubblicato sul tuo sito live, assicurati che il contenuto che desideri associare all'esperimento sia disponibile in un gruppo di pubblicazione *prima* di collegare l'esperimento. Per ulteriori informazioni sui gruppi di pubblicazione, fai riferimento a [Utilizzare i gruppi di pubblicazione](publish-groups.md).

## <a name="edit-your-variations"></a>Modificare le varianti

Quando esci dalla procedura guidata **Collega esperimento**, le varianti sono create automaticamente. Segui i passaggi seguenti per modificare le varianti in modo che riflettano le scelte che devi verificare nell'ipotesi dell'esperimento.

1. Nella visualizzazione dell'editor, utilizza il menu a discesa delle varianti sotto la barra dei comandi per modificare ogni variante in base all'ipotesi originale. Puoi anche stabilire una variante di base o controllo lasciando invariata una delle varianti.
1. Seleziona il modulo su cui sperimentare, seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi all'esperimento**.

> [!NOTE]
> Puoi stabilire una variante di base o controllo lasciando invariata una delle varianti.

## <a name="previous-step"></a>Passaggio precedente
[Configurare un esperimento](experimentation-setup.md) 


## <a name="next-step"></a>Passaggio successivo
[Visualizzare un esperimento in anteprima e pubblicarlo](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
