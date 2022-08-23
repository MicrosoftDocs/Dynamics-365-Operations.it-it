---
title: Plafond fiscale
description: Questo articolo spiega come impostare e lavorare con il plafond fiscale, un processo di esenzione fiscale.
author: mrolecki
ms.date: 02/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: mrolecki
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.9
ms.search.form: ''
ms.openlocfilehash: 63358116e12e0b0423ce0c8f48526ac0e7651acb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292270"
---
# <a name="tax-plafond"></a>Plafond fiscale

[!include [banner](../includes/banner.md)]

Il plafond fiscale è un processo di esenzione fiscale disponibile per le aziende, chiamato *esportatore abituale*, di acquistare e importare beni e servizi senza pagare l'IVA, entro un valore limitato delle loro vendite all'estero nel periodo precedente. Una società è una *esportatore abituale* se, durante l'anno precedente, il 10 percento del suo valore dei ricavi proveniva dalla vendita in un paese straniero. L'importo iniziale del plafond e le sue date di validità sono stabiliti all'inizio del periodo. La società può acquistare senza pagare l'IVA purché il valore degli acquisti sia inferiore all'importo iniziale del plafond.

Questo articolo descrive come completare queste attività:

- Configurare il sistema affinché utilizzi la funzionalità **Plafond fiscale**.
- Lavora con lettere di intenti e plafond fiscali.
- Segnala pagamenti fiscali che includono informazioni sul plafond fiscale.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità**, abilita la funzionalità **Plafond fiscale**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- È previsto un periodo di liquidazione IVA (**Imposta** > **Imposte indirette** > **IVA** > **Periodi liquidazione IVA**) per il periodo in cui si prevede di creare un plafond fiscale e lettere di intenti e di registrare documenti fiscali con riferimento alle lettere di intenti.

## <a name="set-up-parameters"></a>Imposta parametri

### <a name="set-up-accounts-payable-parameters"></a>Impostazione dei parametri di Contabilità fornitori

1. Vai a **Contabilità fornitori** \> **Impostazioni** \> **Parametri contabilità fornitori**.
2. Nella scheda **Sequenze numeriche**, specifica le sequenze numeriche per i seguenti riferimenti:

    - Numero plafond
    - Numero lettera d'intento

3. Nella scheda **Lettere di intenti - Modello telematico** nel campo **Mappatura del formato del modello di lettera di intenti**, specificare il riferimento alla configurazione **Modello telematico lettera di intenti**.

    ![Campo di mappatura del formato del modello di lettera di intenti.](media/emea-ita-exil-plafond-model.jpg)

    > [!NOTE]
    > La configurazione deve essere importata utilizzando il report elettronico (ER). Per ulteriori istruzioni su come scaricare le configurazioni dei report elettronici, vedi [Scarica le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

4. Nella scheda **Contabilità generale e IVA**, nella Scheda dettaglio **IVA**, sezione **Plafond**, imposta i campi **Gruppo plafond fiscale** e **Data plafond predefinita**.

    ![Campi nella sezione Plafond.](media/emea-ita-exil-plafond-group.jpg)

### <a name="set-up-general-ledger-parameters"></a>Impostazione dei parametri di Contabilità generale

1. Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.
2. Nella scheda **Sequenze numeriche**, specificare la sequenza numerica per il riferimento **ID modello telematico lettera di intenti**.

### <a name="set-up-sales-tax-codes"></a>Imposta i codici IVA

1. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.
2. Nella sezione Scheda dettaglio **Generale**, nella sezione **Fatturazione**, imposta l'opzione **Invia lettere di intento** su **Sì**.

    ![Influisce sull'opzione lettere di intenti.](media/emea-ita-exil-intent-tax-setup.jpg)

## <a name="create-tax-plafond"></a>Crea plafond fiscale

Prima di iniziare a creare un nuovo plafond fiscale, verificare che sia presente un periodo di liquidazione IVA per il periodo in cui si prevede di creare un plafond fiscale e lettere di intenti e di registrare documenti fiscali con riferimento alle lettere di intenti.

Per registrare un nuovo plafond fiscale, attieniti alla seguente procedura.

1. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Plafond fiscale**.
2. Nel riquadro azioni, seleziona **Funzioni** \> **Crea nuovo** e inserisci le informazioni sul plafond fiscale.

   Nella seguente tabella vengono descritti i vari campi.

    | Nome campo                             | Descrizione |
    |----------------------------------------|-------------|
    | Numero plafond                         | Il numero del plafond fiscale. Questo valore viene inserito automaticamente in base alla sequenza numerica specificata per il riferimento **Numero plafond** nella pagina **Parametri contabilità fornitori**. |
    | Descrizione                            | Immetti una descrizione del plafond fiscale. |
    | Dal                              | La data di inizio del periodo durante il quale è effettivo il plafond fiscale. |
    | Al                                | La data di fine del periodo durante il quale è effettivo il plafond fiscale. |
    | Data di chiusura                            | La data calcolata in cui il plafond fiscale è chiuso. |
    | Importo del plafond iniziale                 | Immetti l'importo del plafond fiscale. |
    | Importo corrente iniziale                 | L'importo calcolato disponibile nel plafond fiscale. |
    | Tipo di avviso del plafond, importo,%        | Il tipo di controllo che viene eseguito e l'importo o la percentuale correlati in corrispondenza dei quali gli utenti inizieranno a ricevere avvisi sull'importo rimanente del plafond fiscale. |
    | Periodo di liquidazione                      | Specifica il periodo di liquidazione. |
    | Operazioni che contribuiscono al plafond | Attiva o disattiva le opzioni per l'inclusione nel report sulle lettere di intenti. |

Per rivedere le transazioni fiscali registrate per un plafond fiscale esistente, nella pagina **Plafond fiscale**, nel riquadro azioni, seleziona **Transazioni plafond**.

## <a name="create-intent-letters"></a>Crea lettere d'intento

Prima di iniziare a creare una nuova lettera di intenti, verificare che sia presente un periodo di liquidazione IVA per il periodo in cui si prevede di creare un plafond fiscale e lettere di intenti e di registrare documenti fiscali con riferimento alle lettere di intenti.

Per creare una nuova lettera di intenti per un fornitore, effettua le seguenti operazioni.

1. Vai a **Contabilità fornitori** \> **Lettere di intenti** \> **Lettere di intenti**.
2. Nel riquadro azioni, seleziona **Nuovo** e inserisci le seguenti informazioni relative alla lettera di intenti.

    | Nome campo   | Descrizione                                                                      |
    |--------------|----------------------------------------------------------------------------------|
    | Data di registrazione | Specifica la data di registrazione della lettera di intenti.                                  |
    | Tipo lettera  | Seleziona il tipo di lettera di intenti: **Quantità** oppure **Operazione specifica**.          |
    | Dal    | Specifica la data di inizio del periodo durante il quale è effettiva la lettera di intenti. |
    | Al      | Specifica la data di fine del periodo durante il quale è effettiva la lettera di intenti.   |
    | Quantità       | Specifica l'importo della lettera di intenti.                                        |

3. Nella Scheda dettaglio **Record da includere**, seleziona **Filtro** per selezionare i fornitori per i quali devono essere create le lettere di intenti.
4. Seleziona **OK** per finalizzare la selezione.
5. Nella pagina successiva, seleziona **Aggiorna gli ordini fornitore esistenti**, applica nuove lettere di intenti agli ordini fornitore esistenti che non sono stati ancora fatturati per i fornitori selezionati.
6. Seleziona **Conferma nuovamente ordini fornitore** per riconfermare gli ordini fornitore a cui vengono applicate le lettere di intenti, nel caso fossero confermate.
7. Seleziona **Escludi ordini fornitore consegnati o parzialmente consegnati** per escludere gli ordini fornitore che sono stati consegnati in tutto o in parte dall'elenco degli ordini fornitore che verranno aggiornati con lettere di intenti.
8. Seleziona **OK** per creare lettere di intenti basate su parametri specificati.

    > [!NOTE]
    > Quando vengono create lettere di intenti, il sistema le numera automaticamente in base alla sequenza numerica specificata per il riferimento **Numero lettera di intenti** nella pagina **Parametri contabilità fornitori**.

9. Per le lettere di intenti che vengono create, nella scheda **Generale**, puoi inserire informazioni sul modello telematico generato.

    Nella seguente tabella vengono descritti i vari campi.

    | Nome campo    | Descrizione |
    |---------------|-------------|
    | ID modello      | L'identificatore del modello telematico in cui è stata inclusa la lettera di intenti. Questo valore viene inserito automaticamente in base alla sequenza numerica specificata per il riferimento **ID modello telematico lettera di intenti** nella pagina **Parametri di contabilità generale**. |
    | Tipo di acquisto | Seleziona il tipo di acquisto: **Acquisti** o **Importo**. |

> [!NOTE]
> Le lettere di intenti del tipo **Periodo** non sono supportate e non è possibile crearle. Il tipo **Periodo** viene selezionato per i dati storici, per quegli utenti che hanno precedentemente utilizzato questo tipo e il parametro **Assegnazione automatica lettera di intento** nella scheda **Contabilità generale e IVA** della pagina **Parametri contabilità fornitori**.

## <a name="work-with-intent-letters"></a>Utilizza le lettere di intenti

Le lettere di intenti create per i fornitori possono essere applicate agli ordini fornitore o alle fatture fornitore prima che le fatture vengano registrate.

Per applicare una lettera di intenti a un ordine fornitore o a un giornale di registrazione delle fatture fornitore, selezionala nel campo **Numero lettera di intenti** del relativo ordine fornitore o giornale di fatture dei fornitori. Il gruppo IVA sulle vendite specificato nel campo **Gruppo plafond fiscale** nella pagina **Parametri contabilità fornitori** verrà compilata automaticamente per l'ordine fornitore o per il giornale di fatture dei fornitori.

![Campo del numero di lettera di intenti per un ordine fornitore.](media/emea-ita-exil-plafond-PO.jpg)

Puoi inoltre rivedere le lettere di intenti per un fornitore specifico dai dati master del fornitore.

1. Andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**.
2. Nel riquadro azioni, nella scheda **Fornitore** del gruppo **Informazioni correlate**, seleziona **Lettere di intenti** per visualizzare le lettere di intenti correlate al fornitore selezionato.

## <a name="generate-the-telematic-model-for-intent-letters"></a>Genera il modello telematico per le lettere di intenti

Per generare il modello telematico per una lettera di intenti, attieniti alla seguente procedura.

1. Vai a **Imposta** \> **Dichiarazioni** \> **IVA** \> **Lettere di intenti - Modello telematico**.
2. Nel riquadro azioni, seleziona **Nuovo** per creare un nuovo record per il reporting di modelli telematici. L'ID del modello viene inserito automaticamente in base alla sequenza numerica specificata per il riferimento **ID modello telematico lettera di intenti** nella pagina **Parametri di contabilità generale**.
3. Nel campo **Descrizione interna**, specificare la descrizione interna per il nuovo modello telematico.
4. Nella scheda **Generale**, immetti tutte le informazioni correlate sul nuovo modello telematico: firmatario, autore, parametri integrativi e nome del file.
5. Nel riquadro azioni, seleziona **Trasferimento**, quindi seleziona le lettere di intenti da includere nel modello corrente. Le lettere di intenti selezionate verranno visualizzate nella Scheda dettaglio **Lettere di intenti**.

    > [!NOTE] 
    > Le lettere di intenti già incluse in altri modelli non possono essere selezionate.

6. Nel riquadro azioni, seleziona **Esporta** per generare il file di output **Modello telematico lettera di intenti**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
