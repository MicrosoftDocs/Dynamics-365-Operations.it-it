---
title: Flusso di lavoro fornitori
description: Modificare le informazioni sul fornitore e utilizzare il flusso di lavoro per approvarle.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: fb89b54b2f9377c216c447590a9434e3ff2d9bac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248137"
---
# <a name="vendor-workflow"></a>Flusso di lavoro fornitori

[!include [banner](../includes/banner.md)]

Quando viene utilizzato il flusso di lavoro fornitori, le modifiche apportate a campi specifici vengono inviate al flusso di lavoro per l'approvazione prima che vengano aggiunte al fornitore.

## <a name="set-up-the-vendor-workflow"></a>Impostare il flusso di lavoro fornitori

Prima di poter utilizzare la funzionalità del flusso di lavoro, è necessario abilitarla.

1. Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
2. Nella scheda **Generale**, nella Scheda dettaglio **Approvazione fornitore**, impostare l'opzione **Abilita approvazioni fornitore** su **Sì**.
3. Nel campo **Comportamento entità di dati** selezionare il comportamento da utilizzare quando vengono importati i dati:

    - **Consenti modifiche senza approvazione** - L'entità di dati può aggiornare il record fornitore senza elaborarlo attraverso il flusso di lavoro.
    - **Rifiuta modifiche** - Non è possibile apportare modifiche al record fornitore. L'importazione non avrà esito positivo per i campi che sono abilitati per il flusso di lavoro.
    - **Crea proposte di modifica** - Tutti i campi verranno modificati eccetto i campi che sono abilitati per il flusso di lavoro. I nuovi valori per questi campi verranno aggiunti al fornitore come modifiche proposte e il flusso di lavoro verrà avviato automaticamente.

4. Nell'elenco di campi del fornitore, selezionare la casella di controllo **Abilita** per ogni campo che deve essere approvato prima che si possano apportare modifiche.
5. Passare a **Contabilità fornitori \> Impostazioni \> Flussi di lavoro contabilità fornitori**.
6. Selezionare **Nuovo**.
7. Selezionare **Flusso di lavoro modifiche fornitore proposte**. 
8. Impostare il flusso di lavoro in modo che corrisponda al processo di approvazione. L'elemento di approvazione del flusso di lavoro **Approvazione del flusso di lavoro per la modifica fornitore proposta** applicherà le modifiche al fornitore.

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>Modificare le informazioni sul fornitore e inviare le modifiche al flusso di lavoro

Quando si modifica un campo abilitato per il flusso di lavoro, viene visualizzata la pagina **Modifiche proposte**. In questa pagina vengono visualizzati il valore originale del campo e il nuovo valore immesso. Il campo che è stato modificato viene ripristinato al valore originale. Un messaggio di stato informa anche che le modifiche non sono state inviate. 

Ogni volta che si modifica un campo che è abilitato per il flusso di lavoro, questo campo viene aggiunto all'elenco nella pagina **Modifiche proposte**. Per eliminare il valore proposto per un campo, utilizzare il pulsante **Elimina** accanto al campo nell'elenco. Per eliminare tutte le modifiche, utilizzare il pulsante **Ignora tutte le modifiche** nella parte inferiore della pagina. Selezionare **OK** per chiudere la pagina.

Quando si ha almeno una modifica proposta, vengono visualizzate due schede aggiuntive nel riquadro azioni: **Modifiche proposte** e **Flusso di lavoro**.

1. Selezionare **Modifiche proposte** per aprire la pagina **Modifiche proposte** ed esaminare le modifiche.
2. Selezionare **Flusso di lavoro \> Invia per inviare le modifiche al flusso di lavoro**.

    Lo stato sulla pagina è cambiato in **Modifiche in attesa di approvazione**.

Il flusso di lavoro segue il processo standard del flusso di lavoro. L'approvatore viene reindirizzato alla pagina **Fornitore**, in cui le modifiche possono essere riviste nella pagina **Modifiche proposte** e selezionare **Flusso di lavoro \> Approva** per approvare il flusso di lavoro. Una volta completate tutte le approvazioni, i campi vengono aggiornati con i valori proposti.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]