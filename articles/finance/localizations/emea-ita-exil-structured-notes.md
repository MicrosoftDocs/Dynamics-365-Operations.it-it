---
title: Gestione note avanzate
description: Questo argomento spiega come impostare e stampare note predefinite per clienti, fornitori e prodotti.
author: ilkond
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9c52bb2ee553f0b15f1f41e68eeae7a4aea65205
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428933"
---
# <a name="advanced-notes-management"></a>Gestione note avanzate

[!include [banner](../includes/banner.md)]

La funzione di gestione avanzata delle note ti consente di impostare note predefinite che si applicano a tutti o a specifici clienti, fornitori e prodotti. È quindi possibile aggiungere queste note a documenti aziendali specifici.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare la configurazione, è necessario soddisfare i seguenti prerequisiti:

- La funzionalità **Gestione avanzata delle note** deve essere attivata nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="advanced-notes-setup"></a>Impostazioni note libere

Se è necessario stampare note simili su documenti per gruppi di clienti, è possibile definire nuovi gruppi appositamente per le note avanzate. 

### <a name="define-group-codes-and-descriptions"></a>Definire codici e descrizioni di gruppi

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Note avanzate** \> **Gruppi note avanzate clienti**.

![Configurazione di gruppi di note avanzate dei clienti](media/emea-ita-exil-notes-groups.jpg)

2. Dopo aver creato i gruppi, andare a **Contabilità clienti**\>**Clienti**\>**Tutti i clienti**. 
3. Nella Scheda dettaglio **Impostazioni predefinite ordine cliente**, nella sezione **Note avanzate** assegnare i riferimenti per i clienti richiesti ai nuovi gruppi.

![Assegnazione del gruppo clienti](media/emea-ita-exil-notes-cust-groups.jpg)

### <a name="set-up-advanced-notes-groups-for-vendors"></a>Impostare gruppi di note avanzate per fornitori

1. Andare a **Contabilità fornitori** \> **Impostazioni** \> **Note avanzate** \> **Gruppi note avanzate fornitori**.
2. Dopo aver creato i gruppi per i fornitori, andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**. 
3. Nella Scheda dettaglio **Impostazioni predefinite ordine fornitore**, nella sezione **Note avanzate** assegnare i riferimenti per i fornitori richiesti ai nuovi gruppi.

### <a name="set-up-advanced-notes-groups-for-products"></a>Impostare gruppi di note avanzate per prodotti 

1. Andare a **Gestione informazioni sul prodotto** \> **Impostazioni** \> **Note avanzate** \> **Gruppi note avanzate prodotti**.
2. Dopo aver creato i gruppi per i prodotti, andare a **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**. 
3. Nella Scheda dettaglio **Generale**, nella sezione **Amministrazione** assegnare i riferimenti per i prodotti richiesti ai nuovi gruppi.

### <a name="set-up-advanced-notes-for-customers-and-vendors"></a>Impostare note avanzate per clienti e fornitori

1. Per inserire il testo delle note avanzate per i clienti e impostare l'applicabilità delle note, andare a **Contabilità clienti**\>**Impostazioni**\>**Note avanzate**\>**Impostazione note avanzate clienti**.

![Configurazione di note avanzate dei clienti](media/emea-ita-exil-notes-setup.jpg)

2. Nella parte inferiore della pagina è possibile inserire il testo della nota nella lingua predefinita dell'utente. Per inserire il testo della nota in altre lingue, selezionare **Traduzioni**.

3. Nella parte superiore della pagina **Impostazione note avanzate**, è possibile impostare l'applicabilità alle note avanzate. Selezionare le caselle di controllo appropriate per attivare le note per i vari documenti disponibili. Sulla scheda **Intestazione**, è possibile definire note per tutti i clienti, i singoli clienti o i gruppi di clienti. Sulla scheda **Righe**, è possibile definire le note per tutti gli elementi o per singoli elementi.

![Configurazione di righe di note avanzate dei clienti](media/emea-ita-exil-notes-setup-item.jpg)

4. Per impostare le note avanzate per i fornitori, andare a **Contabilità fornitori**\>**Impostazioni**\>**Note avanzate**\>**Impostazione note avanzate fornitori**.

> [!NOTE]
> Per le note avanzate dei fornitori, **Ordine fornitore**è l'unico documento disponibile.

### <a name="set-up-document-types"></a>Imposta i tipi di documenti

Andare a **Amministrazione organizzazione**\>**Gestione documenti**\>**Tipi di documenti** per definire i tipi di documenti che vengono utilizzati quando vengono creati gli allegati di documenti correlati. Nel campo **Classe**, selezionare **Nota semplice**.

![Configurazione dei tipi di documenti](media/emea-ita-exil-notes-document-type.jpg)

### <a name="set-up-forms"></a>Imposta i moduli

Andare a **Contabilità clienti**\>**Impostazioni**\>**Moduli**\>**Impostazione moduli** per impostare i riferimenti ai tipi di documenti per i documenti correlati. Inoltre, è possibile definire se le note sono applicabili all'intestazione, alle righe o a entrambe le cose di un documento.

![Impostazione dei moduli](media/emea-ita-exil-notes-setup-forms.jpg)

### <a name="direct-attachment-to-documents"></a>Allegato diretto ai documenti
Le note avanzate possono essere direttamente collegate automaticamente alle conferme degli ordini di vendita, alle liste di prelievo, ai documenti di trasporto e alle fatture senza allegato preliminare agli ordini di vendita. Per abilitare l'allegato diretto, completare i seguenti passaggi. 
1. Passare a **Contabilità clienti** \> **Impostazioni** \> **Moduli** \> **Impostazione moduli**.
2. Nella scheda dettaglio **Generale**, nella sezione **Note avanzate** abilitare il parametro **Allegato diretto ai documenti**.

  ![Pagina di configurazione dei moduli, evidenziazione del parametro Allegato diretto ai documenti](media/attach-documents.jpg)

## <a name="advanced-notes-processing"></a>Elaborazione delle note avanzate

### <a name="generating-advanced-notes"></a>Generazione delle note avanzate

In Contabilità clienti, le note per conferme, distinte di prelievo, documenti di trasporto e fatture vengono generate automaticamente come allegati agli ordini cliente generati per clienti e prodotti selezionati.

![Note degli ordini cliente](media/emea-ita-exil-notes-order.jpg)

Le note per offerte e fatture a testo libero sono generate automaticamente nei documenti appropriati.

In Contabilità fornitori, le note vengono generate automaticamente come allegati a nuovi ordini fornitore per fornitori e prodotti applicabili.

### <a name="printing-advanced-notes"></a>Stampa delle note avanzate

Note avanzate definite come **Esterne**sono stampate nei relativi documenti commerciali a seconda delle impostazioni di **Impostazione moduli**

![Impostazione della stampa delle note avanzate](media/emea-ita-exil-notes-printing.jpg)
