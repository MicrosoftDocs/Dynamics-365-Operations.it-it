---
title: Fatture elettroniche del fornitore
description: Questo argomento spiega come configurare e inviare fatture elettroniche del fornitore in Italia.
author: ikondo
ms.date: 12/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 3984823
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2021-12-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d797ec3f9b08ec850c7a73518035b33490763329
ms.sourcegitcommit: 6109fc2fe5f407363bb6f240d64b7214657f5914
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2022
ms.locfileid: "8603071"
---
# <a name="vendor-electronic-invoices"></a>Fatture elettroniche del fornitore

[!include [banner](../includes/banner.md)]

Secondo la normativa italiana, le fatture che pervengono da fornitori esteri non fiscalmente residenti in Italia devono essere presentate al Sistema di Interscambio (SDI). Questo argomento spiega come configurare e inviare le fatture elettroniche del fornitore nel formato elettronico **FatturaPA**.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- L'esportazione delle fatture elettroniche dei fornitori deve essere implementata simmetricamente all'esportazione delle fatture elettroniche dei clienti italiani e deve utilizzare i parametri comuni definiti nella pagina **Parametri fattura elettronica** in Contabilità clienti. Questi parametri devono essere configurati in anticipo. Per ulteriori informazioni, vedi [Fatture elettroniche dei clienti](emea-ita-e-invoices.md).

## <a name="configure-accounts-payable-parameters"></a><a id="apparameters"></a>Configurare i parametri di Contabilità fornitori 

Segui questi passaggi per impostare la configurazione della fattura elettronica in Parametri contabilità fornitori.

1. Vai a **Contabilità fornitori** \> **Impostazioni** \> **Parametri contabilità fornitori**.
2. Nella scheda **Documenti elettronici** nel campo **Fattura fornitore (esportazione)** seleziona la configurazione **Fattura fornitore (IT)**. Questa configurazione viene utilizzata per generare i file XML per l'esportazione delle fatture elettroniche dei fornitori.

   ![Campo Fattura fornitore (esportazione) impostato nella scheda Documenti elettronici della pagina Parametri contabilità fornitori.](media/emea-ita-AP-parameter-e-invoices.jpg)

   > [!NOTE]
   > Le configurazioni devono essere importate prima di poter essere selezionate. Per ulteriori informazioni, vedere [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).
   >
   > La configurazione del modello padre, **Modello fattura** e la relativa configurazione di mapping del modello, **Mapping modello di fattura fornitore (IT)**, verranno importate o aggiornate automaticamente.

## <a name="enable-electronic-invoice-generation"></a>Abilitare la generazione di fatture elettroniche

Segui questi passaggi per abilitare il registro della fattura elettronica e la generazione della fattura elettronica per un fornitore.

1. Vai a **Contabilità fornitori** \> **Tutti i fornitori**.
2. Seleziona e apri il record del fornitore per il quale abilitare il registro della fattura elettronica. 
2. Nella scheda dettaglio **Fattura e consegna** nella sezione **Fattura elettronica** attiva l'opzione **Registro fattura elettronica** per abilitare la generazione di fatture elettroniche per il fornitore selezionato.

## <a name="configure-invoice-types"></a>Configurare i tipi di fattura 

Il tipo di fattura è un attributo obbligatorio delle fatture elettroniche. Deve essere assegnato a una fattura elettronica prima che tale fattura sia inviata al sistema di Exchange.

### <a name="define-invoice-types"></a>Definire i tipi di fattura 

Segui questi passaggi per definire uno o più tipi di fattura.

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri fatture elettroniche**. 
2. Nella scheda **Tipi di fattura** definisci i codici per uno o più tipi di fattura richiesti e immetti una descrizione di ciascuno.

   ![Tipi di fattura definiti nella scheda Tipi di fattura della pagina Parametri fattura elettronica.](media/emea-ita-invoice-types.jpg)

### <a name="assign-invoice-types-to-sales-tax-codes"></a>Assegnare i tipi di fattura ai codici IVA

È possibile associare i tipi di fattura a codici IVA specifici. 

1. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.
2. Nella scheda dettaglio **Generale** nel campo **Tipo di fattura** immetti il riferimento a un tipo di fattura specifico.

   ![Tipo di fattura assegnato a un codice IVA nella pagina Codici IVA.](media/emea-ita-invoice-types-tax-codes.jpg)

## <a name="invoice-types-processing"></a>Elaborazione dei tipi di fattura

I tipi di fattura associati al codice IVA utilizzato su una fattura vengono inseriti automaticamente nel tag **TipoDocumento** del file XML che viene generato per la fattura elettronica.

Se al codice IVA non è associato alcun tipo di fattura, verranno inseriti automaticamente i seguenti tipi di documenti fattura fornitore:

- **TD16** – Per i fornitori che si trovano in Italia, se una fattura contiene un codice IVA dove **Imposta d'uso** o **Reverse charge** è attivato.
- **TD17** – Per i fornitori che si trovano nell'Unione Europea (UE), se viene emessa una fattura per la fornitura di **Servizi**.
- **TD18** – Per i fornitori che si trovano nell'Unione Europea (UE), se viene emessa una fattura per la vendita di **prodotti**.

Se un tipo di fattura richiesto non è immesso, è possibile modificare manualmente il tipo di fattura nel giornale di registrazione fatture fornitore.

### <a name="configure-electronic-document-properties"></a>Configurare le proprietà documento elettronico

1. Vai a **Contabilità clienti** > **Impostazione** > **Tipi di proprietà del documento elettronico**.
2. Seleziona **Nuovo** per aggiungere un tipo di proprietà.
2. Nel campo **Tipo** immetti **DocumentType**. 
3. Seleziona **Applicabilità** per aggiungere una tabella applicabile. 
4. Nella pagina **Impostazione dell'applicabilità dei tipi di proprietà di documenti elettronici**, nel campo **Nome tabella** seleziona **Giornale di registrazione fatture fornitore**.
5. Salva e torna alla pagina **Tipi di proprietà di documenti elettronici**.

   ![Tipo di proprietà aggiunto nella pagina Tipi di proprietà di documenti elettronici.](media/emea-ita-invoice-type-parameter.jpg)

### <a name="register-invoice-types"></a>Registrare i tipi di fattura

Segui i passaggi seguenti per registrare i tipi di fattura.

1. Andare a **Contabilità fornitori** \> **Richieste di informazioni e report** \> **Fattura** \> **Giornale di registrazione fatture**.
2. Seleziona una fattura nell'elenco, quindi seleziona **Proprietà del documento elettronico**.

    ![Pulsante Proprietà documento elettronico.](media/emea-ita-invoice-type-in-invoice.jpg)

3. Inserisci un tipo di fattura richiesto. Il valore del campo **Valore** per il tipo di fattura sovrascrive eventuali codici creati automaticamente quando vengono generati i file XML per le fatture elettroniche.

    ![Valore del tipo di fattura immesso nella pagina delle proprietà del documento elettronico.](media/emea-ita-invoice-type-value.jpg)

## <a name="process-vendor-electronic-invoices"></a>Elaborare le fatture elettroniche del fornitore

Per visualizzare tutte le fatture elettroniche dei fornitori ed eseguire varie azioni, andare a **Contabilità clienti** > **Fatture** > **Fatture elettroniche** > **Fatture elettroniche**. La funzionalità è simile alla funzionalità per l'elaborazione delle fatture elettroniche dei clienti. Per ulteriori informazioni, vedere [Registro delle fatture elettroniche](emea-ita-e-invoices.md#einvoiceregister).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
