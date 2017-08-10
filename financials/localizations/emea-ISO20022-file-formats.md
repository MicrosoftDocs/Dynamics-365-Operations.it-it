---
title: Importazione di file ISO20022
description: In questo argomento viene descritto come importare file di pagamento dei formati camt.054 e pain.002 ISO 20022 in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
author: neserovleo
manager: AnnBe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Italy, Latvia, Lithuania, Norway, Poland, Spain, Sweden, Switzerland, United Kingdom
ms.author: v-lenest
ms.search.validFrom: 2017-06-01T00:00:00.000Z
ms.dyn365.ops.version: Enterprise edition, July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 48e280bf0a6c5db237bd389fe448c9d698d3ae12
ms.openlocfilehash: acf6ed5f503d77f372d802a51a71cec062c2b24b
ms.contentlocale: it-it
ms.lasthandoff: 07/25/2017

---

# <a name="import-iso20022-files"></a>Importare file ISO20022

## <a name="overview"></a>Panoramica
È possibile importare file di pagamento con i seguenti formati:

 - **Avviso di accredito ISO20022 camt.054**: importare pagamenti ricevuti da un file in questo formato nel giornale di registrazione pagamenti del cliente.
 - **Reso con stato ISO20022 pain.002** e **Avviso di addebito ISO20022 camt.054**: importare file di rimborso in questi formati nel giornale di registrazione trasferimenti pagamenti di contabilità fornitori.

## <a name="prerequisites-for-importing-the-camt054-credit-advice-file"></a>Prerequisiti per importare il file di avviso di accredito camt.054
È necessario completare i seguenti prerequisiti per importare i messaggi di notifica della banca nel formato camt.054.001.002 nel giornale di registrazione pagamenti del cliente.

1. Importare la configurazione di reporting elettronica (ER) **ISO20022 camt.054** da Microsoft Dynamics Lifecycle Services (LCS). Quindi, nella pagina **Metodo di pagamento cliente**, nel campo **Configurazione formato di importazione**, selezionare la configurazione. Per ulteriori informazioni, vedere [Formati di file per i metodi di pagamento](emea-select-file-formats-for-the-method-of-payments.md).
2. Nella pagina **Tutti i clienti** immettere un nome e un numero di organizzazione per ogni cliente.
3. Nella pagina **Conto bancario cliente** impostare un record di conto bancario del cliente immettendo le seguenti informazioni: IBAN o numero di conto bancario e codice SWIFT o numero di registrazione.
4. Nella pagina **Conti bancari** impostare i conti bancari della persona giuridica immettendo le seguenti informazioni: IBAN o numero di conto bancario, codice SWIFT o numero di registrazione, valuta e indirizzo.

    > [!NOTE]
    > Se si prevede di utilizzare la riconciliazione degli estratti conto avanzata, nella scheda dettaglio **Riconciliazione** impostare l'opzione **Riconciliazione estratti conto avanzata** su **Sì**. Se si prevede di riconciliare i pagamenti importati non registrati, impostare l'opzione **Utilizza rendiconti bancari come conferma di pagamenti elettronici** su **Sì**.

5. Facoltativo: nella pagina **Mapping dei codici transazione** impostare il mapping tra codici di transazione bancaria nel file e tipi di transazioni bancarie.
6. Se il file contiene spese di transazione che si desidera registrare insieme al pagamento ricevuto, creare una commissione di pagamento nella pagina **Commissione pagamento cliente**. Quindi, nella pagina **Metodi di pagamento** associare la commissione di pagamento al conto bancario nell'impostazione della commissione di pagamento.
7. Se i pagamenti PVR verranno importati e conterranno i riferimenti ISR (applicabili alle persone giuridiche in Svizzera), completare la seguente configurazione:

    - Nel campo **Pagamenti clienti, lunghezza conto** immettere la lunghezza del codice cliente utilizzato nei riferimenti ISR o per l'identificazione automatica del cliente.
    - Verificare che il numero di fattura e il numero cliente (sequenze numeriche) contengano solo cifre. Non devono contenere altri caratteri. Il numero di fattura non deve avere zeri iniziali.
    - Immettere i numeri ESR, BESR e di registrazione del conto bancario della persona giuridica. Per ulteriori informazioni, vedere [funzionalità PVR precedenti](emea-che-esr-customer-payments-import.md), poiché impostazioni simili sono necessarie.
    
## <a name="import-the-camt054-credit-advice-file-into-the-customer-payment-journal"></a>Importare il file di avviso di accredito camt.054 nel giornale di registrazione pagamenti cliente
1. Nella pagina **Righe giornale di registrazione pagamenti cliente** fare clic su **Funzioni** > **Importa pagamenti**.
2. Selezionare il metodo di pagamento con le impostazioni richieste per il formato ISO20022 camt.054.
3. Specificare i parametri necessari e il percorso del file, quindi fare clic su **OK**.

Il file viene importato.

## <a name="prerequisites-for-importing-files-in-the-pain002-status-return-and-camt054-debit-advice-formats-into-the-ap-payment-transfer-journal"></a>Prerequisiti per l'importazione di file nel reso con stato pain.002 e di formati di avviso di addebito camt.054 nel giornale di registrazione trasferimenti pagamenti di contabilità fornitori.
È necessario completare i seguenti prerequisiti per importare messaggi bancari nei seguenti formati ISO20022 nella pagina **Trasferimento pagamenti fornitore** : messaggi di reso con stato pain.002.001.003 e avviso di addebito camt.054.001.002.

1. Importare le configurazioni ER **ISO20022 camt.054** e **ISO20022 pain.002** da LCS.
2. Nella pagina **Metodo di pagamento fornitore**, nei campi **Configurazione formato risposta** e **Configurazione secondaria formato risposta**, selezionare le configurazioni ER importate. Sarà necessario attivare il formato di risposta elettronica generica per il metodo di pagamento selezionato.
3. Nella pagina **Mapping dello stato formato risposta** impostare il mapping dei codici stato tra gli stati pain.002 e gli stati del giornale di registrazione pagamenti fornitore.

    Di seguito è riportato un esempio di impostazione dello stato.

    Stato di reso | Stato pagamenti
    --------------|---------------
    RJCT          | Rifiutato
    ACCP          | Accettato
    ACSP          | Ricevuti

4. Nella pagina **Codici di errore formato risposta** impostare i codici di errore pain.002 e le descrizioni in conformità ai codici motivo esterni dello stato ISO20022.

    Di seguito è riportato un esempio della parte dell'impostazione di un codice di errore.

    Codice | Nome
    -----|-----
    AC01 | IncorrectAccountNumber
    AC02 | InvalidDebtorAccountNumber
    AC03 | InvalidCreditorAccountNumber
    AC04 | ClosedAccountNumber
    AC05 | ClosedDebtorAccountNumber
    AC06 | BlockedAccount

5. Se il file camt.054 contiene spese di transazione che si desidera registrare insieme al pagamento ricevuto, creare una commissione di pagamento nella pagina **Commissione pagamento fornitore**. Quindi, nella pagina **Metodi di pagamento** associare la commissione di pagamento al conto bancario nell'impostazione della commissione di pagamento.

## <a name="import-the-pain002-status-return-or-camt054-debit-advice-files-into-the-vendor-payment-journal"></a>Importare i file con avviso di addebito camt.054 o di reso con stato pain.002 nel giornale di registrazione pagamenti fornitore
1. Aprire la pagina **Trasferimenti di pagamento** dal menu della Contabilità fornitori.
2. Nella pagina **Trasferimenti di pagamento** fare clic su **Archivio resi - Fornitore**.
3. Selezionare il metodo di pagamento con le impostazioni richieste per i file ISO20022, quindi fare clic su **OK**.
4. Selezionare il formato di file che si prevede di importare e fare clic su **OK**.
5. Specificare i parametri necessari e il percorso del file, quindi fare clic su **OK**.

Se si importa il file pain.002, lo stato delle righe di pagamento fornitore viene aggiornato in base alle informazioni incluse nel file importato.

Se si importa il file camt.054, è necessario specificare i parametri aggiuntivi seguenti:

- **ID commissione**: immettere l'ID della commissione che definirà le nuove righe della commissione di pagamento, che verranno create nella riga del giornale di registrazione pagamenti fornitore se l'importo dell'addebito è presente nel file camt.054.
- **Nuovo nome giornale di registrazione** e **Descrizione nuovo giornale di registrazione**: immettere il nome e la descrizione del giornale di registrazione nel quale verranno trasferite le transazioni elaborate. Dopo il trasferimento i nuovi numeri dei giustificativi devono essere assegnati nel nuovo giornale di registrazione.
- **Importa transazioni di addebito diretto**: impostare questa opzione su **Sì** se gli addebiti diretti in uscita devono essere importati nel giornale di registrazione pagamenti fornitore.
- **Nome giornale di registrazione**: definire un nuovo nome di giornale di registrazione per le transazioni di addebito diretto importate.
- **Liquida transazioni**: impostare questa opzione su **Sì** se i pagamenti fornitore importati devono essere liquidati con fatture presenti nel sistema.

È possibile visualizzare le informazioni importate nella pagina **Trasferimenti di pagamento**. 
