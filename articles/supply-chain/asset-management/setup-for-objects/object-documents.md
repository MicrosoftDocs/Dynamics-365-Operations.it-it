---
title: Documenti cespiti
description: In questo argomento vengono descritti i documenti di cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectDocument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f8bcae99a96ccd83dc4543b1c56007a4263a19b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021681"
---
# <a name="asset-documents"></a>Documenti cespiti

[!include [banner](../../includes/banner.md)]

 

In questo argomento vengono descritti i documenti di cespiti in Gestione cespiti.

In Gestione cespiti, è possibile impostare documenti in modo da correlarli automaticamente ai tipi di processo, ai produttori cespite, tipi del cespite, o ai cespiti, ad esempio. Questa funzionalità è utile quando versioni aggiornate dei documenti vengono rilasciate. In questo caso, è sufficiente mettere il documento aggiornato nell'ubicazione standard utilizzata per i documenti Supply Chain Management e collegare il documento al record documenti cespiti creato. Il documento aggiornato potrà quindi essere accessibile tramite **Tutti i cespiti**, **Cespiti attivi**, **Cespiti attivi personali**, **Tutti gli ordini di lavoro** e **Processi ordini di lavoro attivi**. Il processo per collegare documenti a un record documenti cespiti utilizza il sistema di gestione documenti standard.

**Esempio 1:** un documento correlato a un tipo di processo può descrivere una procedura per questo tipo di processo.

**Esempio 2:** un documento correlato a una combinazione di tipo cespite, produttore e modello potrebbe essere il manuale predefinito per il modello del produttore del cespite selezionato.

## <a name="create-asset-document-relation"></a>Creare la relazione dei documenti cespiti

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Documenti cespiti**.
2. Selezionare **Nuovo** per creare un record documenti cespiti.
3. A seconda del livello di specificità desiderato per la relazione del documento, selezionare opzioni appropriate in uno o più dei campi seguenti: **Tipo di cespite**, **Produttore**, **Modello**, **Cespite**, **Categoria tipo di processo**, **Tipo di processo**, **Variante tipo di processo** e **Fabbisogno processo**. Le opzioni disponibili nei campi **Fabbisogno processo** e **Variante tipo di processo** dipendono dalla selezione effettuata nel campo **Tipo di processo**.

    > [!NOTE]
    > Quando il sistema cerca i documenti che devono essere correlati a un cespite o un ordine di lavoro, Gestione cespiti analizza tutti i record documenti cespiti per verificare la presenza di una corrispondenza possibile. Controlla sempre la combinazione più specifica per prima. In altre parole, Gestione cespiti controlla prima **Fabbisogno processo** per trovare una corrispondenza. Se non trova corrispondenza, controlla **Variante tipo di processo**. Se non trova corrispondenza, controlla **Tipo di processo** e così via. Come si vede nel layout della pagina **Documenti cespiti**, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per una corrispondenza. È possibile che più documenti possono essere collegati a un cespite o un ordine di lavoro. È possibile modificare il livello di servizio in una richiesta di intervento di manutenzione o un ordine di lavoro in base alle esigenze.

4. Selezionare **Allegati**. Verrà visualizzata la pagina **Gestione documenti** standard.
5. Impostare i documenti o note che dovranno essere collegati al record documenti cespiti. Dopo aver collegato i documenti, il campo **Allegati** mostra il numero di documenti correlati al record.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]