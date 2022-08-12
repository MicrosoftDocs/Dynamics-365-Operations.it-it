---
title: Supporto della funzione fiscale per ordini di trasferimento
description: In questo articolo viene illustrato il nuovo supporto della funzione fiscale per gli ordini di trasferimento utilizzando il servizio di calcolo delle imposte.
author: Kai-Cloud
ms.date: 10/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b611abb2d68d93178d0c26ba40b22f1b8d26b191
ms.sourcegitcommit: 6d9fcb52d723ac5022a3002e0ced8e7b56e9bc2a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9203111"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Supporto della funzione fiscale per ordini di trasferimento

[!include [banner](../../includes/banner.md)]

In questo articolo vengono fornite informazioni sul calcolo delle imposte e sull'integrazione della registrazione negli ordini di trasferimento. Questa funzionalità consente di impostare il calcolo delle imposte e la registrazione negli ordini di trasferimento per i trasferimenti di scorte. Ai sensi della normativa sull'imposta sul valore aggiunto (IVA) dell'Unione europea (UE), i trasferimenti di scorte sono considerati fornitura intracomunitaria e acquisizioni intracomunitarie.

Per configurare e utilizzare questa funzionalità, è necessario completare tre passaggi principali:

1. **Configurazione RCS:** In Regulatory Configuration Service, imposta la funzione fiscale, i codici imposta e l'applicabilità dei codici imposta per la determinazione del codice imposta negli ordini di trasferimento.
2. **Configurazione di Dynamics 365 Finance**: In Finance, attiva la funzionalità **Imposta in ordine di trasferimento**, imposta i parametri del servizio di calcolo imposte per l'inventario e imposta i parametri fiscali di base.
3. **Configurazione inventario:** Imposta la configurazione dell'inventario per le transazioni degli ordini di trasferimento.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Impostare RCS per le transazioni di imposte e ordini di trasferimento

Segui questi passaggi per configurare l'imposta applicata in un ordine di trasferimento. Nell'esempio mostrato qui, l'ordine di trasferimento è dai Paesi Bassi al Belgio.

1. Nella pagina **Funzionalità fiscali**, nella scheda **Versioni** seleziona la versione bozza della funzionalità, quindi selezionare **Modifica**.

2. Nella pagina **Configurazione funzioni fiscali** nella scheda **Codici imposta** seleziona **Aggiungi** per creare nuovi codici imposta. Per questo esempio, vengono creati tre codici imposta: **NL-Exempt**, **BE-RC-21**, e **BE-RC+21**.

    - Quando un ordine di trasferimento viene spedito da un magazzino nei Paesi Bassi, il codice imposta olandese esente da IVA (**NL-Exempt**) viene applicato.
      
        Crea il codice imposta **NL-Exempt**.
        1. Seleziona **Aggiungi**, immetti **NL-Exempt** nel campo **Codice imposta**.
        2. Seleziona **Per importo netto** nel campo **Componente fiscale**.
        3. Selezionare **Salva**.
        4. Nella tabella **Tasso** seleziona **Aggiungi**.
        5. Imposta **Esente** su **Sì** nella sezione **Generale**.
        6. Nel campo **Codice esenzione** immetti **EC**.

    - Quando un ordine di trasferimento viene ricevuto in un magazzino in Belgio, il meccanismo di reverse charge viene applicato utilizzando i codici imposta **BE-RC-21** e **BE-RC+21**.
        
        Crea il codice imposta **BE-RC-21**.      
        1. Seleziona **Aggiungi**, immetti **BE-RC-21** nel campo **Codice imposta**.
        2. Seleziona **Per importo netto** nel campo **Componente fiscale**.
        3. Selezionare **Salva**.
        4. Nella tabella **Tasso** seleziona **Aggiungi**.
        5. Immetti **-21** nel campo **Aliquota imposta**.
        6. Imposta **Reverse Charge** su **Sì** nella sezione **Generale**.
        7. Selezionare **Salva**.
        
        Crea il codice imposta **BE-RC+21**.
        1. Seleziona **Aggiungi**, immetti **BE-RC-21** nel campo **Codice imposta**.
        2. Seleziona **Per importo netto** nel campo **Componente fiscale**.
        3. Selezionare **Salva**.
        4. Nella tabella **Tasso** seleziona **Aggiungi**.
        5. Immetti **21** nel campo **Aliquota imposta**.
        6. Selezionare **Salva**.

3. Definisci la fascia IVA.
    1. Seleziona **Gestisci colonne**, quindi seleziona il campo riga **Fascia IVA**.
    2. Seleziona **->** e quindi seleziona **OK**.
    3. Seleziona **Aggiungi** per aggiungere una fascia IVA.
    4. Nella colonna **Fascia IVA** immetti **AR-EU** e poi seleziona il codice imposta **NL-Exempt**.
    5. Seleziona **Aggiungi** per aggiungere una fascia IVA.
    6. Nella colonna **Fascia IVA** immetti **RC-VAT** e poi seleziona i codici imposta **BE-RC-21** e **BE-RC+21**.
4. Definisci la fascia IVA dell'articolo.
    1. Seleziona **Gestisci colonne**, quindi seleziona il campo riga **Fascia IVA articolo**.
    2. Seleziona **->** e quindi seleziona **OK**.
    3. Seleziona **Aggiungi** per aggiungere una fascia IVA dell'articolo.
    4. Immetti **COMPLETO** nella colonna **Fascia IVA articolo**. Seleziona i codici imposta **BE-RC-21**, **BE-RC+21**, e **NL-Exempt**.
5. Definisci l'applicabilità della fascia IVA.

    1. Seleziona **Gestisci colonne** e quindi seleziona le colonne da utilizzare per creare la tabella di applicabilità.

        > [!NOTE]
        > Assicurati di aggiungere le colonne **Processo aziendale** e **Indicazioni fiscali** alla tabella. Entrambe le colonne sono essenziali per la funzionalità dell'imposta negli ordini di trasferimento.

    2. Aggiungi le regole di applicabilità. Non lasciare vuoto il campo **Fascia IVA**.
        
        Aggiungi una nuova regola per la spedizione dell'ordine di trasferimento.
        1. Nella tabella **Regole di applicabilità** seleziona **Aggiungi**.
        2. Nel campo **Processo aziendale** seleziona **Inventario** per rendere la regola applicabile a un ordine di trasferimento.
        3. Nel campo **Spedisci da Paese/Regione** inserisci **NLD**.
        4. Nel campo **Spedisci a Paese/Regione** inserisci **BEL**.
        5. Nel campo **Direzione fiscale** seleziona **Output** per rendere la regola applicabile alla spedizione dell'ordine di trasferimento.
        6. Nel campo **Fascia IVA** seleziona **AR-EU**.
        
        Aggiungi un'altra regola per la ricezione dell'ordine di trasferimento.
        
        1. Nella tabella **Regole di applicabilità** seleziona **Aggiungi**.
        2. Nel campo **Processo aziendale** seleziona **Inventario** per rendere la regola applicabile a un ordine di trasferimento.
        3. Nel campo **Spedisci da Paese/Regione** inserisci **NLD**.
        4. Nel campo **Spedisci a Paese/Regione** inserisci **BEL**.
        5. Nel campo **Direzione fiscale** seleziona **Input** per rendere la regola applicabile alla ricezione dell'ordine di trasferimento.
        6. Nel campo **Fascia IVA** seleziona **RC-VAT**.

6. Definisci l'applicabilità della fascia IVA dell'articolo.

    1. Seleziona **Gestisci colonne** e quindi seleziona le colonne da utilizzare per creare la tabella di applicabilità.
    2. Aggiungi le regole di applicabilità.
        
       > [!NOTE]
       > Se la fascia IVA articolo predefinita nelle righe del documento imponibile è già corretta, lascia vuota questa matrice. 
        
        Aggiungi una nuova regola per la spedizione dell'ordine di trasferimento e il ricevimento.
        1. Nella pagina **Regole di applicabilità** seleziona **Aggiungi**.
        2. Nel campo **Processo aziendale** seleziona **Inventario** per rendere la regola applicabile all'ordine di trasferimento.
        3. Nel campo **Fascia IVA articolo** seleziona **COMPLETO**.
7. Completa e pubblica la nuova versione della funzione fiscale.


## <a name="set-up-finance-for-transfer-order-transactions"></a>Impostare Finance per le transazioni di ordini di trasferimento

Per impostare le imposte per gli ordini di trasferimento, effettua i passaggi descritti di seguito.

1. In Finance, vai a **Aree di lavoro** > **Gestione funzionalità**.
2. Nell'elenco, trova e seleziona la funzionalità **Imposta in ordine di trasferimento**, quindi seleziona **Abilita ora** per attivarla.

    > [!IMPORTANT]
    > La funzionalità **Imposta in ordine di trasferimento** è completamente dipendente dal servizio di calcolo imposte. Pertanto, può essere attivata solo dopo aver installato il servizio di calcolo imposte.

    ![Funzionalità imposta in ordine di trasferimento.](../media/image7.png)

3. Abilita il servizio calcolo imposte e seleziona il processo aziendale **Inventario**.

    > [!IMPORTANT]
    > È necessario completare questo passaggio per ogni persona giuridica in Finance in cui si desidera rendere disponibili il servizio calcolo imposte e la funzionalità per le imposte negli ordini di trasferimento.

    1. Vai a **Imposta** > **Impostazioni** > **Configurazione imposta** > **Parametri calcolo imposta**.
    2. Nel campo **Processo aziendale** seleziona **Inventario**.

4. Verificare che il meccanismo di reverse charge sia impostato. Vai a **Contabilità generale** \> **Impostazioni** \> **Parametri** e poi nella scheda **Reverse charge** verifica che l'opzione **Abilita reverse charge** sia impostata su **Sì**.

    ![Abilitare l'opzione di inversione contabile.](../media/image9.png)

5. Verifica che i codici imposta, i gruppi di imposte, i gruppi di imposte articoli e i numeri di registrazione IVA correlati siano stati impostati in Finance in base alle indicazioni del servizio di calcolo imposte.
6. Crea un conto di transito provvisorio. Questo passaggio è necessario solo quando l'imposta applicata a un ordine di trasferimento non è applicabile a un meccanismo di esenzione fiscale o di reverse charge.

    1. Vai a **Imposta** > **Impostazioni** > **IVA** > **Gruppi registrazione contabile**.
    2. Nel campo **Transito provvisorio** seleziona un conto CoGe.

       ![Selezione di un conto di transito provvisorio.](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Impostare l'inventario di base per le transazioni di ordini di trasferimento

Segui questi passaggi per impostare l'inventario di base per abilitare le transazioni degli ordini di trasferimento.

1. Crea siti di partenza e destinazione della spedizione per i tuoi magazzini in diversi paesi o regioni e aggiungi l'indirizzo principale per ogni sito.

    1. Vai a **Gestione magazzino** > **Impostazione** > **Magazzino** > **Siti**.
    2. Seleziona **Nuovo** per creare il sito che in seguito assegnerai a un magazzino.
    3. Ripeti il passaggio 2 per tutti gli altri siti che è necessario creare.

    > [!NOTE]
    > Uno dei siti che crei deve essere denominato **Transito**. Nelle fasi successive di questa procedura, assegnerai questo sito al magazzino di transito, in modo che i giustificativi di inventario relativi alle imposte possano essere registrati nelle transazioni di "spedizione" e "ricezione" per gli ordini di trasferimento. L'indirizzo del sito di transito è irrilevante per il calcolo delle imposte. Pertanto, non è possibile non specificare tale valore.

    ![Impostazione dei siti.](../media/image11.png)

2. Crea magazzini di partenza, transito e consegna. Qualsiasi informazione sull'indirizzo conservata in un magazzino sovrascriverà l'indirizzo del sito durante il calcolo delle imposte.

    1. Vai a **Gestione magazzino** > **Impostazioni** > **Magazzino** > **Magazzini**.
    2. Seleziona **Nuovo** per creare il magazzino e assegnarlo al sito corrispondente.
    3. Ripeti il passaggio 2 per creare un magazzino per ogni sito come richiesto.

       ![Impostazione dei magazzini.](../media/image12.png)

    > [!NOTE]
    > Per un magazzino di partenza, è necessario selezionare un magazzino di transito nel campo **Magazzino di transito** per le transazioni dell'ordine di trasferimento.
    >
    > ![Selezione di un magazzino di transito.](../media/image13.png)

3. Verifica che la configurazione di registrazione inventario sia configurata per le transazioni degli ordini di trasferimento.

    1. Vai a **Gestione scorte** > **Impostazioni** > **Registrazione** > **Registrazione**.
    2. Nella scheda **Inventario** verifica che sia impostato un conto contabile per le registrazioni **Uscita inventario** e **Entrata inventario**.

        ![Impostazione dell'uscita di scorte e della registrazione delle entrate scorte.](../media/image14.png)

    3. Verifica che sia impostato un conto contabile per la registrazione **Contabilità fornitori tra unità**.

        ![Impostazione della registrazione contabilità fornitori tra unità.](../media/image15.png)

    4. Verifica che sia impostato un conto contabile per la registrazione **Contabilità clienti tra unità**.

        ![Impostazione della registrazione contabilità clienti tra unità.](../media/image16.png)
        
        
  [!INCLUDE[footer-include](../../../includes/footer-banner.md)]
