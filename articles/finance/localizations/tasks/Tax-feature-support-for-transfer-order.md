---
title: Supporto della funzione fiscale per ordini di trasferimento
description: In questo argomento viene illustrato il nuovo supporto della funzione fiscale per gli ordini di trasferimento utilizzando il servizio di calcolo delle imposte.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920957"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Supporto della funzione fiscale per ordini di trasferimento

[!include [banner](../../includes/banner.md)]

In questo argomento vengono fornite informazioni sul calcolo delle imposte e sull'integrazione della registrazione negli ordini di trasferimento. Questa funzionalità consente di impostare il calcolo delle imposte e la registrazione negli ordini di trasferimento per i trasferimenti di scorte. Ai sensi della normativa sull'imposta sul valore aggiunto (IVA) dell'Unione europea (UE), i trasferimenti di scorte sono considerati fornitura intracomunitaria e acquisizioni intracomunitarie.

Per configurare e utilizzare questa funzionalità, è necessario completare tre passaggi principali:

1. **Configurazione RCS:** In Regulatory Configuration Service, imposta la funzione fiscale, i codici imposta e l'applicabilità dei codici imposta per la determinazione del codice imposta negli ordini di trasferimento.
2. **Configurazione Finance:** In Microsoft Dynamics 365 Finance, attiva la funzionalità **Imposta in ordine di trasferimento**, imposta i parametri del servizio fiscale per l'inventario e imposta i parametri fiscali di base.
3. **Configurazione inventario:** Imposta la configurazione dell'inventario per le transazioni degli ordini di trasferimento.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Impostare RCS per le transazioni di imposte e ordini di trasferimento

Segui questi passaggi per configurare l'imposta applicata in un ordine di trasferimento. Nell'esempio mostrato qui, l'ordine di trasferimento è dai Paesi Bassi al Belgio.

1. Nella pagina **Funzionalità fiscali**, nella scheda **Versioni** seleziona la versione bozza della funzionalità, quindi selezionare **Modifica**.

    ![Selezione di Modifica](../media/image1.png)

2. Nella pagina **Configurazione funzioni fiscali** nella scheda **Codici imposta** seleziona **Aggiungi** per creare nuovi codici imposta. Per questo esempio, vengono creati tre codici imposta: **NL-Exempt**, **BE-RC-21**, e **BE-RC+21**.

    - Quando un ordine di trasferimento viene spedito da un magazzino nei Paesi Bassi, il codice imposta olandese esente da IVA (**NL-Exempt**) viene applicato.
      
        Crea il codice imposta **NL-Exempt**.
        1. Seleziona **Aggiungi**, immetti **NL-Exempt** nel campo **Codice imposta**.
        2. Seleziona **Per importo netto** nel campo **Componente fiscale**.
        3. Selezionare **Salva**.
        4. Nella tabella **Tasso** seleziona **Aggiungi**.
        5. Imposta **Esente** su **Sì** nella sezione **Generale**.

        ![Codice imposta NL-Exempt](../media/image2.png)

    - Quando un ordine di trasferimento viene ricevuto in un magazzino in Belgio, il meccanismo di reverse charge viene applicato utilizzando i codici imposta **BE-RC-21** e **BE-RC+21**.
        
        Crea il codice imposta **BE-RC-21**.      
        1. Seleziona **Aggiungi**, immetti **BE-RC-21** nel campo **Codice imposta**.
        2. Seleziona **Per importo netto** nel campo **Componente fiscale**.
        3. Selezionare **Salva**.
        4. Nella tabella **Tasso** seleziona **Aggiungi**.
        5. Immetti **-21** nel campo **Aliquota imposta**.
        6. Imposta **Reverse Charge** su **Sì** nella sezione **Generale**.
        7. Selezionare **Salva**.

        ![Codice imposta BE-RC-21 per reverse charge](../media/image3.png)
        
        Crea il codice imposta **BE-RC+21**.
        1. Seleziona **Aggiungi**, immetti **BE-RC-21** nel campo **Codice imposta**.
        2. Seleziona **Per importo netto** nel campo **Componente fiscale**.
        3. Selezionare **Salva**.
        4. Nella tabella **Tasso** seleziona **Aggiungi**.
        5. Immetti **21** nel campo **Aliquota imposta**.
        6. Selezionare **Salva**.

        ![Codice imposta BE-RC+21 per reverse charge](../media/image4.png)

3. Definisci l'applicabilità dei codici imposta.

    1. Seleziona **Gestisci colonne** e quindi seleziona le colonne da utilizzare per creare la tabella di applicabilità.

        > [!NOTE]
        > Assicurati di aggiungere le colonne **Processo aziendale** e **Indicazioni fiscali** alla tabella. Entrambe le colonne sono essenziali per la funzionalità dell'imposta negli ordini di trasferimento.

    2. Aggiungi le regole di applicabilità. Non lasciare i campi **Codici imposta**, **Gruppo di imposte**, e **Gruppo di imposte articolo** vuoti.
        
        Aggiungi una nuova regola per la spedizione dell'ordine di trasferimento.
        1. Nella tabella **Regole di applicabilità** seleziona **Aggiungi**.
        2. Nel campo **Processo aziendale** seleziona **Inventario** per rendere la regola applicabile a un ordine di trasferimento.
        3. Nel campo **Spedisci da Paese/Regione** inserisci **NLD**.
        4. Nel campo **Spedisci a Paese/Regione** inserisci **BEL**.
        5. Nel campo **Direzione fiscale** seleziona **Output** per rendere la regola applicabile alla spedizione dell'ordine di trasferimento.
        6. Nel campo **Codici imposta** seleziona **NL-Exempt**.
        7. Nel campo **Gruppo di imposte** e **Gruppo di imposte articolo**, immetti la fascia IVA correlata e la fascia IVA articolo definite nel sistema Finance.
        
        Aggiungi un'altra regola per la ricezione dell'ordine di trasferimento.
        1. Nella tabella **Regole di applicabilità** seleziona **Aggiungi**.
        2. Nel campo **Processo aziendale** seleziona **Inventario** per rendere la regola applicabile a un ordine di trasferimento.
        3. Nel campo **Spedisci da Paese/Regione** inserisci **NLD**.
        4. Nel campo **Spedisci a Paese/Regione** inserisci **BEL**.
        5. Nel campo **Direzione fiscale** seleziona **Input** per rendere la regola applicabile alla ricezione dell'ordine di trasferimento.
        6. Nel campo **Codici imposta** seleziona **BE-RC+21** e **BE-RC-21**.
        7. Nel campo **Gruppo di imposte** e **Gruppo di imposte articolo**, immetti la fascia IVA correlata e la fascia IVA articolo definite nel sistema Finance.

        ![Regole di applicabilità](../media/image5.png)

4. Completa e pubblica la nuova versione della funzione fiscale.

    [![Modifica dello stato della nuova versione](../media/image6.png)](../media/image6.png)

## <a name="set-up-finance-for-transfer-order-transactions"></a>Impostare Finance per le transazioni di ordini di trasferimento

Per impostare le imposte per gli ordini di trasferimento, effettua i passaggi descritti di seguito.

1. In Finance, via a **Aree di lavoro** \> **Gestione funzionalità**.
2. Nell'elenco, trova e seleziona la funzionalità **Imposta in ordine di trasferimento**, quindi seleziona **Abilita ora** per attivarla.

    > [!IMPORTANT]
    > La funzionalità **Imposta in ordine di trasferimento** è completamente dipendente dal servizio fiscale. Pertanto, può essere attivata solo dopo aver installato il servizio fiscale.

    ![Funzionalità imposta in ordine di trasferimento](../media/image7.png)

3. Abilita il servizio fiscale e seleziona il processo aziendale **Inventario**.

    > [!IMPORTANT]
    > È necessario completare questo passaggio per ogni persona giuridica in Finance in cui si desidera rendere disponibili il servizio fiscale e la funzionalità per le imposte negli ordini di trasferimento.

    1. Vai a **Imposte** \> **Impostazioni** \> **Configurazione fiscale** \> **Configurazione del servizio fiscale**.
    2. Nel campo **Processo aziendale** seleziona **Inventario**.

    ![Impostazione del campo Processo aziendale](../media/image8.png)

4. Verificare che il meccanismo di reverse charge sia impostato. Vai a **Contabilità generale** \> **Impostazioni** \> **Parametri** e poi nella scheda **Reverse charge** verifica che l'opzione **Abilita reverse charge** sia impostata su **Sì**.

    ![Abilitare l'opzione di inversione contabile](../media/image9.png)

5. Verifica che i codici imposta, i gruppi di imposte, i gruppi di imposte articoli e i numeri di registrazione IVA correlati siano stati impostati in Finance in base alle indicazioni del servizio fiscale.
6. Crea un conto di transito provvisorio. Questo passaggio è necessario solo quando l'imposta applicata a un ordine di trasferimento non è applicabile a un meccanismo di esenzione fiscale o di reverse charge.

    1. Vai a **Imposta** \> **Impostazioni** \> **IVA** \> **Gruppi registrazione contabile**.
    2. Nel campo **Transito provvisorio** seleziona un conto CoGe.

    ![Selezione di un conto di transito provvisorio](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Impostare l'inventario di base per le transazioni di ordini di trasferimento

Segui questi passaggi per impostare l'inventario di base per abilitare le transazioni degli ordini di trasferimento.

1. Crea siti di partenza e destinazione della spedizione per i tuoi magazzini in diversi paesi o regioni e aggiungi l'indirizzo principale per ogni sito.

    1. Vai a **Gestione magazzino** \> **Impostazione** \> **Magazzino** \> **Siti**.
    2. Seleziona **Nuovo** per creare il sito che in seguito assegnerai a un magazzino.
    3. Ripeti il passaggio 2 per tutti gli altri siti che è necessario creare.

    > [!NOTE]
    > Uno dei siti che crei deve essere denominato **Transito**. Nelle fasi successive di questa procedura, assegnerai questo sito al magazzino di transito, in modo che i giustificativi di inventario relativi alle imposte possano essere registrati nelle transazioni di "spedizione" e "ricezione" per gli ordini di trasferimento. L'indirizzo del sito di transito è irrilevante per il calcolo delle imposte. Pertanto, non è possibile non specificare tale valore.

    ![Impostazione dei siti](../media/image11.png)

2. Crea magazzini di partenza, transito e consegna. Qualsiasi informazione sull'indirizzo conservata in un magazzino sovrascriverà l'indirizzo del sito durante il calcolo delle imposte.

    1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Magazzino** \> **Magazzini**.
    2. Seleziona **Nuovo** per creare il magazzino e assegnarlo al sito corrispondente.
    3. Ripeti il passaggio 2 per creare un magazzino per ogni sito come richiesto.

    ![Impostazione dei magazzini](../media/image12.png)

    > [!NOTE]
    > Per un magazzino di partenza, è necessario selezionare un magazzino di transito nel campo **Magazzino di transito** per le transazioni dell'ordine di trasferimento.
    >
    > ![Selezione di un magazzino di transito](../media/image13.png)

3. Verifica che la configurazione di registrazione inventario sia configurata per le transazioni degli ordini di trasferimento.

    1. Andare a **Gestione scorte**\>**Impostazioni**\>**Registrazione**\>**Registrazione**.
    2. Nella scheda **Inventario** verifica che sia impostato un conto contabile per le registrazioni **Uscita inventario** e **Entrata inventario**.

        ![Impostazione dell'uscita di scorte e della registrazione delle entrate scorte](../media/image14.png)

    3. Verifica che sia impostato un conto contabile per la registrazione **Contabilità fornitori tra unità**.

        ![Impostazione della registrazione contabilità fornitori tra unità](../media/image15.png)

    4. Verifica che sia impostato un conto contabile per la registrazione **Contabilità clienti tra unità**.

        ![Impostazione della registrazione contabilità clienti tra unità](../media/image16.png)
