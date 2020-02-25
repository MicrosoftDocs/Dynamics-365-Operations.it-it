---
title: Tipo di destinazione posta elettronica ER
description: In questo argomento vengono fornite informazioni su come configurare una destinazione posta elettronica per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019846"
---
# <a name="EmailDestinationType">Destinazione posta elettronica</a>

[!include [banner](../includes/banner.md)]

È possibile configurare una destinazione posta elettronica per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita. In base all'impostazione di destinazione, un documento generato viene fornito come allegato di un messaggio di posta elettronica.

Impostare **Abilitato** su **Sì** per inviare un file di output tramite posta elettronica. Dopo aver abilitato questa opzione, è possibile specificare i destinatari del messaggio di posta elettronica e modificare l'oggetto e il corpo del messaggio. È possibile impostare testi costanti per l'oggetto e il corpo del messaggio di posta elettronica oppure utilizzare le [formule](er-formula-language.md) ER per creare in modo dinamico i testi del messaggio di posta elettronica. 

È possibile configurare gli indirizzi di posta elettronica per ER in due modi. La configurazione può essere completata come avviene con la funzionalità Gestione stampa oppure è possibile risolvere un indirizzo di posta elettronica utilizzando un riferimento diretto alla configurazione ER mediante una formula.

[![Abilitare la destinazione posta elettronica](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>Tipi di indirizzo di posta elettronica

Quando si seleziona **Modifica** nel campo **A** o **Cc**, viene visualizzata la finestra di dialogo **Destinatario messaggio di posta elettronica**. È quindi possibile selezionare il tipo di indirizzo di posta elettronica da utilizzare. I tipi di posta elettronica **Posta elettronica configurazione** e **Gestione stampa** sono attualmente supportati.

[![Selezionare il tipo di posta elettronica](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management"></a>Gestione stampa

Se si seleziona il tipo di posta elettronica **Gestione stampa**, è possibile immettere indirizzi di posta elettronica fissi nel campo **A**. 

[![Configurare indirizzi di posta elettronica fissi](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)

Per utilizzare indirizzi di posta elettronica non fissi, è necessario selezionare il tipo di origine di posta elettronica per una destinazione file. I valori seguenti sono supportati: **Cliente**, **Fornitore**, **Prospect**, **Contatto**, **Concorrente**, **Lavoratore**, **Candidato**, **Fornitore potenziale** e **Fornitore non autorizzato**. Dopo avere selezionato un tipo di origine di posta elettronica, utilizzare il pulsante accanto al campo **Conto di origine posta elettronica** per aprire il modulo **Designer formula**. È possibile utilizzare questo modulo per allegare una formula che restituisce in fase di esecuzione il '**conto parte** del tipo di origine selezionato nel documento elaborato per la destinazione posta elettronica.

[![Configurare un conto di origine di posta elettronica](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)

Le formule sono specifiche alla configurazione ER. Nel campo **Formula** immettere un riferimento specifico per il documento a un tipo di parte del cliente o del fornitore. Anziché digitare, è possibile cercare il nodo di origine dati che rappresenti il conto cliente o fornitore e selezionare **Aggiungi origine dati** per aggiornare la formula. Ad esempio, se si utilizza la configurazione **bonifico ISO 20022**, il nodo che rappresenta un conto fornitore è `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`

Se si immette un valore stringa, ad esempio `"DE-001"` e si salva una formula, verrà inviato un messaggio e-mail alla persona di contatto del fornitore, ovvero **DE-001**.


[![Pagina Designer formula ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)

[![Configurare conto di origine posta elettronica](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)



### <a name="configuration-email"></a>Posta elettronica configurazione

Utilizzare questo tipo di messaggio di posta elettronica se la configurazione utilizzata include un nodo nelle origini dati che restituisce un **indirizzo di posta elettronica**. È possibile utilizzare le origini dati e le funzioni in Designer formula per ottenere un indirizzo di posta elettronica formattato correttamente. Ad esempio, se si utilizza la configurazione **bonifico ISO 20022**, il nodo che rappresenta un indirizzo di posta elettronica di una persona di contatto di un fornitore è `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurare l'origine di un indirizzo di posta elettronica](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
- [Designer formula nella creazione di report elettronici (ER)](general-electronic-reporting-formula-designer.md)
