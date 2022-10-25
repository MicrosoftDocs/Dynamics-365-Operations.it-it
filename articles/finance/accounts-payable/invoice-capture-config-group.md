---
title: Gruppi di configurazione della soluzione Invoice Capture
description: In questo articolo vengono fornite informazioni generali sui gruppi di configurazione nella soluzione Invoice Capture.
author: sunfzam
ms.date: 09/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cfe5ae35b4f87a350d944b30a49251081766ad27
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691215"
---
# <a name="invoice-capture-solution-configuration-groups"></a>Gruppi di configurazione della soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Gli utenti possono gestire l'elenco dei campi fattura e l'impostazione di revisione manuale per le persone giuridiche utilizzando i gruppi di configurazione. Gli utenti possono impostare configurazioni di fattura per diverse persone giuridiche in gruppi. Tutte le persone giuridiche nello stesso gruppo di configurazione utilizzano gli stessi campi fattura e le stesse impostazioni di revisione manuale.

## <a name="manage-configuration-groups"></a>Gestisci gruppi di configurazioni

Per gestire i gruppi di configurazione tramite l'app, vai a **Impostazione**, quindi seleziona **Impostazioni sistema \> Definisci componente gruppi di configurazione**.

Nella pagina **Definisci gruppi di configurazione**, la scheda principale mostra l'elenco dei gruppi di configurazione che sono stati definiti. Mostra anche un gruppo di configurazione predefinito. Per ogni gruppo di configurazione, sono disponibili le azioni seguenti:

- **Copia un gruppo di configurazione** – È possibile creare un nuovo gruppo di configurazione duplicando un gruppo esistente. Il nuovo gruppo ha gli stessi valori del gruppo originale per tutti i campi tranne **Nome gruppo** e **Descrizione gruppo**. Dopo che il gruppo di configurazione è stato duplicato, seleziona **OK**.
- **Elimina gruppi di configurazione** – Per eliminare un gruppo di configurazione, selezionalo, quindi seleziona **Elimina**.

    > [!NOTE]
    > Il gruppo di configurazione non può essere eliminato.

- **Modifica l'ID di un gruppo di configurazione** – Per modificare l'ID di un gruppo di configurazione, seleziona il campo **ID gruppo** e aggiorna il valore. L'ID gruppo non deve contenere spazi o caratteri speciali e non deve superare i 20 caratteri.

    > [!NOTE]
    > Il valore del campo **ID gruppo** può essere aggiornato una sola volta.

- **Modifica la descrizione di un gruppo di configurazione** – Per modificare la descrizione di un gruppo di configurazione, seleziona il campo **Descrizione** e aggiorna il valore.
- **Modifica l'impostazione della revisione manuale** – Gli utenti possono decidere se una fattura deve essere rivista manualmente. Per modificare l'impostazione della revisione manuale, seleziona l'opzione **Necessita di revisione manuale**. Di seguito vengono illustrate le opzioni disponibili.

    - **Sempre revisione manuale** – Seleziona questa opzione se le fatture nel gruppo di configurazione richiedono sempre la revisione manuale.
    - **Per errori e avvisi** – Seleziona questa opzione se le fatture che contengono messaggi di errore o di avviso richiedono una revisione manuale.
    - **Per errori** – Seleziona questa opzione se le fatture che contengono messaggi di errore richiedono una revisione manuale.

- **Modifica l'impostazione del punteggio di attendibilità** – Il punteggio di attendibilità è costituito dai metadati forniti dalla soluzione Invoice Capture per segnalare l'accuratezza dei dati delle fatture riconosciute. Più alto è il punteggio, più accurati potrebbero essere i dati riconosciuti. La configurazione consente agli utenti di definire quando è necessaria la revisione manuale, in base al punteggio di attendibilità. Gli utenti possono modificare la soglia del punteggio di attendibilità per le fatture. Per aggiornare l'impostazione del punteggio di attendibilità, seleziona il campo **Punteggio di attendibilità** e aggiorna il valore.

    Esistono due tipi di avviso per i punteggi di attendibilità:

    - **Avviso** – I campi fattura con punteggi di attendibilità superiori alla soglia di avviso sono considerati corretti. La soglia di avviso deve essere superiore alla soglia di errore e inferiore a 100.
    - **Errore** – I campi fattura con punteggi di attendibilità inferiori alla soglia di errore sono considerati errati. I messaggi di errore verranno mostrati all'utente. La soglia di errore deve essere superiore a 0 (zero) e inferiore alla soglia di avviso. Verranno visualizzati messaggi di avviso per i campi fattura con punteggi di attendibilità compresi tra la soglia di avviso e la soglia di errore.

- **Gestisci i campi della fattura** – Gli utenti possono gestire l'elenco dei campi fattura che viene mostrato nel visualizzatore affiancato. Nella scheda **Gestione campo fattura**, seleziona il simbolo dell'ingranaggio, seleziona i campi della fattura da aggiungere, quindi seleziona **Salva**. I campi selezionati verranno aggiunti all'elenco. Per rimuovere un campo fattura dall'elenco, seleziona **Rimuovi** sul campo.

### <a name="manage-file-filters-optional"></a>Gestisci filtri file (facoltativo)

Gestisci filtri file consente agli utenti di definire filtri aggiuntivi per i file delle fatture in entrata. I file che non soddisfano i criteri di filtro verranno ricevuti e appariranno nell'elenco **File ricevuti**, ma mostreranno errori di convalida del file. Questo comportamento è diverso dal comportamento per i filtri definiti nel canale. Per quei filtri, i file che non soddisfano i criteri non verranno ricevuti affatto. Gli utenti possono esaminare i file in entrata e decidere se ogni file è una fattura non valida e possono rendere obsoleto il file o includerlo manualmente per il riconoscimento e l'inclusione nelle fatture acquisite.

Quando viene installata la soluzione Invoice Capture, viene definito un filtro file predefinito. Questo filtro di file è globale. Se desideri impostazioni di filtro diverse, puoi aggiornare il filtro predefinito. Se un campo è obbligatorio, seleziona **Obbligatorio**. 

### <a name="accepted-file-size"></a>Dimensioni file accettate

Puoi scegliere la dimensione del file accettata.

> [!NOTE]
> I file di dimensioni superiori a 20.480 kilobyte (KB) non sono supportati.

### <a name="supported-file-types"></a>Tipi di file supportati

Attualmente sono supportati i seguenti tipi di file:

- PDF
- PNG
- JPG
- JPEG
- TIF
- TIFF
