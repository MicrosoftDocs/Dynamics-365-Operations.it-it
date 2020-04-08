---
title: Elaborazione delle ricevute spese
description: Questo argomento fornisce informazioni sull'elaborazione OCR (riconoscimento ottico dei caratteri) per le ricevute. Questa funzionalità è progettata per migliorare l'esperienza utente quando vengono create note spese in Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 49cdfeac8cda9f1ddd3aca61f902f00f30f3485b
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154042"
---
# <a name="expense-receipt-processing"></a>Elaborazione ricevuta spese

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


L'inserimento delle spese è stata migliorato con l'introduzione dell'elaborazione OCR (riconoscimento ottico dei caratteri) per le ricevute. Questa funzionalità è progettata per migliorare l'esperienza utente quando vengono create note spese.

## <a name="key-features"></a>Funzionalità principali

- Il nome del commerciante, la data e l'importo totale vengono estratti dalle ricevute.
- La funzione tenta di associare le ricevute non collegate alle transazioni di spesa non collegate.
- Gli utenti possono creare transazioni di spesa inserite manualmente dalle ricevute.

## <a name="usage-examples"></a>Esempi di utilizzo

- **Collegare automaticamente le ricevute che includono transazioni con carta di credito quando viene creata una nota spese.**

    1. Aprire l'area di lavoro **Gestione spese**.
    2. Nella scheda **Ricevute**, verificare l'esistenza di ricevute non collegate. È anche possibile caricare ricevute nella scheda **Ricevute**.
    3. Nella scheda **Spese**, verificare l'esistenza di spese non collegate. In genere, l'amministratore spese importa queste spese dal fornitore della carta di credito.
    4. Selezionare **Nuova nota spese**. Si noti che ora è possibile includere spese e ricevute quando si crea una nota spese. Se si aggiungono le spese e ricevute, viene attivata l'associazione automatica delle ricevute con le spese.

- **Creare una spesa o associare una spesa di una ricevuta.**

    1. In una nota spese, nella scheda **Ricevute**, collegare una ricevuta selezionando **Aggiungi ricevute**.
    2. Sotto l'immagine della ricevuta caricata, notare le opzioni **Crea** e **Associa**.

        - Selezionare **Crea** per creare una transazione di spesa immessa manualmente e immettere i valori estratti dalla ricevuta.
        - Se si seleziona **Associa**, il sistema tenta di associare una spesa esistente alla ricevuta.

## <a name="installation"></a>Installazione

Questa funzionalità viene utilizzata con la funzionalità **Note spese rinnovate** per semplificare l'esperienza di spesa.

Per utilizzare queste funzionalità di spesa avanzate, installare il componente aggiuntivo Servizio gestione spese per Microsoft Dynamics 365 Finance e attivare le funzionalità nella propria istanza. È possibile accedere al componente aggiuntivo dal progetto in Microsoft Dynamics Lifecycle Services (LCS).

1. Accedere a LCS e aprire l'ambiente desiderato.
2. Andare a **Dettagli completi**.
3. Selezionare **Gestisci** oppure scorrere verso il basso la scheda dettaglio **Componenti aggiuntivi dell'ambiente**.
4. Selezionare **Installare un nuovo componente aggiuntivo**.
5. Selezionare **Servizio gestione spese**.
6. Seguire la guida all'installazione e accettare le condizioni.
7. Selezionare **Installa**.

Nell'area di lavoro **Gestione funzionalità**, attivare le seguenti funzionalità:

- Note spese rinnovate
- Esegui la corrispondenza automatica e crea le spese dalla ricevuta

Quando vengono attivate questa funzionalità, si verificano le seguenti azioni:

- L'area di lavoro **Gestione spese** esistente viene sostituita con la nuova area di lavoro.
- Viene aggiunta una nuova voce di menu per la visibilità del campo delle spese.
- È sempre possibile aprire la pagina **Note spese** precedente selezionando **Gestione spese > Spese personali > Note spese**.
- I flussi di lavoro e le eventuali approvazioni portano ancora alla pagina delle note spese esistente.
- Le ricevute verranno elaborate tramite Microsoft Azure Cognitive Services e i metadati verranno estratti e aggiunti.
- Viene aggiunta un'opzione che consente di creare una nota spese che include le ricevute non collegate associate.
- Un'opzione che viene aggiunta alle note spese consente di creare una riga spese da una ricevuta o tenta di associare una ricevuta esistente a una riga spese esistente.

Per ulteriori informazioni sulla funzionalità Note spese rinnovate, vedere [Note spese rinnovate](ExpenseWorkspaceNew.md).

## <a name="frequently-asked-questions"></a>Domande frequenti

**Microsoft utilizza i dati personali per i propri modelli?**

No, Microsoft ha creato un modello generale di machine learning per il proprio servizio di elaborazione delle ricevute. Questo modello non si basa sulle ricevute caricate.

**Dove è disponibile e viene elaborata questa funzione?**

Attualmente negli Stati Uniti.

**Dove vanno a finire le ricevute?**

Finance contatterà i servizi cognitivi per estrarre i dati del campo. I servizi cognitivi conserveranno una copia della ricevuta per un massimo di 24 ore durante l'elaborazione. Al termine dell'elaborazione, i servizi cognitivi rimuoveranno la ricevuta. Le ricevute sono ancora archiviate in Finance.

Per ulteriori informazioni, vedere [Abilitare la comprensione delle ricevute con la nuova funzionalità di Form Recognizer](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).
