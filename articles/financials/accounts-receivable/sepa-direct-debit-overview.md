---
title: Panoramica di addebito diretto SEPA
description: "SEPA (Single Euro Payments Area) viene impostata dalla Commissione Europea e determina che tutti i pagamenti elettronici vengono considerati nazionali, indipendentemente dal paese in cui si trovano i singoli individui, le aziende o l'organizzazione e la banca. Non c'è differenza tra i pagamenti nazionali e quelli transfrontalieri. SEPA include i 28 stati membri dell'Unione Europea (UE) oltre all'Islanda, il Liechtenstein, la Norvegia, la Svizzera, Monaco e San Marino. SEPA consente di formare un singolo mercato per le transazioni di pagamento all'interno dell'Area Economica Europea. Infine, SEPA prevede di ridurre il numero dei formati di pagamento con cui lavorano le banche, le aziende e i singoli individui."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 11144
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fb55f4b0b06019891c2e490eda837cfad882e6db
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="sepa-direct-debit-overview"></a>Panoramica di addebito diretto SEPA

[!include [banner](../includes/banner.md)]

SEPA (Single Euro Payments Area) viene impostata dalla Commissione Europea e determina che tutti i pagamenti elettronici vengono considerati nazionali, indipendentemente dal paese in cui si trovano i singoli individui, le aziende o l'organizzazione e la banca. Non c'è differenza tra i pagamenti nazionali e quelli transfrontalieri. SEPA include i 28 stati membri dell'Unione Europea (UE) oltre all'Islanda, il Liechtenstein, la Norvegia, la Svizzera, Monaco e San Marino. SEPA consente di formare un singolo mercato per le transazioni di pagamento all'interno dell'Area Economica Europea. Infine, SEPA prevede di ridurre il numero dei formati di pagamento con cui lavorano le banche, le aziende e i singoli individui.   

<a name="what-is-the-goal-of-sepa-direct-debits"></a>Qual è l'obiettivo degli addebiti diretti SEPA?
---------------------------------------

Un addebito diretto SEPA consente al creditore di prelevare denaro dal conto corrente bancario del cliente, ammesso che il cliente abbia concesso un mandato firmato al creditore. Il cliente firma un mandato che autorizza il creditore a riscuotere un pagamento e istruisce la banca del cliente a effettuare il pagamento. 

L'addebito diretto SEPA crea, per la prima volta, uno strumento di pagamento che può essere utilizzato sia per gli addebiti diretti nazionali che transfrontalieri di euro attraverso i 32 paesi SEPA. 

Sono disponibili due combinazioni: la combinazione principale di addebito diretto SEPA e la combinazione di addebito diretto B2B SEPA. Entrambe le combinazioni utilizzano lo stesso formato di file.

## <a name="what-is-the-core-direct-debit-scheme"></a>Cos'è la combinazione principale di addebito diretto?
La combinazione principale di addebito diretto SEPA è la combinazione di base. Dispone dei seguenti attributi:
-   Il trasferimento di fondi è in euro (anche se i conti bancari possono utilizzare i fondi in altre valute).
-   Il cliente e il creditore devono disporre di un conto in un istituto di credito che si trova in SEPA.
-   Il cliente deve concedere un mandato firmato al creditore.
-   I mandati scadono 36 mesi dopo l'ultima riscossione iniziata.
-   Il creditore deve archiviare i mandati a condizione che il mandato sia valido e per almeno 14 mesi dopo l'ultima riscossione.
-   La combinazione può essere utilizzata per le riscossioni di addebito diretto ricorrenti o singole (una volta).
-   I clienti hanno il tacito diritto di ricevere un rimborso fino a otto settimane successive all'addebito sul conto.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>Cos'è la combinazione di addebito diretto B2B SEPA?
La combinazione di addebito diretto B2B SEPA viene applicata alle transazioni e alle compilazioni nella combinazione principale di addebito diretto SEPA. Le differenze principali sono:
-   La combinazione di addebito diretto B2B SEPA non è consentita quando il cliente è un individuo privato (utente).
-   Il cliente non è autorizzato a ottenere un rimborso di una transazione autorizzata.
-   Le banche del cliente devono verificare che la riscossione sia autorizzata verificando le informazioni di mandato. Viene richiesto alle banche e ai clienti di accordarsi sulla verifica che verrà eseguita per ogni addebito diretto.
-   La combinazione offre una sequenza temporale più breve per la presentazione di addebiti diretti e riduce il periodo di reso.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>È possibile utilizzare lo schema COR1 per i metadati di addebito diretto?
Sì. È possibile utilizzare la combinazione COR1 per i mandati di addebito diretto SEPA in Austria, in Belgio, Germania, in Francia, Italia, in Spagna e nei Paesi Bassi. Lo schema fornisce un periodo di notifica preliminare più breve per la raccolta di addebito diretto del creditore.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>Cosa sono i numeri IBAN e BIC?
I codici IBAN (International Bank Account Number) e BIC (Bank Identifier Code) sono utilizzati per identificare qualsiasi conto in 32 paesi SEPA. Immettere il codice BIC nel campo Codice SWIFT e l'IBAN nel campo IBAN. Entrambi i campi si trovano nella FastTab Identificazione aggiuntiva nella scheda Dettaglio del conto bancario nella pagina dei conti bancari. Questa opzione è vera per il conto bancario del creditore e del cliente.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>Dove si immettono gli identificatori del creditore (ID addebito diretto)?
In SEPA, ogni creditore viene identificato da un identificatore univoco del creditore. Questo identificatore consente al cliente e alla banca di filtrare tutti gli addebiti diretti e quindi di elaborare o rifiutare l'addebito diretto in base alle istruzioni del cliente. I creditori devono richiedere questo identificatore tramite la propria banca. Immettere questo identificatore nel campo ID addebito diretto per il conto bancario della persona giuridica.

## <a name="what-are-mandates"></a>Cosa sono i mandati?
Il cliente firma un mandato che autorizza il creditore a riscuotere un pagamento e istruisce la banca del cliente a effettuare il pagamento. Il cliente può emettere il mandato in forma cartacea o elettronica. Per impostazione predefinita, il mandato scade 36 mesi dopo aver inizializzato l'ultimo addebito diretto.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>Dove è necessario specificare il formato di file di addebito diretto SEPA (ISO 20022)?
I formati dati SEPA si basano sugli standard di messaggio ISO 20022. È necessario selezionare la casella di controllo Report elettronici generici e il formato di addebito diretto SEPA come configurazione del formato di esportazione quando si configurano i metodi di pagamento per la contabilità clienti. Utilizzare questo metodo di pagamento quando si genera un file di pagamento in un giornale di registrazione pagamenti del cliente.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>Nei formati di file posso generare i file di pagamento in addebito diretto SEPA?
L'utente può generare file di pagamento elettronico per addebito diretto SEPA nei seguenti formati:
-   Addebito diretto SEPA nel formato di file XML PAIN.008.001.02 per Belgio, Germania, Spagna, Francia, Italia e Paesi Bassi.
-   File di pagamento in addebito diretto SEPA nel formato di file XML PAIN.008.001.02 per l'Austria e nel formato di file XML PAIN.008.003.02 per la Germania.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>Come funzionano i rimborsi e i resi con gli addebiti diretti SEPA?
In entrambe le combinazioni di addebito diretto SEPA, i clienti hanno determinati diritti sui rimborsi. Al cliente è consentito di richiamare tutte le transazioni autorizzate durante un periodo di otto giorni successivi alla data di scadenza, senza dover fornire un motivo. Nel caso delle transazioni non autorizzate, il periodo è esteso a 13 mesi dopo la data di scadenza. Gli storni di tutti i pagamenti effettuati vengono eseguiti manualmente tramite il pulsante Annulla pagamento nella pagina Transazioni cliente.






