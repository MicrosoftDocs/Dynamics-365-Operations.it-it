---
title: L'imposta è registrata nel conto CoGe sbagliato nel giustificativo
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando l'imposta viene registrata nel conto CoGe errato nel giustificativo.
author: qire
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 9c9f3fc63374b185a795977566cf73c8c29ee5d3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686437"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>L'imposta è registrata nel conto CoGe sbagliato nel giustificativo

[!include [banner](../includes/banner.md)]

Durante la registrazione, l'importa potrebbe essere registrata nel conto CoGe sbagliato nel giustificativo. Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto. Gli esempi in questo argomento utilizzano un ordine cliente come documento aziendale.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>Trovare il codice imposta della transazione fiscale registrata in modo errato

1. Nella pagina **Transazioni giustificativo** selezionare la transazione con cui si desidera lavorare, quindi selezionare **IVA registrata**.

    [![Pulsante IVA registrata nella pagina Transazioni giustificativo.](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. Nel campo **Codice IVA** rivedere il valore. In questo esempio, è **IVA 19**.

    [![Campo Codice IVA nella pagina IVA registrata.](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>Controllare il gruppo di registrazione contabile del codice imposta

1. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.
2. Trova e seleziona il codice imposta, quindi controlla il valore nel campo **Gruppo registrazione contabile**. In questo esempio, è **IVA**.

    [![Campo Gruppo registrazione contabile nella pagina dei codici IVA.](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. Il valore nel campo **Gruppo registrazione contabile** è un collegamento. Per visualizzare i dettagli della configurazione del gruppo, selezionare il collegamento. In alternativa, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il campo, quindi seleziona **Visualizza dettagli**.

    [![Comando Visualizza dettagli.](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. Nel campo **IVA a debito** verificare che il numero di conto sia corretto, in base al tipo di transazione. In caso contrario, seleziona il conto corretto in cui registrare. In questo esempio, l'IVA dell'ordine fornitore deve essere registrata nel conto IVA a debito 222200.

    [![Il campo IVA a debito nella pagina dei gruppi di registrazione contabile.](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    La tabella seguente fornisce informazioni su ogni campo nella pagina **Gruppi registrazione contabile**.

    | Campo                  | descrizione |
    |------------------------|-------------|
    | IVA a debito      | Immettere il conto principale per l'IVA in uscita (pagabile all'ufficio IVA). |
    | IVA a credito   | Il conto principale per l'IVA in entrata proveniente dall'ufficio IVA. |
    | Importo IVA intracomunitaria        | Il conto principale utilizzato per registrare le imposte di utilizzo deducibili che i fornitori non richiedono o non dichiarano all'autorità fiscale come parte dell'Imposta sui Beni e Servizi (GST)/Harmonized Sales Tax (HST) reverse charge dell'Unione europea (UE). L'opzione **IVA intracomunitaria** deve essere selezionata per il codice IVA nella fascia IVA utilizzata nella transazione. Questo campo non è disponibile se è selezionata l'opzione **Applica regole di tassazione IVA** nella pagina **Parametri di contabilità generale**. |
    | IVA intracomunitaria a debito        | Conto principale utilizzato per registrare le imposte di utilizzo in entrata pagabili alle autorità fiscali. |
    | Conto di liquidazione     | Conto principale utilizzato per registrare il saldo netto dei conti CoGe specificati nei campi **VAT intracomunitaria a debito** e **IVA a credito**. |
    | Sconto di cassa fornitore   | Il conto principale utilizzato per la registrazione di uno sconto di cassa per i codici IVA associati al gruppo di registrazione contabile. |
    | Sconto di cassa cliente | Il conto principale utilizzato per la registrazione di uno sconto di cassa per i codici IVA associati al gruppo di registrazione contabile. |

    Per ulteriori informazioni, vedere [Impostare gruppi di registrazione contabile per l'IVA](tasks/set-up-ledger-posting-groups-sales-tax.md).

## <a name="debug-in-code-to-check-ledger-dimensions"></a>Eseguire il debug nel codice per controllare le dimensioni contabili

Nel codice, il conto di registrazione è determinato dalla dimensione contabile. La dimensione contabile salva l'ID record di un conto nel database.

1. Per un ordine cliente, aggiungere un punto di interruzione nei metodi **Tax::saveAndPost()** e **Tax::post()**. Presta attenzione al valore di **\_ledgerDimension**.

    [![Esempio di codice di ordine cliente con un punto di interruzione.](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    Per un ordine fornitore, aggiungere un punto di interruzione ai metodi **TaxPost::saveAndPost()** e **TaxPost::postToTaxTrans()**. Presta attenzione al valore di **\_ledgerDimension**.

    [![Esempio di codice di ordine fornitore con un punto di interruzione.](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. Eseguire la seguente query SQL per trovare il valore visualizzato del conto nel database, in base all'ID record salvato dalla dimensione contabile.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![Valore visualizzato dell'ID record.](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. Esamina il callstack per trovare dove il valore **_ledgerDimension** viene assegnato. Di solito, il valore proviene da **TmpTaxWorkTrans**. In questo caso, dovresti aggiungere un punto di interruzione in **TmpTaxWorkTrans::insert()** e **TmpTaxWorkTrans::update()** per trovare dove il valore assegnato.

## <a name="determine-whether-customization-exists"></a>Determinare se esiste la personalizzazione

Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione. Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
