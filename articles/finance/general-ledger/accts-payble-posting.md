---
title: Registrazioni nella contabilità fornitori
description: Questo argomento spiega come vengono configurate le registrazioni nella Contabilità fornitori e fornisce esempi di configurazioni di registrazione.
author: rachel-profitt
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPosting, VendPaymMode, VendCashDiscount, MarkupTable\_Vend, VendPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb3ebad31c9f41e405b9fc31a0f71df05fa1cc60
ms.sourcegitcommit: 10b85a09e8a550155a69aa2a8877a7c88b887242
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2022
ms.locfileid: "8014467"
---
# <a name="accounts-payable-posting"></a>Registrazione nella contabilità fornitori

[!include [banner](../includes/banner.md)]

Il profilo di registrazione principale per il modulo **Contabilità fornitori** è il profilo di registrazione fornitore. Questo profilo di registrazione determina il conto riepilogativo utilizzato quando i saldi fornitore vengono registrati nella contabilità generale. Un conto riepilogativo è un conto principale. Viene anche chiamato conto commerciale Contabilità fornitori.

Per ulteriori informazioni, vedi [Profili di registrazione fornitore](../accounts-payable/vendor-posting-profiles.md).

Diverse configurazioni di registrazione oltre al profilo di registrazione fornitore sono disponibili in Contabilità fornitori. Nelle sezioni seguenti vengono fornite altre informazioni su queste altre configurazioni di registrazione.

## <a name="methods-of-payment-posting-accounts"></a>Conti registrazione di metodi di pagamento

I metodi di pagamento definiscono come un pagamento viene registrato nella contabilità generale. Controllano anche il comportamento dell'output del pagamento. In genere, viene creato un metodo di pagamento per ogni tipo di pagamento effettuato dall'organizzazione (ad esempio contanti, assegno, carta di credito, vaglia postale e bonifico).

I campi nella sezione **Registrazione** della Scheda dettaglio **Generale** nella pagina **Metodi di pagamento** (**Contabilità fornitori > Impostazione pagamento > Metodi di pagamento**) controlla come verrà registrato un pagamento nella contabilità generale. Devi prima selezionare un valore nel campo **Tipo di conto**. Il tipo di conto selezionato controlla il comportamento del campo **Conto pagamenti**. Ti consigliamo di selezionare **Banca** nel campo **Tipo di conto** e quindi selezionare il conto bancario nel campo **Conto pagamenti**. Il vantaggio dell'approccio è che il sistema registrerà il pagamento nel giornale di registrazione secondario Banca, che supporta la riconciliazione e altri processi relativi alla cassa. La tabella seguente mostra un esempio della configurazione del profilo di registrazione se stai utilizzando il modulo **Gestione cassa e banche**.

| Tipo di registrazione | Tipo di account | Esempio di nome di conto pagamenti | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|--------------|------------------------------|--------------|---------------|------------------|-------------|
| Banca | Banca | Banca d'America | Conto bancario collegato a un cespite | Dare | No | Per ogni metodo di pagamento, inserisci il conto principale nel campo **Conto pagamenti**. |

Se non hai intenzione di utilizzare la gestione cassa e banche, devi selezionare **Contabilità** nel campo **Tipo di conto** e quindi selezionare il conto principale nel campo **Conto pagamenti**. La tabella seguente mostra un esempio della configurazione del profilo di registrazione se **non** stai utilizzando Gestione cassa e banche.

| Tipo di registrazione | Tipo di account |Esempio di conto pagamenti | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|--------------|------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Banca d'America | AttivitÃ  | Dare | No | Per ogni metodo di pagamento, inserisci il conto principale nel campo **Conto pagamenti**. |

## <a name="bridging-accounts"></a>Conti provvisori

La registrazione provvisoria è un processo in due fasi utilizzato quando vengono registrati i pagamenti. È una funzionalità opzionale che può essere utilizzata con conti bancari a saldo zero, ad esempio. Può aiutare a garantire un processo di riconciliazione bancaria più agevole e tempestivo. Nella prima fase, un pagamento viene registrato su un conto temporaneo (il conto provvisorio). Nel secondo passaggio, il movimento registrato viene stornato e registrato sul conto bancario quando il pagamento compensa la banca. La tabella seguente mostra un esempio della configurazione del profilo di registrazione per la registrazione provvisoria.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Giornale di registrazione contabile | 130725 | Contanti non compensati | Passività | Dare | Sì | Per ogni metodo di pagamento, inserisci il conto principale nel campo **Conto provvisorio**. |

Per ulteriori informazioni, vedi [Impostare ed elaborare pagamenti provvisori](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="customer-cash-discounts-posting-accounts"></a>Conti di registrazione degli sconti di cassa dei clienti

Se l'organizzazione riceve sconti di cassa dai fornitori in cambio di un pagamento rapido, è necessario configurare i codici di sconto di cassa e specificare come devono essere registrati gli sconti nella contabilità generale. Sono disponibili diverse opzioni per specificare il conto principale utilizzato per registrare uno sconto di cassa del cliente.

Per ulteriori informazioni, vedere [Sconti di cassa](../cash-bank-management/cash-discounts.md).

## <a name="payment-fee-posting-accounts"></a>Conti di registrazione delle commissioni di pagamento

Le commissioni di pagamento ti consentono di aggiungere automaticamente una commissione a un pagamento fornitore quando si applica una serie di condizioni. Le commissioni di pagamento possono essere pagate al fornitore o possono essere registrate sul tuo conto bancario come spesa. Di seguito sono riportati alcuni esempi.

- Un fornitore ti addebita il 3% del totale del pagamento se paghi utilizzando una carta di credito.
- La tua banca ti addebita 1,00 USD per ogni bonifico che elabori e la commissione del bonifico viene addebitata.

Quando configuri una commissione di pagamento fornitore, se imposti il campo **Addebito** su **Fornitore**, il campo **Conto principale** diventa non disponibile e il sistema utilizza il profilo di registrazione del fornitore per registrare la commissione. Se imposti il campo **Addebito** su **Contabilità**, è necessario impostare il campo **Conto principale** sul conto principale in cui verrà registrata la commissione di pagamento. S solito il conto principale è un conto spese. La tabella seguente mostra un esempio della configurazione del profilo di registrazione per la registrazione commissione di pagamento.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|----------------|------------------|-------------|
| Giornale di registrazione contabile | 618190 | Spesa di commissione bancaria | Spese | Dare | No | Se **Contabilità generale** è selezionato nel campo **Addebito**, seleziona questo conto nel campo **Contro principale** della pagina **Commissione pagamento**. |

Per ulteriori informazioni, vedere [Definire le commissioni di pagamento fornitore](../accounts-payable/tasks/define-vendor-payment-fees.md).

## <a name="charges-code-posting-accounts"></a>Conti di registrazione di codici di spese

Se è necessario tenere traccia degli importi di acquisto in aggiunta alle voci, puoi utilizzare i codici di spese. Ad esempio, il tuo fornitore potrebbe addebitarti le spese di trasporto e gestione, oppure potrebbe addebitarti alcune spese di trasporto e gestione interne. È possibile specificare se questi importi devono essere registrati nei conti spese o aggiunti al costo degli articoli.

I codici di spese possono essere creati per la contabilità clienti e la contabilità fornitori. Quando configuri un codice di spese, è necessario definire la registrazione. La registrazione controlla sia il conto in Dare che il conto in Avere. Quando crei i codici di spese, puoi selezionare il tipo di registrazione utilizzato per ciascun codice di spese. La tabella seguente mostra esempi di codici di spese tipici per Contabilità fornitori nella pagina **Codici di spese**.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Addebito acquisto | Lascia vuoto il campo. | Non applicabile | Articolo | Dare | No | **Esempio di commissione di acquisto per un articolo:** </p><ul><li>Campo **Tipo di addebito** = **Articolo**</li><li>  Campo **Tipo di accredito** = **Cliente/Fornitore**.</li><li> La registrazione dell'articolo utilizza il conto principale del profilo di registrazione dell'inventario. |
| Ordine, spese di trasporto | 600120 | Spese di trasporto | Ricavi | Dare | No | **Esempio di spese di trasporto pagate a un fornitore:** </p><ul><li>Campo **Tipo di addebito** = **Conto CoGe**</li><li> Campo **Tipo di accredito** = **Cliente/Fornitore** |
| Ribasso\* | 503160 | Sconto fornitore (contro COGS)| Spese | Credito | No | **Esempio di sconto fornitore:**</p><ul><li>Campo **Tipo di addebito** = **Cliente/Fornitore**</li><li>Campo **Tipo di accredito** = **Conto CoGe** |

\* Per l'esempio di sconto, la registrazione viene utilizzata solo quando un codice di spese viene aggiunto a un'intestazione o una riga di un ordine fornitore. La funzionalità di sconto avanzata disponibile in Microsoft Dynamics 365 Supply Chain Management fornisce un maggiore controllo e automazione degli sconti. Per ulteriori informazioni, vedi [Sconti fornitore](../../supply-chain//procurement/vendor-rebates.md).

La tabella precedente mostra tre esempi tipici di tipi di registrazione che possono essere utilizzati per i codici di spese. Dovrebbe essere usata come linea guida e una selezione di esempi. Non fornisce un elenco completo di tutte le possibili combinazioni o tipi di registrazione che possono essere utilizzati.

Per ulteriori informazioni, vedi [Creare codici di spese](../accounts-receivable/create-charges-codes.md).
