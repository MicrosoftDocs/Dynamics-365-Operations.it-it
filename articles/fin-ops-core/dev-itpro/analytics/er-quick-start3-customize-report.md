---
title: Personalizzare le configurazioni dei rapporti elettronici per generare un documento elettronico
description: Questo articolo spiega come personalizzare le configurazioni di report elettronico (ER) fornite da Microsoft che vengono usate per generare un documento elettronico personalizzato.
author: kfend
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.custom: 220314,  ""intro-internal
ms.assetid: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
ms.openlocfilehash: cd3200bea07d622632dc5781638ec825c21233e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278948"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>Personalizzare le configurazioni dei rapporti elettronici per generare un documento elettronico

[!include[banner](../includes/banner.md)]

Il [framework di report elettronico (ER)](general-electronic-reporting.md) consente di caricare [configurazioni](general-electronic-reporting.md#Configuration) di report elettronici che Microsoft fornisce nell'istanza di Microsoft Dynamics 365 Finance. In questo modo, le configurazioni fornite da Microsoft possono fungere da soluzione ER utilizzata per generare fatture elettroniche dei clienti (fatture elettroniche). È possibile utilizzare questa soluzione ER per configurare la propria soluzione ER personalizzata per accedere ai campi del database personalizzati e generare fatture elettroniche conformi ai requisiti specifici, senza dover modificare il codice sorgente.

## <a name="overview"></a>Panoramica

Per l'esempio in questo articolo, è necessario specificare un codice di identificazione imposta federale come nuovo attributo personalizzato di ogni cliente fatturato elettronicamente. Pertanto, è necessario personalizzare la struttura della fattura attualmente utilizzata, aggiungendo una nuova voce che deve essere riempita con il codice fiscale in ogni fattura elettronica che viene generata.

Le procedure in questo articolo spiegano come un utente con il ruolo Amministratore di sistema, Sviluppatore per la creazione di report elettronici o Consulente funzionale per la creazione di report elettronici può eseguire le seguenti attività nell'istanza di Finance:

- [Configurare il set minimo di parametri ER necessario per iniziare a utilizzare il framework ER](#ConfigureER).
- [Importare le versioni iniziali delle configurazioni ER standard fornite per generare le fatture elettroniche](#ImportERConfigurations1).
- [Configurare i parametri della contabilità clienti per iniziare a utilizzare le configurazioni ER standard](#ConfigureAR1).
- [Configurare i parametri della persona giuridica per fatturare i clienti](#ConfigureLE).
- [Preparare un record cliente per la fatturazione elettronica](#ConfigureCustomer1).
- [Aggiungere, registrare e inviare una fattura cliente utilizzando le configurazioni ER standard](#ProcessInvoice1).
- [Aggiungere un campo di database personalizzato per gestire un codice di identificazione imposta federale per i clienti](#AddCustomField).
- [Aggiornare i metadati ER per abilitare le modifiche al database per la progettazione del mapping di modello ER](#RefreshERMetadata).
- [Progettare le configurazioni ER personalizzate per generare fatture elettroniche che contengano il nuovo codice fiscale](#DesignCustomERConfigurations).
- [Configurare i parametri della contabilità clienti per iniziare a utilizzare le configurazioni ER personalizzate](#ConfigureAR2).
- [Aggiornare un record cliente per la fatturazione elettronica](#ConfigureCustomer2).
- [Aggiungere, registrare e inviare una fattura cliente utilizzando le configurazioni ER personalizzate](#ProcessInvoice2).
- [Importare le nuove versioni delle configurazioni ER standard fornite per generare le fatture elettroniche](#ImportERConfigurations2).
- [Adottare le modifiche alle nuove versioni delle configurazioni ER standard nelle configurazioni ER personalizzate](#RebaseCustomERConfigurations).
- [Aggiungere, registrare e inviare una fattura cliente utilizzando le nuove versioni delle configurazioni ER personalizzate](#ProcessInvoice3).

Tutte queste procedure possono essere completate nella società **DEMF**.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>Configurare il framework ER

In qualità di utente nel ruolo di consulente funzionale per la creazione di report elettronici o sviluppatore per la creazione di report elettronici, è necessario configurare il set minimo di parametri ER. È quindi possibile iniziare a utilizzare il framework ER per progettare versioni personalizzate delle configurazioni standard della soluzione ER utilizzata per generare fatture elettroniche.

### <a name="configure-er-parameters"></a>Configurare i parametri ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Progetto localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Parametri per la creazione di report elettronici**.
3. Nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
4. Nella scheda **Allegati** nel campo **Configurazioni** selezionare **File**.
5. Nei campi **Archivio processi**, **Temporaneo**, **Base** e **Altri**, seleziona il tipo **File**.

Per ulteriori informazioni sui parametri ER, vedi [Configurare il framework ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a>Attivare un provider di configurazioni ER

Ogni configurazione ER aggiunta viene contrassegnata come di proprietà di un provider di configurazione ER. Il provider di configurazione ER che è attivato nell'area di lavoro **Creazione di report elettronici** viene utilizzato per questo scopo. Pertanto, è necessario attivare un provider di configurazione ER nell'area di lavoro **Creazione di report elettronici** prima di iniziare ad aggiungere o modificare le configurazioni ER.

> [!NOTE]
> Solo il proprietario di una configurazione ER può modificarla. Pertanto, prima di poter modificare una configurazione ER, è necessario attivare il provider di configurazione ER appropriato nell'area di lavoro **Creazione di report elettronici**.

#### <a name="review-the-list-of-er-configuration-providers"></a>Rivedere l'elenco dei provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Progetto localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Tabella del provider di configurazione**, ogni record del provider ha un nome e un URL univoci. Rivedi il contenuto della pagina. Se un record per **Litware, Inc.** (`https://www.litware.com`) esiste già, salta la procedura successiva, [Aggiungere un nuovo provider di configurazione ER](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Aggiungere un nuovo provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Progetto localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Provider di configurazione**, seleziona **Nuovo**.
4. Nel campo **Nome**, immetti **Litware, Inc.**
5. Nel campo **Indirizzo Internet** immetti `https://www.litware.com`.
6. Selezionare **Salva**.

#### <a name="activate-an-er-configuration-provider"></a>Attivare un provider di configurazioni ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Progetto localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Litware, Inc.**, quindi seleziona **Imposta attivo**.

Per ulteriori informazioni sui provider di configurazione ER, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>Importare le versioni iniziali delle configurazioni ER standard

Per aggiungere le configurazioni ER standard all'istanza corrente di Finance, è necessario importarle dall'[archivio](general-electronic-reporting.md#Repository) ER che era configurato per quell'istanza.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Progetto localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**, quindi seleziona **Archivi** per visualizzare l'elenco dei repository per il provider Microsoft.
3. Nella pagina **Archivi di configurazione** seleziona l'archivio del tipo **Globale**, quindi seleziona **Apri**. Se viene richiesta l'autorizzazione per connettersi a Regulatory Configuration Service, segui le istruzioni di autorizzazione.
4. Nella pagina **Archivio di configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona la configurazione del formato **Fattura di vendita Peppol**.
5. Nella scheda dettaglio **Versioni**, selezionare la versione **11.2.2**.
6. Selezionare **Importa** per scaricare la versione selezionata dal repository globale.

![Pagina Archivio di configurazione.](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> In caso di problemi di accesso all'[archivio globale](er-download-configurations-global-repo.md), puoi invece [scaricare le configurazioni](download-electronic-reporting-configuration-lcs.md) da Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a>Rivedere le configurazioni ER importate

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Progetto localizzazione**, nella sezione **Configurazioni**, seleziona il riquadro **Configurazioni report**.
3. Nella pagina **Configurazioni** espandere la scheda dettaglio **Componenti di configurazione**.
4. Nell'albero di configurazione nel riquadro di sinistra, espandere **Modello di fattura** e quindi espandere **Fattura di vendita UBL**.

Si noti che, oltre al formato ER **Fattura di vendita Peppol** selezionato, sono state importate altre configurazioni ER necessarie. Poiché le nuove versioni delle configurazioni ER vengono costantemente pubblicate nel repository globale e in LCS per mantenere le soluzioni corrispondenti conformi ai nuovi requisiti, le ultime versioni della configurazione del modello di dati richiesta e le relative configurazioni di mapping di modello sono state importate.

![Pagina Configurazioni.](./media/er-quick-start3-imported-solution1a.png)

Per simulare lo stato in cui si troverebbero le configurazioni ER nell'istanza corrente di Finance se si importasse la versione **11.2.2** del formato ER **Fattura di vendita Peppol** in passato (ad esempio, il 7 agosto 2019), seguire questi passaggi.

- Nel riquadro azioni selezionare **Elimina** per eliminare tutte le configurazioni ER che sono state pubblicate dopo il 7 agosto 2019. Solo le configurazioni **Modello di fattura**, **Mapping di modello fattura** (inizialmente chiamato **Mapping di modello fattura cliente**), **Fattura di vendita UBL** e **Fattura di vendita Peppol** devono rimanere.
- Per le configurazioni ER rimaste, nella scheda dettaglio **Versioni** selezionare **Elimina** per eliminare tutte le versioni delle configurazioni ER pubblicate dopo il 7 agosto 2019.

Quindi verificare che le seguenti configurazioni siano disponibili nell'albero di configurazione:

- Configurazione di modello di dati ER **modello di fattura** (inizialmente denominato **modello di fattura cliente**):

    - La versione 11 contiene la versione 10 del componente ER modello di dati che rappresenta la struttura dati del dominio aziendale di fatturazione. Questa configurazione ER è stata importata come predecessore del formato ER **Fattura di vendita Peppol** selezionato per l'importazione.
    - La versione 50 contiene la versione 31 del componente ER del modello di dati. Questa configurazione ER è stata importata come predecessore della versione del 7 agosto 2019 della configurazione del mapping di modello ER **mapping di modello di fattura**.

    ![Configurazione del modello di dati ER modello di fattura nella pagina Configurazioni.](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > Se non è visualizzata la versione 50 di questo modello di dati, aprire il repository globale e importare la versione 50.19 della configurazione ER **Mapping di modello di fattura**.

- Configurazione mapping di modello ER **mapping modello di fattura** (inizialmente denominato **mapping modello di fattura cliente**):

    - La versione 50.19 è stata importata come ultima implementazione della versione 50 della configurazione del modello di dati ER **modello di fattura**. Contiene due componenti ER mapping di modello che descrivono come il modello di dati viene compilato con i dati dell'applicazione in fase di runtime.

    ![Configurazione mapping modello ER mapping modello fattura nella pagina Configurazioni.](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > Se non è visualizzata la versione 50.19 di questo mapping di modello, aprire il repository globale e importare la versione 50.19 della configurazione ER **Mapping di modello di fattura**.

- **Configurazioni del formato ER Fattura di vendita UBL**:

    - La versione 11.2 contiene i componenti ER formato e mapping del formato. Il componente di formato specifica il layout del report. Il componente di mapping del formato contiene l'origine dati del modello e specifica come questa origine dati viene usata per compilare il layout del report in fase di esecuzione. Questo formato ER è stato configurato per generare fatture elettroniche in formato UBL (Universal Business Language). È stato importato come padre del formato ER **Fattura di vendita Peppol** selezionato per l'importazione.

- **Configurazioni del formato ER Fattura di vendita Peppol**:

    - La versione 11.2.2 contiene i componenti ER formato e mapping del formato configurati per generare fatture elettroniche nel formato PEPPOL (Pan-European Public Procurement OnLine).

    ![Configurazione formato ER fattura di vendita Peppol nella pagina Configurazioni.](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>Configurare i parametri contabilità clienti

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.
2. Nella scheda **Documenti elettronici** nella scheda dettaglio **Creazione di report elettronici** nel campo **Fattura di vendita e a testo libero** selezionare **Fattura di vendita Peppol**.
3. Selezionare **Salva**.

![Scheda Documento elettronico nella pagina parametri contabilità clienti.](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>Configurare i parametri della persona giuridica

1. Andare ad **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche**.
2. Per la società **DEMF** selezionata, nella scheda dettaglio **Informazioni sul conto bancario** nel campo **Numero di registrazione** immettere **1234**.
3. Selezionare **Salva**.
4. Chiudere la pagina **Persone giuridiche**.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>Preparare un record cliente

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Nella pagina **Tutti i clienti** selezionare il collegamento dell'account cliente **DE-014**.

### <a name="add-a-customer-contact"></a>Aggiungere un contatto cliente

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Nel riquadro azioni, nella scheda **Cliente**, nel gruppo **Account**, selezionare **Contatti**.
3. Selezionare **Aggiungi contatti**.
4. Nella pagina **Contatti** nel campo **Nome** aprire la ricerca, selezionare **Adam Carter** e quindi selezionare **Seleziona** per chiudere la ricerca.
5. Selezionare **Salva**.
6. Chiudere la pagina **Contatti**.

### <a name="define-a-primary-contact"></a>Definire un contatto primario

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Nella scheda dettaglio **Dati demografici vendite** nel campo **Contatto primario** selezionare **Adam Carter**.

### <a name="set-the-e-invoicing-option"></a>Impostare l'opzione di fatturazione elettronica

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Nella scheda dettaglio **Fattura e consegna** impostare l'opzione **Fattura elettronica** su **Sì**.
3. Selezionare **Salva**.
4. Chiudere la pagina **Tutti i clienti**.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>Elaborare una fattura cliente utilizzando le configurazioni ER standard

È ora possibile utilizzare le configurazioni ER standard importate per inviare elettronicamente una fattura a testo libero a un cliente.

### <a name="add-a-new-invoice"></a>Aggiungere una nuova fattura

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Nella pagina **Fattura a testo libero** selezionare **Nuovo**.
3. Nella scheda dettaglio **Intestazione fattura a testo libero** nel campo **Account cliente** selezionare **DE-014**.
4. Nella scheda dettaglio **Righe fattura** viene aggiunta automaticamente una riga della fattura. In questa riga, impostare i seguenti campi:

    - Nel campo **Descrizione** immettere **Notebook**.
    - Nel campo **Conto principale** selezionare **401100**.
    - Nel campo **Prezzo unitario** immettere **1000**.

5. Selezionare **Salva**.

![Pagina Fattura a testo libero.](./media/er-quick-start3-add-invoice.png)

Per ulteriori informazioni, vedere [Creare una fattura a testo libero](../../../finance/accounts-receivable/create-free-text-invoice-new.md).

### <a name="post-a-new-invoice"></a>Registrare una nuova fattura

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Nella pagina **Fattura a testo libero** nel riquadro azioni selezionare **Registra**.
3. Nella finestra di dialogo **Registra fattura a testo libero** selezionare **OK**.

![Pagina Dettagli fattura a testo libero.](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>Inviare una fattura registrata

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Nella pagina **Fattura a testo libero** nel riquadro azioni, nel gruppo di **documenti** selezionare **Invia** \> **Originale**.

    ![Anteprima della fattura originale.](./media/er-quick-start3-send-invoice.png)

3. Chiudere la pagina **Fattura a testo libero**.

### <a name="analyze-a-generated-e-invoice"></a>Analizzare una fattura elettronica generata

1. Accedere a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi di creazione report elettronici**.
2. Nella pagina **Processi di creazione report elettronici** selezionare il record iniziale che ha la descrizione dell'attività **Invia XML di fatturazione elettronica**.
3. Selezionare **Mostra file** per accedere all'elenco dei file generati.

    ![Pagina dei processi di Creazione di report elettronici.](./media/er-quick-start3-jobs-list.png)

4. Selezionare **Apri** per scaricare il file XML di fatturazione elettronica che viene generato.
5. Analizzare il file XML di fatturazione elettronica. Si noti che lo schema fiscale del cliente è attualmente rappresentato dagli attributi XML **schemeID** e **schemeAgencyID**. Notare anche che l'elemento XML **cbc:CustomizationID** attualmente contiene il testo seguente: `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![Anteprima del file XML di fatturazione elettronica generato.](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>Aggiungere un campo di database personalizzato

È possibile usare la funzione [Campo personalizzato](../../fin-ops/get-started/user-defined-fields.md) per eseguire la seguente personalizzazione nell'istanza di Finance corrente:

- Personalizzare la struttura del database aggiungendo un nuovo campo di database personalizzato che memorizza un codice di identificazione imposta federale per ogni cliente.
- Personalizzare la pagina **Cliente** aggiungendo un nuovo campo di immissione dati che può essere utilizzato per inserire un valore di codice fiscale nel nuovo campo di database personalizzato.

Seguire i passaggi seguenti per effettuare le personalizzazioni.

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Nella pagina **Tutti i clienti** selezionare il collegamento dell'account cliente **DE-014**.
3. Nella scheda dettaglio **Generale** fare clic con il pulsante destro del mouse in qualsiasi area vuota sotto il campo **Lingua** quindi selezionare **Personalizza: UpperGroup**.

    Il contenuto della scheda dettaglio **Generale** è evidenziato e un menu **Personalizza** viene visualizzato.

4. Nel menu **Personalizza** selezionare **Aggiungi un campo**.
5. Nella finestra di dialogo **Aggiungi colonne** selezionare **Crea nuovo campo**.
6. Nella finestra di dialogo **Crea nuovo campo** nel campo **Nome tabella** selezionare **Clienti**.
7. Nel campo **Prefisso nome**, immettere **FederalTaxID**.

    > [!NOTE]
    > L'intero nome del campo è stato definito automaticamente come **FederalTaxID\_Personalizzato**.

8. Nel campo **Etichetta**, immettere **ID imposta federale**.
9. Nel campo **Tipo** selezionare **Testo**.
10. Nel campo **Lunghezza** immettere **20**.
11. Selezionare **Salva**.
12. Nella finestra di messaggio visualizzata, selezionare **Sì** per confermare che si desidera creare una nuova voce di campo **FederalTaxID** per la tabella **Clienti**.
13. Selezionare **Inserisci** per <a name="insert_custom_field"></a>aggiungere il campo **FederalTaxID\_Personalizzato** alla pagina corrente.

    ![Pagina Tutti i clienti.](./media/er-quick-start3-create-new-field.gif)

14. Chiudere la pagina **Tutti i clienti**.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>Aggiornare i metadati ER

È necessario aggiornare i metadati ER per creare il campo personalizzato aggiunto [visibile](electronic-reporting-er-configure-parameters.md#frequently-asked-questions) nella progettazione mapping di modello ER.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Rigenera riferimenti tabella**.
2. Nella finestra di dialogo **Aggiorna modello di dati** selezionare **OK**.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>Progettare le configurazioni ER personalizzate

È possibile utilizzare le configurazioni ER fornite da Microsoft per progettare le configurazioni ER personalizzate in modo che generino fatture elettroniche che contengano il nuovo codice fiscale.

### <a name="customize-the-data-model-configuration"></a>Personalizzare la configurazione del modello di dati

In qualità di utente nel ruolo di consulente funzionale per la creazione di report elettronici, è possibile progettare il modello di dati ER personalizzato.

#### <a name="add-a-custom-data-model-configuration"></a>Aggiungere una configurazione del modello dati personalizzata

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, selezionare **Modello di fattura cliente**.
3. Nel riquadro azioni, selezionare **Crea configurazione**.
4. Nella finestra di dialogo a discesa, nel campo **Nuovo** selezionare **Deriva da nome: modello di fattura cliente, Microsoft** per indicare che la nuova configurazione del modello di dati ER personalizzata deve essere basata sulla configurazione del modello di dati ER.
5. Nel campo **Nome** digitare **Modello di fattura (Litware)**.
6. Selezionare **Crea configurazione** per aggiungere la nuova configurazione ER.

È ora possibile utilizzare la progettazione del modello di dati ER per modificare la versione 50.1 della configurazione ER **Modello di fattura (Litware)** nello stato **Bozza**.

![Versione 50.1 della configurazione ER nella pagina Configurazioni.](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>Configurare un modello di dati personalizzato

È necessario modificare il modello di dati personalizzato aggiungendo un nuovo campo per fornire il valore di un codice di identificazione imposta federale. Questo codice fa parte dei dati del cliente per ogni formato ER che utilizzerà questo modello di dati come origine dati.

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, selezionare **Modello di fattura (Litware)**.
2. Nella scheda dettaglio **Versioni** selezionare la versione **50.1** della configurazione del modello di dati ER selezionata nello stato **Bozza**.
3. Nel riquadro azioni selezionare **Progettazione** per la versione di configurazione selezionata.
4. Nella pagina **Progettazione modello di dati** nell'albero del modello di dati, selezionare **Informazioni sul cliente (cliente)**.
5. Selezionare **Nuovo**.
6. Nella finestra di dialogo a discesa, nel campo **Nuovo nodo come** accettare il valore predefinito, **Figlio di un nodo attivo**.
7. Nel campo **Nome**, immettere **FederalTaxID\_Litware**.
8. Nel campo **Tipo di elemento** accettare il valore predefinito, **Stringa**.
9. Selezionare **Aggiungi** e quindi **Salva**.

    ![Finestra di progettazione modello di dati.](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > I campo **Etichetta** e **Descrizione** descrivono lo scopo del nuovo campo. È possibile compilare questi campi in più lingue. Per ulteriori informazioni, vedere [Progettare report multilingue nella creazione di report elettronici](er-design-multilingual-reports.md).

10. Chiudere la pagina **Progettazione del modello di dati**.

#### <a name="complete-a-custom-data-model-configuration"></a>Completare una configurazione del modello dati personalizzata

È necessario completare il lavoro con la versione 50.1 della configurazione del modello di dati ER personalizzata per renderla disponibile in modo che sia possibile aggiungere altre configurazioni ER personalizzate.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura**, quindi selezionare **Modello di fattura (Litware)**.
3. Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.

Lo stato della versione 50.1 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura. Una nuova versione modificabile, 50.2, è stata aggiunta e ha lo stato di **Bozza**. È possibile utilizzare questa versione per apportare ulteriori modifiche alla configurazione del modello di dati ER personalizzata.

![Versione 50.1 completata nella pagina Configurazioni.](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>Personalizzare la configurazione del mapping di modello

In qualità di utente nel ruolo di sviluppatore per la creazione di report elettronici, è possibile progettare il mapping di modello ER personalizzato.

#### <a name="add-a-custom-model-mapping-configuration"></a>Aggiungere una configurazione del mapping di modello personalizzata

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura cliente**, quindi selezionare **Mapping di modello di fattura cliente**.
3. Nel riquadro azioni, selezionare **Crea configurazione**.
4. Nella finestra di dialogo a discesa, nel campo **Nuovo** selezionare **Deriva da nome: mapping di modello di fattura cliente, Microsoft** per indicare che la nuova configurazione del mapping di modello ER personalizzata deve essere basata sulla configurazione del mapping di modello ER.
5. Nel campo **Nome** digitare **Mapping di modello di fattura (Litware)**.
6. Nel campo **Modello di destinazione** selezionare **Modello di fattura (Litware)**.

    > [!IMPORTANT]
    > Questo passaggio è molto importante. Se si omette non si potrà utilizzare il modello di dati personalizzato nel mapping di modello configurato.

7. Selezionare **Crea configurazione** per aggiungere la nuova configurazione ER.

![Aggiunta di una configurazione del mapping di modello personalizzata nella pagina Configurazioni.](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>Configurare un mapping di modello personalizzato

È necessario modificare il mapping di modello personalizzato e specificare come il campo **FederalTaxID\_Litware** personalizzato del modello di dati personalizzato deve essere compilato con i dati dell'applicazione in fase di esecuzione.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura cliente** \> **Mapping di modello di fattura cliente** e selezionare **Mapping di modello di fattura (Litware)**.
3. Nel riquadro azioni selezionare **Progettazione**.
4. Nella pagina **Modello per mapping origine dati** selezionare il mapping **Fattura cliente**.

    ![Pagina Modello per mapping origine dati.](./media/er-quick-start3-select-customer-mapping.png)

5. Selezionare **Progettazione**.
6. Nella pagina **Progettazione mapping di modello** nel riquadro **Origini dati** espandere l'origine dati **CustInvoiceJour** che rappresenta la tabella dell'applicazione **CustInvoiceJour**.
7. Sotto **CustInvoiceJour**, espandere **Relazioni** per esaminare l'elenco delle relazioni di tipo molti-a-uno (N:1) per la tabella **CustInvoiceJour**.
8. Sotto **CustInvoiceJour** \> **Relazioni**, espandere **Clienti (CustTable)** per accedere ai campi e alle relazioni della tabella **Clienti (CustTable)**.
9. Selezionare il campo origine dati **FederalTaxID\_Personalizzato** implementato [prima](#insert_custom_field).
10. Nel riquadro **Modello di dati** espandere **Informazioni sul cliente (cliente)** e selezionare il campo del modello di dati **FederalTaxID\_Litware**.
11. Selezionare **Associa**.

    ![Pagina Progettazione mapping modello.](./media/er-quick-start3-customize-model-mapping.gif)

12. Selezionare **Salva**.
13. Chiudere la pagina **Progettazione mapping modello**.
14. Chiudere la pagina **Modello per mapping origine dati**.

#### <a name="complete-a-custom-model-mapping-configuration"></a>Completare una configurazione del mapping di modello personalizzata

È necessario completare il lavoro con la versione 50.19.1 della configurazione del mapping di modello ER personalizzata per renderla disponibile per l'uso.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura cliente** \> **Mapping di modello di fattura cliente** e selezionare **Mapping di modello di fattura (Litware)**.
3. Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.

Lo stato della versione 50.19.1 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura. Una nuova versione modificabile, 50.19.2, è stata aggiunta e ha lo stato di **Bozza**. È possibile utilizzare questa versione per apportare ulteriori modifiche alla configurazione del mapping di modello ER personalizzata.

![Versione 50.19.1 completata nella pagina Configurazioni.](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> Il [ciclo di vita](general-electronic-reporting-manage-configuration-lifecycle.md) della configurazione supportata non copre il ciclo di vita delle modifiche al database. Se si esporta la versione 50.19.1 della configurazione **Mapping di modello di fattura (Litware)** dall'istanza di Finance corrente e si tenta di importarla in un'altra istanza che non contiene il campo personalizzato **FederalTaxID\_Personalizzato** nella tabella **CustTable**, si verificherà un'eccezione. L'eccezione indicherà che la configurazione ER importata non è compatibile con i metadati dell'istanza di Finance di destinazione.

### <a name="customize-the-format-configuration"></a>Personalizzare la configurazione del formato

In qualità di utente nel ruolo di consulente funzionale per la creazione di report elettronici, è possibile progettare il formato ER personalizzato.

#### <a name="add-a-custom-format-configuration"></a>Aggiungere una configurazione di formato ER personalizzata

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura cliente** \> **Fattura di vendita UBL**, quindi selezionare **Fattura di vendita Peppol**.
3. Nel riquadro azioni, selezionare **Crea configurazione**.
4. Nella finestra di dialogo a discesa, nel campo **Nuovo** selezionare **Deriva da nome: fattura di vendita Peppol, Microsoft** per indicare che la nuova configurazione del formato ER personalizzata deve essere basata sulla configurazione del formato ER.
5. Nel campo **Nome** digitare **Fattura di vendita Peppol (Litware)**.
6. Nel campo **Modello di dati** selezionare **Modello di fattura (Litware)** per utilizzare i componenti di mapping di modello e modello di dati personalizzati.

    > [!NOTE]
    > Questo passaggio è molto importante. Se si omette non si potrà utilizzare il modello di dati personalizzato nel formato configurato.

7. Nel campo **Modello di dati**, selezionare la definizione radica **InvoiceCustomer**.
8. Selezionare **Crea configurazione** per aggiungere la nuova configurazione ER.

![Aggiunta di una configurazione di formato personalizzata nella pagina Configurazioni.](./media/er-quick-start3-adding-custom-format.png)

È ora possibile utilizzare la progettazione delle operazioni ER per modificare la versione 11.2.2.1 della configurazione ER **Fattura di vendita Peppol (Litware)** nello stato **Bozza**.

![Versione 11.2.2.1 della configurazione ER nella pagina Configurazioni.](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>Configurare un formato personalizzato

È necessario modificare il formato personalizzato aggiungendo un nuovo elemento di formato per compilare il valore del codice di identificazione imposta federale di un cliente fatturato.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura cliente** \> **Fattura di vendita UBL** \> **Fattura di vendita Peppol**, quindi selezionare **Fattura di vendita Peppol (Litware)**.
3. Nel riquadro azioni selezionare **Progettazione**.
4. Nella struttura ad albero del formato, espandere **XMLHeader** \> **Invoice** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** e selezionare **cbc:ID**.
5. Selezionare **Aggiungi** e quindi **XML** \> **Attributo**.
6. Nella finestra di dialogo **Proprietà componente**, nel campo **Nome**, immettere **FederalTaxID**.
7. Selezionare **OK** per aggiungere un nuovo elemento di formato per crearne uno nuovo attributo XML **FederalTaxID** in un file XML generato.
8. Nella struttura ad albero del formato, sotto **XMLHeader** \> **Invoice** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID**, selezionare **FederalTaxID**.
9. Selezionare **Sposta su**.

![Nuovo elemento di formato nella pagina Progettazione formati.](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>Configurare un mapping di formato personalizzato

1. Nella pagina **Progettazione format**, nella scheda **Mapping**, espandere l'origine dati **Fattura** della tabella **Modello**.
2. Sotto **Fattura**, espandere **Informazioni sul cliente (cliente)** e selezionare **FederalTaxID\_Litware**.
3. Selezionare **Associa**.

    ![Pagina Progettazione formati.](./media/er-quick-start3-customized-format-mapping.png)

4. Selezionare l'origine dati **Fattura** di tipo **Modello** e selezionare **Modifica**.
5. Nel campo **Versione** selezionare la versione **1** del modello di dati personalizzato, quindi selezionare **OK**.
6. Selezionare **Salva**.
7. Chiudere la pagina **Progettazione formati**.

#### <a name="complete-a-custom-format-configuration"></a>Completare una configurazione di formato ER personalizzata

È necessario completare il lavoro con la versione 11.2.2.1 della configurazione del formato ER personalizzata per renderla disponibile per l'uso.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura cliente** \> **Fattura di vendita UBL** \> **Fattura di vendita Peppol**, quindi selezionare **Fattura di vendita Peppol (Litware)**.
3. Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.

Lo stato della versione 11.2.2.1 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura. Una nuova versione modificabile, 11.2.2.2, è stata aggiunta e ha lo stato di **Bozza**. È possibile utilizzare questa versione per apportare ulteriori modifiche alla configurazione di formato ER personalizzata.

![Versione 11.2.2.1 completata nella pagina Configurazioni.](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>Configurare i parametri della contabilità clienti per iniziare a utilizzare le configurazioni ER personalizzate

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.
2. Nella scheda **Documenti elettronici** nella scheda dettaglio **Creazione di report elettronici** nel campo **Fattura di vendita e a testo libero** selezionare **Fattura di vendita Peppol (Litware)**.
3. Selezionare **Salva**.

![Pagina parametri contabilità clienti, scheda Documento elettronico, scheda dettaglio Creazione di report elettronici.](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>Aggiornare un record cliente aggiungendo un codice di identificazione imposta federale

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Nella pagina **Tutti i clienti** selezionare il collegamento dell'account cliente **DE-014**.
3. Nella scheda dettaglio **Generale** nel campo **ID imposta federale** immettere **LITWARE-6789**.
4. Selezionare **Salva**.

    ![Pagina Dettagli cliente DE-014.](./media/er-quick-start3-added-tax-id-value.png)

5. Chiudere la pagina **Tutti i clienti**.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>Elaborare una fattura cliente utilizzando le configurazioni ER personalizzate

### <a name="select-and-send-a-posted-invoice"></a>Selezionare e inviare una fattura registrata

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Nella pagina **Fattura a testo libero** selezionare la fattura precedentemente aggiunta e registrata.
3. Nel riquadro azioni, nel gruppo di **documenti** selezionare **Invia** \> **Originale**.
4. Chiudere la pagina **Fattura a testo libero**.

### <a name="analyze-a-generated-e-invoice"></a>Analizzare una fattura elettronica generata

1. Accedere a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi di creazione report elettronici**.
2. Nella pagina **Processi di creazione report elettronici** selezionare l'ultimo record che ha la descrizione dell'attività **Invia XML di fatturazione elettronica**.
3. Selezionare **Mostra file** per accedere all'elenco dei file generati.
4. Selezionare **Apri** per scaricare il file XML di fatturazione elettronica che viene generato.
5. Analizzare il file XML di fatturazione elettronica. Si noti che, in base alla personalizzazione, lo schema fiscale del cliente include l'attributo XML **FederalTaxID** personalizzato oltre agli attributi XML **schemeID** e **schemeAgencyID**. Il valore di questo nuovo attributo XML è specificato dall'ID imposta federale **LITWARE-6789** immesso per un cliente fatturato.

    ![Anteprima del file XML di fatturazione elettronica generato con le personalizzazioni.](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>Importare le ultime versioni delle configurazioni ER standard

Per mantenere il set di configurazioni ER standard nell'istanza di Finance [aggiornato](general-electronic-reporting-manage-configuration-lifecycle.md), è necessario importarne le nuove versioni ogni volta che diventano disponibili nel [repository](general-electronic-reporting.md#Repository) ER configurato per quell'istanza.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**, quindi seleziona **Archivi** per visualizzare l'elenco dei repository per il provider Microsoft.
3. Nella pagina **Archivi di configurazione** seleziona l'archivio del tipo **Globale**, quindi seleziona **Apri**. Se viene richiesta l'autorizzazione per connettersi a Regulatory Configuration Service, segui le istruzioni di autorizzazione.
4. Nella pagina **Archivio di configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona la configurazione del formato **Fattura di vendita Peppol**.
5. Nella scheda dettaglio **Versioni** selezionare la versione **32.6.7** della configurazione del formato ER selezionata che è stata rilasciata per supportare le fatture elettroniche dei clienti in formato PEPPOL BIS 3. Per ulteriori informazioni, vedere [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic).
6. Seleziona **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.

![Versione 32.6.7 selezionata nella pagina Archivio di configurazione.](./media/er-quick-start3-import-solution2.png)

Per informazioni su come automatizzare questo processo, vedere [Importare versioni aggiornate delle configurazioni ER](er-download-updated-versions-global-repo.md).

### <a name="review-the-imported-er-configurations"></a>Rivedere le configurazioni ER importate

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
3. Espandere la Scheda dettaglio **Componenti di configurazione**.
4. Nell'albero di configurazione nel riquadro sinistro, espandere **Modello di fattura**. Si noti che il nome **Modello di fattura cliente** è stato cambiato in **Modello di fattura** in una delle configurazioni del modello di dati ER importate.
5. Nell'albero di configurazione nel riquadro sinistro, espandere **Mapping di modello di fattura**. Si noti che il nome **Mapping di modello di fattura cliente** è stato cambiato in **Mapping di modello di fattura** in una delle configurazioni del mapping di modello ER importate.
6. Espandere **Fattura di vendita UBL** \> **Fattura di vendita Peppol**.

Si noti che, oltre al formato ER **Fattura di vendita Peppol** selezionato, sono state importate le ultime versioni delle altre configurazioni ER necessarie. Poiché le nuove versioni delle configurazioni ER vengono costantemente pubblicate nel repository globale e in LCS per mantenere le soluzioni ER corrispondenti conformi ai nuovi requisiti, le ultime versioni della configurazione del modello di dati richiesta e le relative configurazioni di mapping di modello sono state importate.

Verificare che le seguenti configurazioni ER siano disponibili nella struttura di configurazione:

- Configurazione del modello dati di ER **Modello di fattura**:

    - La versione 206 (o successiva) contiene la versione 24 (o successiva) del componente ER modello di dati che rappresenta la struttura dati del dominio aziendale di fatturazione. Questa configurazione ER è stata importata come predecessore dell'ultima configurazione del mapping di modello ER **mapping di modello di fattura** disponibile.

    ![Versione 206 nella pagina Configurazioni.](./media/er-quick-start3-imported-solution2b1.png)

- Configurazione del mapping di modello ER **Mapping di modello di fattura**:

    - La versione 206.132 (o successiva) è stata importata come ultima implementazione della versione 206 della configurazione del modello di dati ER **modello di fattura**. Contiene diversi componenti ER mapping di modello che descrivono come il modello di dati viene compilato con i dati dell'applicazione in fase di runtime.

    ![Versione 206.132 nella pagina Configurazioni.](./media/er-quick-start3-imported-solution2b2.png)

- **Configurazioni del formato ER Fattura di vendita UBL**:

    - La versione 32.6 contiene i componenti ER formato e mapping di formato. Il componente di formato specifica il layout del report. Il componente di mapping del formato contiene l'origine dati del modello e specifica come questa origine dati viene usata per compilare il layout del report in fase di esecuzione. Questo formato ER è stato configurato per generare fatture elettroniche in formato UBL. È stato importato come padre del formato ER **Fattura di vendita Peppol** selezionato per l'importazione.

- **Configurazioni del formato ER Fattura di vendita Peppol**:

    - La versione 32.6.7 contiene i componenti ER formato e mapping del formato configurati per generare fatture elettroniche nel formato PEPPOL.

    ![Versione 32.6.7 nella pagina Configurazioni.](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>Adottare le modifiche alle nuove versioni delle configurazioni ER standard nelle configurazioni ER personalizzate

### <a name="adopt-your-custom-er-data-model"></a>Adottare il modello di dati ER personalizzato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura**, quindi selezionare **Modello di fattura (Litware)**.
3. Nella scheda dettaglio **Versioni** per la versione di bozza **50.2** della configurazione del modello di dati selezionata, selezionare **Riassegna**.
4. Nel campo **Versione di destinazione** confermare la selezione della versione **206** della configurazione del modello di dati ER di base, quindi selezionare **OK**.

    La versione di bozza della configurazione del modello di dati ER personalizzata viene rinumerata da **50.2** a **206.2** per indicare che ora contiene la personalizzazione che è stata unita alle modifiche nell'ultima versione (206) della configurazione del modello di dati ER di base.

    > [!NOTE]
    > L'azione di riassegnazione è reversibile. Per annullare questa riassegnazione, seleziona la versione **50.1** del modello **Modello di fattura (Litware)** nella Scheda Dettaglio **Versioni**, quindi seleziona **Ottieni questa versione**. La versione 206.2 verrà quindi rinumerata in **50.2** e il contenuto della bozza della versione 50.2 corrisponderà al contenuto della versione 50.1.

5. Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.

Lo stato della versione 206.2 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura. Una nuova versione modificabile, 206.3, è stata aggiunta e ha lo stato di **Bozza**. È possibile utilizzare questa versione per apportare ulteriori modifiche alla configurazione del modello di dati ER personalizzata.

![Versione 206.2 completata nella pagina Configurazioni.](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>Adottare il mapping di modello ER personalizzato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura** \> **Mapping di modello di fattura** e selezionare **Mapping di modello di fattura (Litware)**.
3. Nella scheda dettaglio **Versioni** per la versione di bozza **50.19.2** della configurazione del mapping di modello selezionata, selezionare **Riassegna**.
4. Nel campo **Versione di destinazione** confermare la selezione della versione **206.132** della configurazione del mapping di modello ER di base, quindi selezionare **OK**.

    La versione di bozza della configurazione del mapping di modello ER personalizzata viene rinumerata da **50.19.2** a **206.132.2** per indicare che ora contiene la personalizzazione che è stata unita alle modifiche nell'ultima versione (206.132) della configurazione del mapping di modello ER di base.

    Notare che sono stati rilevati alcuni conflitti di riassegnazione. È ora necessario risolvere manualmente tali conflitti.

    ![Messaggio di conflitto di riassegnazione nella pagina Configurazioni.](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. Nel riquadro azioni selezionare **Progettazione**, quindi, nell'elenco dei mapping selezionare **Fattura cliente**.
6. Per ogni conflitto di riassegnazione, selezionare **Mantieni il valore**, perché è necessario mantenere il numero di versione del modello di dati personalizzato per ogni componente che è stato menzionato.

    ![Conflitti di riassegnazione nella finestra di progettazione mapping modello.](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. Selezionare **Salva** quindi chiudere la pagina **Progettazione mapping di modello**.
8. Nell'elenco dei mapping selezionare **Fattura di progetto**.
9. Per ogni conflitto di riassegnazione, selezionare **Mantieni il valore**, perché è necessario mantenere il numero di versione del modello di dati personalizzato per ogni componente che è stato menzionato.
10. Selezionare **Salva** quindi chiudere la pagina **Mapping di modello**.

    > [!NOTE]
    > L'azione di riassegnazione è reversibile. Per annullare questa riassegnazione, seleziona la versione **50.19.1** del mapping di modello **Mapping di modello di fattura (Litware)** nella Scheda Dettaglio **Versioni**, quindi seleziona **Ottieni questa versione**. La versione 206.132.2 verrà quindi rinumerata in **50.19.2** e il contenuto della bozza della versione 50.19.2 corrisponderà al contenuto della versione 50.19.1.

11. Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.

Lo stato della versione 206.132.2 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura. Una nuova versione modificabile, 206.132.3, è stata aggiunta e ha lo stato di **Bozza**. È possibile utilizzare questa versione per apportare ulteriori modifiche alla configurazione del mapping di modello ER personalizzata.

![Versione 206.132.2 completata nella pagina Configurazioni.](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>Adottare il formato ER personalizzato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandere **Modello di fattura** \> **Fattura di vendita UBL** \> **Fattura di vendita Peppol**, quindi selezionare **Fattura di vendita Peppol (Litware)**.
3. Nella scheda dettaglio **Versioni** per la versione di bozza **11.2.2.2** della configurazione del formato selezionata, selezionare **Riassegna**.
4. Nel campo **Versione di destinazione** confermare la selezione della versione **32.6.7** della configurazione del formato ER di base, quindi selezionare **OK**.

    La versione di bozza della configurazione del formato ER personalizzata viene rinumerata da **11.2.2.2** a **32.6.7.2** per indicare che ora contiene la personalizzazione che è stata unita alle modifiche nell'ultima versione (32.6.7) della configurazione del formato ER di base.

    Notare che sono stati rilevati alcuni conflitti di riassegnazione. È ora necessario risolvere manualmente tali conflitti.

5. Nel riquadro azioni selezionare **Progettazione**.
6. Per ogni conflitto di riassegnazione, selezionare **Mantieni il valore**, perché è necessario mantenere il numero di versione del modello di dati personalizzato per ogni componente che è stato menzionato.
7. Selezionare **Salva**.
8. Nella scheda **Mapping** selezionare l'origine dati **Fattura** di tipo **Modello** e selezionare **Modifica**.
9. Nel campo **Versione** selezionare la versione **2** del modello di dati personalizzato, quindi selezionare **OK**.
10. Selezionare **Salva**.

    > [!NOTE]
    > L'azione di riassegnazione è reversibile. Per annullare questa riassegnazione, seleziona la versione **11.2.2.1** del formato **Fattura di vendita (Litware)** nella Scheda Dettaglio **Versioni**, quindi seleziona **Ottieni questa versione**. La versione 32.6.7.2 verrà quindi rinumerata in **11.2.2.2** e il contenuto della bozza della versione 11.2.2.2 corrisponderà al contenuto della versione 11.2.2.1.

11. Chiudere la pagina **Progettazione formati**.
12. Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.

Lo stato della versione 32.6.7.2 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura. Una nuova versione modificabile, 32.6.7.3, è stata aggiunta e ha lo stato di **Bozza**. È possibile utilizzare questa versione per apportare ulteriori modifiche alla configurazione di formato ER personalizzata.

![Versione 32.6.7.2 completata nella pagina Configurazioni.](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>Elaborare una fattura cliente utilizzando le nuove versioni delle configurazioni ER personalizzate

### <a name="select-and-send-a-posted-invoice"></a>Selezionare e inviare una fattura registrata

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Nella pagina **Fattura a testo libero** selezionare la fattura precedentemente aggiunta e registrata.
3. Nel riquadro azioni, nel gruppo di **documenti** selezionare **Invia** \> **Originale**.

    > [!NOTE] 
    > Poiché ora sono disponibili due versioni della configurazione di formato ER **Fattura di vendita Peppol (Litware)** e nessuna delle due versioni ha il valore data effettiva, l'ultima versione viene utilizzata per generare una fattura elettronica.

4. Chiudere la pagina **Fattura a testo libero**.

### <a name="analyze-a-generated-e-invoice"></a>Analizzare una fattura elettronica generata

1. Accedere a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi di creazione report elettronici**.
2. Nella pagina **Processi di creazione report elettronici** selezionare il record più recente che ha la descrizione dell'attività **Invia XML di fatturazione elettronica**.
3. Selezionare **Mostra file** per accedere all'elenco dei file generati.
4. Selezionare **Apri** per scaricare il file XML di fatturazione elettronica che viene generato.
5. Analizzare il file XML di fatturazione elettronica. Si noti che, in base alla personalizzazione, lo schema fiscale del cliente ancora include l'attributo XML **FederalTaxID** personalizzato oltre agli attributi XML **schemeID** e **schemeAgencyID**. Inoltre, poiché le modifiche nella nuova versione del formato di base **Fattura di vendita UBL** sono state unite con la personalizzazione, il testo dell'elemento XML **cbc:CustomizationID** è stato modificato da `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` a `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`.

    ![Anteprima del file XML di fatturazione elettronica generato con personalizzazioni.](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Scaricare configurazioni ER da Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](er-download-configurations-global-repo.md)
- [Crea una fattura a testo libero](../../../finance/accounts-receivable/create-free-text-invoice-new.md)
- [Creare e utilizzare campi personalizzati](../../fin-ops/get-started/user-defined-fields.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
