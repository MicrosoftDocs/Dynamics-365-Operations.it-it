---
title: Flusso di lavoro cliente
description: In questo argomento vengono fornite informazioni sul flusso di lavoro del cliente. È possibile modificare campi specifici per un cliente e inviare tali modifiche per l'approvazione utilizzando il flusso di lavoro prima che vengano aggiunte al cliente.
author: abruer
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: c74f18997b390d70b5012199fab1adc9734994f4
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753828"
---
# <a name="customer-workflow"></a>Flusso di lavoro cliente

[!include [banner](../includes/banner.md)]

Il flusso di lavoro cliente è stato aggiunto alla versione 8.0.4. È possibile modificare campi specifici per un cliente e inviare tali modifiche per l'approvazione utilizzando il flusso di lavoro prima che vengano aggiunte al cliente.

## <a name="set-up-the-customer-workflow"></a>Impostare il flusso di lavoro cliente

Prima di utilizzare la funzionalità del flusso di lavoro del cliente, è necessario abilitarla.

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
2. Nella scheda **Generale**, nella Scheda dettaglio **Approvazione cliente**, impostare l'opzione **Abilita approvazioni cliente** su **Sì** per abilitare la funzionalità.
3. Nel campo **Comportamento entità di dati** selezionare il comportamento che le entità di dati devono utilizzare quando i dati vengono importati:

    - **Consentire modifiche senza approvazione** - Un'entità può aggiornare il record cliente senza elaborarlo durante il flusso di lavoro.
    - **Rifiuta modifiche** - Le modifiche non possono essere applicate al record cliente. L'importazione avrà esito negativo per i campi abilitati per il flusso di lavoro.
    - **Crea proposte di modifica** - Tutti i campi verranno modificati ad eccezione dei campi abilitati per il flusso di lavoro. I nuovi valori per questi campi verranno aggiunti al cliente come modifiche proposte e il flusso di lavoro verrà avviato automaticamente.

4. Nell'elenco dei campi del cliente, selezionare quindi la casella di controllo **Abilita** per ogni campo che deve essere approvato prima che le modifiche possano essere effettuate.
5. Andare a **Contabilità clienti \> Impostazioni \> Flussi di lavoro contabilità clienti**.
6. Selezionare **Nuovo**.
7. Selezionare **Flusso di lavoro della modifica del cliente proposta**. 
8. Impostare il flusso di lavoro in modo che corrisponda al processo di approvazione. L'elemento di approvazione del flusso di lavoro **Approvazione del flusso di lavoro per la modifica cliente proposta** applicherà le modifiche al cliente.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Modificare le informazioni sul cliente e inviare le modifiche al flusso di lavoro

Quando si modifica un campo che viene abilitato per il flusso di lavoro, viene visualizzata la pagina **Modifiche proposte**. In questa pagina vengono visualizzati il valore originale del campo e il nuovo valore immesso. Il campo modificato viene reimpostato sul valore originale. Un messaggio di stato nella pagina comunica all'utente che le modifiche non sono state inviate.

Ogni volta che si modifica un campo abilitato per il flusso di lavoro, tale campo viene aggiunto all'elenco delle modifiche proposte. Per eliminare il valore proposto per un campo, utilizzare il pulsante **Elimina** accanto al campo nell'elenco. Per eliminare tutte le modifiche, utilizzare il pulsante **Ignora tutte le modifiche** in fondo alla pagina. Selezionare **OK** per chiudere la pagina.

Dopo avere almeno una modifica proposta, vengono visualizzati due menu aggiuntivi nel riquadro Azioni: **Modifiche proposte** e **Flusso di lavoro**.

1. Selezionare **Modifiche proposte** per aprire la pagina **Modifiche proposte** ed esaminare le modifiche.
2. Selezionare **Flusso di lavoro \> Invia** per inviare le modifiche al flusso di lavoro.

    Lo stato sulla pagina è passato a **Modifiche in attesa di approvazione**.

Il flusso di lavoro segue il processo standard del flusso di lavoro nell'applicazione. L'approvatore viene reindirizzato alla pagina **Cliente**, in cui le modifiche possono essere riviste nella pagina **Modifiche proposte** e selezionare **Flusso di lavoro \> Approva** per approvare il flusso di lavoro. Una volta completate tutte le approvazioni, i campi vengono aggiornati con i valori proposti.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
