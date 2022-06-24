---
title: Registrazione Contabilità clienti
description: Questo articolo spiega come vengono configurate le registrazioni nella contabilità clienti e fornisce esempi di configurazioni di registrazione.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492bbd31cae08a93cd68e5ce120d02a62141241b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874576"
---
# <a name="accounts-receivable-posting"></a>Registrazione nella contabilità clienti

[!include [banner](../includes/banner.md)]

Il profilo di registrazione principale per il modulo **Contabilità clienti** è il profilo di registrazione cliente. Questo profilo di registrazione determina il conto riepilogativo utilizzato quando i saldi cliente vengono registrati nella contabilità generale. Un conto riepilogativo è un conto principale. Viene anche chiamato conto commerciale Contabilità clienti.

Per ulteriori informazioni, vedi [Profili di registrazione cliente](../accounts-receivable/customer-posting-profiles.md).

Diverse configurazioni di registrazione oltre al profilo di registrazione cliente sono disponibili in Contabilità clienti. Nelle sezioni seguenti vengono fornite altre informazioni su queste altre configurazioni di registrazione.

## <a name="posting-accounts-for-methods-of-payment"></a>Conti registrazione per i metodi di pagamento

I metodi di pagamento definiscono come un pagamento viene registrato nella contabilità generale. Controllano anche il comportamento dell'output del pagamento. In genere, viene creato un metodo di pagamento per ogni tipo di pagamento accettato dall'organizzazione (ad esempio contanti, assegno, carta di credito, vaglia postale e bonifico).

I campi nella sezione **Registrazione** della Scheda dettaglio **Generale** controllano come un pagamento verrà registrato nella contabilità generale. Devi prima selezionare un valore nel campo **Tipo di conto**. Il tipo di conto selezionato controlla il comportamento del campo **Conto pagamenti**. Ti consigliamo di selezionare **Banca** nel campo **Tipo di conto** e quindi selezionare il conto bancario nel campo **Conto pagamenti**. Il vantaggio dell'approccio è che il sistema registrerà il pagamento nel giornale di registrazione secondario Banca, che supporta la riconciliazione e altri processi relativi alla cassa. La tabella seguente mostra un esempio della configurazione del profilo di registrazione se stai utilizzando il modulo **Gestione cassa e banche**.

| Tipo di registrazione | Tipo di account | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Banca | Banca | Banca di Contoso | Conto bancario collegato a un cespite | Credito | Numero | Per ogni metodo di pagamento, inserisci il conto principale nel campo **Conto pagamenti**. |

Se non hai intenzione di utilizzare la gestione cassa e banche, devi selezionare **Contabilità** nel campo **Tipo di conto** e quindi selezionare il conto principale nel campo **Conto pagamenti**. La tabella seguente mostra un esempio della configurazione del profilo di registrazione se non stai utilizzando Gestione cassa e banche.

| Tipo di registrazione | Tipo di account | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Banca di Contoso | Attività | Credito | Numero | Per ogni metodo di pagamento, inserisci il conto principale nel campo **Conto pagamenti**. |

## <a name="bridging-accounts"></a>Conti provvisori

La registrazione provvisoria è un processo in due fasi utilizzato quando vengono registrati i pagamenti. È una funzionalità opzionale che può essere utilizzata con conti bancari a saldo zero, ad esempio. Può aiutare a garantire un processo di riconciliazione bancaria più agevole e tempestivo. Nella prima fase, un pagamento viene registrato su un conto temporaneo (il conto provvisorio). Nel secondo passaggio, il movimento registrato viene stornato e registrato sul conto bancario quando il pagamento compensa la banca. La tabella seguente mostra un esempio della configurazione del profilo di registrazione per la registrazione provvisoria.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Giornale di registrazione contabile | 130725 | Contanti non compensati | Passività | Dare | Sì | Per ogni metodo di pagamento, inserisci il conto principale nel campo **Conto provvisorio**. |

Per ulteriori informazioni, vedi [Impostare ed elaborare pagamenti provvisori](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="posting-accounts-for-customer-cash-discounts"></a>Conti di registrazione per gli sconti di cassa dei clienti

Se l'organizzazione offre sconti di cassa ai clienti in cambio di un pagamento rapido, è necessario configurare i codici di sconto di cassa e specificare come devono essere registrati gli sconti nella contabilità generale. Sono disponibili diverse opzioni per specificare il conto principale utilizzato per registrare uno sconto di cassa del cliente.

Per ulteriori informazioni, vedere [Sconti di cassa](../cash-bank-management/cash-discounts.md).

## <a name="posting-accounts-for-payment-fees"></a>Conti di registrazione per le commissioni di pagamento

Le commissioni di pagamento ti consentono di aggiungere automaticamente una commissione a un pagamento cliente quando si applica una serie di condizioni. Le commissioni di pagamento possono essere addebitate al cliente o possono essere registrate sul tuo conto bancario come spesa. Di seguito sono riportati alcuni esempi.

- Ai clienti viene addebitato il 3% del totale del pagamento se pagano utilizzando una carta di credito.
- La tua banca ti addebita 1,00 USD per ogni bonifico che elabori e la commissione del bonifico viene addebitata.

Quando configuri una commissione di pagamento cliente, se imposti il campo **Addebito** su **Cliente**, il campo **Conto principale** diventa non disponibile e il sistema utilizza il profilo di registrazione del cliente per registrare la commissione. Se imposti il campo **Addebito** su **Contabilità**, è necessario impostare il campo **Conto principale** sul conto principale in cui verrà registrata la commissione di pagamento. S solito il conto principale è un conto spese. La tabella seguente mostra un esempio della configurazione del profilo di registrazione per la registrazione commissione di pagamento.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Giornale di registrazione contabile | 618190 | Spesa di commissione bancaria | Spese | Dare | No |  Se **Contabilità generale** è selezionato nel campo **Addebito**, seleziona questo conto nel campo **Contro principale** per la commissione pagamento. |

Per ulteriori informazioni, vedere [Definire le commissioni di pagamento cliente](../accounts-receivable/tasks/establish-customer-payment-fees.md).

## <a name="posting-accounts-for-charges-codes"></a>Conti di registrazione per i codici di spese

Se è necessario tenere traccia degli importi di vendita in aggiunta alle voci, puoi utilizzare i codici di spese. Ad esempio, potresti addebitare le spese di trasporto e gestione ai clienti potrebbe addebitare alcune spese di trasporto e gestione internamente. È possibile specificare se questi importi devono essere registrati nei conti spese o aggiunti al costo degli articoli.

I codici di spese possono essere creati per la contabilità clienti e la contabilità fornitori. Quando configuri un codice di spese, è necessario definire la registrazione. La registrazione controlla sia il conto in Dare che il conto in Avere. Per ogni codici di spesa creato, puoi selezionare il tipo di registrazione utilizzato. La tabella seguente mostra tipi esempi di codici di addebito tipici per Contabilità clienti.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Commissione pagamento | 411400 | Ricavi – Commissioni | Ricavi | Credito | Numero | **Esempio per fondi insufficienti:** Conto cliente/fornitore di addebito e conto di credito |
| Ordine, spese di trasporto | 403500 | Ricavi – Spese di trasporto | Ricavi | Credito | Numero | **Esempio di spese di trasporto addebitate a un cliente:** Conto cliente/fornitore di addebito e conto di accredito |
| Ribasso\* | 403200 | Sconto | Ricavi | Dare | Numero | **Esempio per uno sconto cliente:** Conto cliente/fornitore di addebito e conto di credito |

\* Per l'esempio di sconto, la registrazione viene utilizzata solo quando un codice di spese viene aggiunto a un'intestazione o una riga di un ordine fornitore. La funzionalità di sconto avanzata disponibile in Microsoft Dynamics 365 Supply Chain Management fornisce un maggiore controllo e automazione degli sconti. Per ulteriori informazioni, vedi [Sconti cliente](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md).

La tabella precedente mostra tre esempi tipici di tipi di registrazione che possono essere utilizzati per i codici di spese. Dovrebbe essere usata come linea guida e un esempio. Non fornisce un elenco completo di tutte le possibili combinazioni o tipi di registrazione che possono essere utilizzati.

Per ulteriori informazioni, vedi [Creare codici di spese](../accounts-receivable/create-charges-codes.md).

## <a name="posting-accounts-for-commissions"></a>Conti di registrazione per commissioni

È possibile configurare facoltativamente il sistema per calcolare le commissioni per un rappresentante di vendita o un gruppo di rappresentanti di vendita su un determinato ordine cliente. Se abiliti questa funzionalità, devi configurare il conto di registrazione utilizzato per calcolare la commissione. Questa configurazione viene eseguita nella pagina **Registrazione provvigione** nel modulo **Vendite e marketing**.

Per ulteriori informazioni, vedere [Impostare regole per la provvigione vendite](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md).
