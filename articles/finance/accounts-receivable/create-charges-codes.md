---
title: Creare codici di spese
description: Questo articolo spiega come configurare i codici di spese per Contabilità fornitori e Contabilità clienti.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MarkupTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d65952cb989672e4eac2dd6101ee9c7c9424daed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866085"
---
# <a name="create-charges-codes"></a>Creare codici di spese

Questo articolo spiega come configurare i codici di spese per Contabilità fornitori e Contabilità clienti. Se l'organizzazione richiede che gli importi di vendita o di acquisto vengano monitorati oltre alle voci di un ordine cliente o di un ordine fornitore, è possibile utilizzare i codici di spese a questo scopo. Ad esempio, è possibile pagare il trasporto e l'assicurazione su un ordine fornitore e tali importi vengono dettagliati separatamente nell'ordine fornitore. In questo caso, puoi specificare se gli importi devono essere registrati nei conti spese o aggiunti al costo degli articoli.

## <a name="set-up-charges-codes-for-accounts-receivable"></a>Impostare codici spese per la contabilità clienti

Per creare codici di spese per Contabilità clienti, attieniti alla seguente procedura.

1. Andare a **Contabilità clienti** &gt; **Impostazione spese** &gt; **Codice di spese**.
2. Selezionare **Nuovo**.
3. Nel campo **Codice di spese** immetti un codice per le spese.
3. Nel campo **Descrizione** immetti una descrizione delle spese.
4. Facoltativo: nel campo **Fascia IVA articoli** seleziona una fascia IVA articoli.
5. Nella Scheda dettaglio **Registrazione** specifica come addebitare e accreditare automaticamente le spese.
6. Se come tipo di addebito o accredito è stato selezionato **Conto CoGe** specifica un tipo di registrazione nei campi **Registrazione** e specifica il conto principale nei campi **Conto**.

### <a name="example"></a>Esempio

Il cliente paga le spese. Di conseguenza vengono aggiunte ai totali dell'ordine cliente. È necessario impostare le seguenti informazioni di registrazione:

- Nel campo **Tipo** della sezione **Dare** seleziona **Cliente/Fornitore** per aggiungere le spese in fattura al conto del cliente.
- Nel campo **Tipo** della sezione **Avere** seleziona **Conto CoGe**. Quindi, nel campo **Conto** seleziona il conto principale per i ricavi dalle spese in fattura.

> [!NOTE]
> Se il tipo di Dare o Avere per il codice selezionato è **Conto CoGe** o **Articolo**, puoi inserire una valuta diversa per la transazione di spese.

È possibile stampare il testo per le spese nella lingua assegnata al cliente. Seleziona **Traduzioni** per specificare il testo per il codice di spese in altre lingue.

## <a name="set-up-charges-codes-for-accounts-payable"></a>Impostare codici di spese per la contabilità fornitori

Per creare codici di spese per Contabilità fornitori, attieniti alla seguente procedura.

1. Eseguire uno dei passaggi riportati di seguito.

    - Vai a **Contabilità fornitori** &gt; **Impostazione** **spese** &gt; **Codice di spese**.
    - Vai a **Approvvigionamento** &gt; **Impostazione** &gt; **Spese** &gt; **Codice di spese**.

2. Selezionare **Nuovo**.
3. Nel campo **Codice di spese** immetti un codice per le spese.
3. Nel campo **Descrizione** immetti una descrizione delle spese.
4. Facoltativo: nel campo **Fascia IVA articoli** seleziona una fascia IVA articoli.
5. Facoltativo: nel campo **Importo massimo** immetti l'importo massimo che si concede per il codice di spese.

    Questo campo viene utilizzato per convalidare gli addebiti per le fatture fornitore. Per abilitare la convalida delle spese, seleziona la casella di controllo **Abilita convalida abbinamento fatture** nella scheda **Convalida fattura** della pagina **Parametri contabilità fornitori**.

    > [!IMPORTANT]
    > Per convalidare le spese per le fatture, è inoltre necessario creare un'istanza di un tipo di regola dei criteri basata sulle spese per i criteri della fattura fornitore specifici.

6. Nella Scheda dettaglio **Registrazione** specifica come addebitare e accreditare automaticamente le spese.
7. Se come tipo di addebito o accredito è stato selezionato **Conto CoGe** specifica un tipo di registrazione nei campi **Addebito** e **Accredito** e specifica il conto principale nei campi **Conto in Dare** e **Conto in Avere**.
8. Per consentire il confronto dei valori delle spese per una fattura contenente le spese nell'intestazione o nelle righe corrispondenti dell'ordine fornitore, seleziona la casella di controllo **Confronta valori ordine fornitore e fattura**.

### <a name="example"></a>Esempio

Le spese possono essere registrate come tali come parte del totale per l'ordine fornitore o la fattura fornitore. Per configurare le informazioni di registrazione procedi come descritto di seguito. 

- Nel campo **Tipo** della sezione **Avere** seleziona **Cliente/Fornitore** per aggiungere le spese in fattura al conto del fornitore.
- Nel campo **Tipo** della sezione **Dare** seleziona **Conto CoGe**. Quindi, nel campo **Conto** seleziona il conto principale per le spese dalle spese in fattura.

Attieniti alla seguente procedura per impostare le informazioni di registrazione in modo che la spesa unitaria venga aggiunta al costo dell'articolo.

- Nel campo **Tipo** della sezione **Avere** seleziona **Cliente/Fornitore** per aggiungere le spese in fattura al conto del fornitore.
- Nel campo **Type** della sezione **Dare** seleziona **Articolo** per aggiungere le spese al costo dell'articolo.

> [!NOTE]
> È consigliabile utilizzare una valuta diversa da quella specificata nell'ordine fornitore o nella fattura. Puoi immettere una valuta differente se il tipo di addebito o di accredito per il codice spese selezionato è impostato su **Conto CoGe** o **Articolo**.

È possibile stampare il testo per le spese nella lingua assegnata al cliente. Seleziona **Traduzioni** per specificare il testo per il codice di spese in altre lingue.
