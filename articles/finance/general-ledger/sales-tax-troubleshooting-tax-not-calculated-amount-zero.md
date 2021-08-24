---
title: L'imposta non viene calcolata o l'importo dell'imposta è zero
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando l'importo dell'imposta è 0 (zero) o l'imposta non viene calcolata.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 45aa5931b5d958dd32bd165b414957fa7b366d077cef67621221ce19b56b67d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772805"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>L'imposta non viene calcolata o l'importo dell'imposta è zero

[!include [banner](../includes/banner.md)]

Una transazione potrebbe avere un importo di riga diverso da 0 (zero), ma l'imposta non viene calcolata o l'importo calcolato dell'imposta è 0. Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>Verificare che i codici imposta siano selezionati correttamente dalla transazione

Se la transazione non seleziona i codici imposta corretti o se non seleziona alcun codice imposta, le tasse non verranno calcolate su di essa. Segui questi passaggi per verificare che i codici imposta siano selezionati correttamente dalla transazione 

1. Nella riga della transazione, nella scheda dettaglio **Dettagli riga**, nella scheda **Impostazioni**, nella sezione **IVA**, verifica che siano selezionate le fasce IVA corrette nei campi **Fascia IVA articoli** e **Fascia IVA**. Se non sono selezionate le fasce IVA corrette, selezionale.

    [![Campi Fascia IVA articoli e Fascia IVA.](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. Passare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Fasce IVA**.
3. Seleziona la fascia IVA appropriata, quindi, nella Scheda dettaglio **Impostazioni**, prendere nota del codice imposta nel campo **Codice IVA**.

    [![Pagina Fasce IVA.](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. Passare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Fasce IVA articoli**.
5. Selezionare la fascia IVA articoli appropriata e quindi, nel Scheda dettaglio **Impostazioni**, verificare che il codice imposta nel campo **Codice IVA** corrisponde al codice imposta della fascia IVA.

    [![Pagina Fasce IVA articoli.](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. Se i codici imposta non corrispondono, aggiorna il codice IVA per uno dei gruppi.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>Verificare che i codici imposta selezionati non siano esenti e che abbiano il valore dell'aliquota fiscale corretto

Se i codici imposta sono esenti o se l'aliquota fiscale è 0 (zero), il risultato del calcolo dell'imposta sarà 0. Segui questi passaggi per determinare se i codici imposta selezionati sono esenti e per verificare che ad essi sia applicata l'aliquota fiscale corretta.

1. Passare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Fasce IVA**.
2. Seleziona la fascia IVA appropriata, quindi, nella scheda dettaglio **Impostazioni**, verificare che la casella di controllo **Esenzione** è deselezionata. Se è selezionata, deselezionala.

    [![Casella di controllo Esenzione nella pagina Fasce IVA.](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.
4. Seleziona il codice IVA appropriato, quindi verifica che il valore dell'aliquota fiscale nel campo **Valore** non è 0 (zero). Se è 0, aggiorna il campo in modo che sia impostato sull'aliquota fiscale corretta.

    [![Campo Valore nella pagina Valori codice IVA.](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>Determina se zero è l'importo dell'imposta corretto

In alcuni scenari, un importo di imposta pari a 0 (zero) è corretto. Segui questi passaggi per determinare se 0 è l'importo fiscale corretto per la tua transazione.

1. Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.
2. Nella scheda **IVA**, nel campo **Metodo di calcolo**, verifica che **Totale** sia selezionato.

    [![Campo Metodo di calcolo nella pagina Parametri di contabilità generale.](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.
4. Seleziona il codice IVA appropriato, seleziona **Calcolo** \> **Base marginale** e verifica che la base marginale sia impostata su **Importo netto del saldo fattura** o **Totale fattura inclusi altri importi IVA**. Per ulteriori informazioni, vedere [Totale fattura inclusi altri importi IVA](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).
5. Se i valori corretti sono impostati nei passaggi 2 e 4, determinare se l'importo totale della transazione è 0 (zero). Se l'importo totale è 0, un importo fiscale pari a 0 è il risultato atteso. Poiché il calcolo delle imposte si basa sull'importo totale del saldo della fattura e tale importo non è riga per riga, l'importo dell'imposta pari a 0 verrà assegnato a ciascuna riga dopo il calcolo delle imposte.

## <a name="determine-whether-customization-exists"></a>Determinare se esiste la personalizzazione

Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione. Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
