---
title: Ordini di controllo qualità
description: In questo argomento viene descritto come creare manualmente o automaticamente gli ordini di controllo qualità e come utilizzarli per eseguire ispezioni e registrare i risultati dei test in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 964f8a37ac9471b2eb6c9ec01fc0322a43cfea11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022182"
---
# <a name="quality-orders"></a>Ordini di controllo qualità

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come creare manualmente o automaticamente gli ordini di controllo qualità e come utilizzarli per eseguire ispezioni e registrare i risultati dei test in Microsoft Dynamics 365 Supply Chain Management.

## <a name="automatically-created-quality-orders"></a>Creazione automatica degli ordini di controllo qualità

È possibile configurare il sistema in modo che crei automaticamente ordini di controllo qualità, in base alle regole di campionamento degli articoli. Per ulteriori informazioni, vedere [Campionamento degli articoli per la gestione della qualità](quality-item-sampling.md).

## <a name="manually-create-quality-orders"></a><a name="manual-quality-orders"></a>Creare manualmente ordini di controllo qualità

Per creare un ordine di controllo qualità manualmente, attieniti alla procedura seguente:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Ordini di controllo qualità**, nel campo **Tipo di riferimento** selezionare il riferimento inventario a cui sarà correlato l'ordine di controllo qualità. Per una descrizione dei tipi di riferimento disponibili per la selezione, vedere la sezione [Tipi di riferimento dell'ordine di controllo qualità](#ref-types) più avanti in questo argomento.

    > [!NOTE]
    > L'inventario correlato al riferimento selezionato deve essere disponibile. Se non è disponibile alcun inventario per la combinazione del tipo di riferimento, della quantità e delle dimensioni inventariali selezionate, verrà visualizzato un messaggio di errore.

1. Eseguire uno dei passaggi riportati di seguito, in base al valore selezionato nel campo **Tipo di riferimento**:

    - Se hai selezionato **Inventario**, non sono necessarie ulteriori informazioni di riferimento.
    - Se hai selezionato **Vendita** o **Acquisto**, specificare le seguenti informazioni:

        - **Selezione conto**: fai riferimento al numero cliente o fornitore.
        - **Numero di riferimento** - Fare riferimento al numero ordine cliente o fornitore.
        - **Lotto di riferimento** - Fare riferimento alla riga dell'ordine cliente o fornitore specifica.

    - Se hai selezionato **Produzione**, **Quarantena**, o **Produzione di coprodotti**, nel campo **Numero di riferimento** fare riferimento all'ordine di produzione, all'ordine batch o al numero dell'ordine di quarantena.
    - Se hai selezionato **Operazione ciclo di lavorazione**, specificare le seguenti informazioni:

        - **Numero di riferimento** - Fare riferimento al numero ordine di produzione o batch.
        - **Numero operazione** - Fare riferimento al numero di operazione ciclo di lavorazione specifico.
        - **Operazione** - Fare riferimento all'operazione ciclo di lavorazione specifica.
        - **Risorsa** - Fare riferimento alla risorsa specifica che deve essere utilizzata con l'operazione ciclo di lavorazione.

1. Nel campo **Gruppo di test** selezionare il gruppo di test da eseguire.
1. Nel campo **Quantità** immettere la quantità degli articoli da testare.
1. Nella sezione **Dimensioni inventariali**, immettere eventuali dimensioni inventariali aggiuntive richieste per l'articolo selezionato.
1. Selezionare **OK**.

Dopo aver creato un ordine di controllo qualità, è possibile iniziare a ispezionare l'inventario e registrare i risultati del test. Per ulteriori informazioni su come registrare e convalidare i risultati dei test, vedere [Verificare la qualità delle merci](tasks/inspect-quality-goods.md).

## <a name="quality-order-reference-types"></a><a name="ref-types"></a>Tipi di riferimento dell'ordine di controllo qualità

Gli ordini di controllo qualità vengono utilizzati per tenere traccia dei dettagli sulle ispezioni e sui risultati dei test per l'inventario specifico nel magazzino. Un ordine di controllo qualità deve includere un riferimento che rappresenta l'origine dell'inventario che viene testato. Gli ordini di controllo qualità possono essere correlati ai seguenti tipi di riferimento:

- **Inventario** - Questo tipo di riferimento indica che stai ispezionando l'inventario disponibile. Le ispezioni di questo tipo sono in genere casuali o non pianificate e vengono eseguite quando un addetto al magazzino identifica un problema.
- **Vendita** - Questo tipo di riferimento indica che stai ispezionando l'inventario correlato a un ordine cliente specifico. Le ispezioni di questo tipo sono tipicamente correlate alle specifiche del cliente o alla generazione di un certificato di analisi (CoA) che deve essere fornito a un cliente come parte di una spedizione. (A volte un CoA viene anche definito certificato di conformità \[CoC\] .)
- **Acquisto** - Questo tipo di riferimento indica che stai ispezionando l'inventario correlato a un ordine fornitore specifico. Le ispezioni di questo tipo vengono spesso utilizzate per ispezionare le merci in entrata prima che vengano messe in magazzino o consumate nei processi di produzione.
- **Produzione** - Questo tipo di riferimento indica che stai ispezionando l'inventario correlato a un ordine di produzione. Le ispezioni di questo tipo vengono spesso utilizzate per ispezionare i prodotti finiti prima che vengano messi in magazzino.
- **Quarantena** - Questo tipo di riferimento indica che stai ispezionando l'inventario correlato a un ordine di quarantena. Gli ordini di quarantena sono un tipo speciale di ordine che tiene traccia dell'inventario in un magazzino separato o in un'area separata del magazzino. Le ispezioni di questo tipo vengono spesso utilizzate per ispezionare le merci che un cliente ha restituito o che sono state messe in quarantena per ulteriori analisi. Gli ordini di quarantena possono essere generati dagli ordini di controllo qualità. In alternativa, possono essere generati da altre origini, quindi gli ordini di controllo qualità possono essere correlati agli ordini di quarantena.
- **Operazione ciclo di lavorazione** - Questo tipo di riferimento indica che stai ispezionando l'inventario correlato a un passaggio specifico di un ciclo di lavorazione per un ordine di produzione. Le ispezioni di questo tipo vengono in genere utilizzate per analizzare il semilavorato (WIP) di un prodotto prima che passi alla fase successiva del processo di produzione.
- **Produzione co-prodotti** - Questo tipo di riferimento indica che stai ispezionando l'inventario correlato a un co-prodotto di un ordine di produzione. Le ispezioni di questo tipo vengono generalmente utilizzate per ispezionare il co-prodotto di un ordine batch prima che il co-prodotto venga aggiunto all'inventario.

## <a name="view-and-create-quality-orders-from-various-parts-of-the-system"></a>Visualizzare e creare ordini di controllo qualità da varie parti del sistema

Gli ordini di controllo qualità possono essere creati manualmente. In alternativa, possono essere creati automaticamente in base alle associazioni di controllo qualità definite. Per ulteriori informazioni su come creare e gestire la creazione automatica degli ordini di controllo qualità, vedere [Associazioni di controllo qualità](quality-associations.md).

È possibile utilizzare la pagina dell'ordine di controllo qualità per creare manualmente un nuovo ordine di controllo qualità o visualizzare lo stato di un ordine di controllo qualità correlato a un altro record. Esistono diversi modi per accedere alla pagina dell'ordine di controllo qualità.

### <a name="from-the-quality-orders-page"></a>Dalla pagina Ordini di controllo qualità

Per creare manualmente ordini di controllo qualità e visualizzare tutti gli ordini di controllo qualità esistenti, andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**. Le sezioni rimanenti di questo argomento forniscono ulteriori informazioni su come lavorare con la pagina **Ordini di controllo qualità**.

### <a name="from-sales-orders"></a>Da ordini cliente

Per lavorare con gli ordini di controllo qualità correlati ai tuoi ordini cliente, vai a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente** e quindi segui uno di questi passaggi:

- Apri un ordine cliente o selezionalo nella griglia. Quindi, nel riquadro azioni, nella scheda **Preleva e imballa**, nel gruppo **Gestione qualità** , selezionare **Ordini di controllo qualità** per aprire la pagina **Ordini di controllo qualità**. Qui è possibile visualizzare, creare o aggiornare gli ordini di controllo qualità correlati all'ordine cliente.
- Aprire un ordine cliente e quindi nella scheda **Intestazione**, seleziona la scheda dettaglio **Generale**. Il campo **Stato ordine di controllo qualità** mostra lo stato generale di tutti gli ordini di controllo qualità correlati all'ordine cliente.
- Aprire un ordine cliente e quindi nella scheda **Righe**, seleziona la scheda dettaglio **Righe ordine cliente**. La colonna **Stato ordine di controllo qualità** mostra lo stato di ogni riga dell'ordine cliente.

### <a name="from-purchase-orders"></a>Da ordini fornitore

Per lavorare con gli ordini di controllo qualità correlati ai tuoi ordini fornitore, vai a **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore** e quindi segui uno di questi passaggi:

- Apri un ordine fornitore o selezionalo nella griglia. Quindi, nel riquadro azioni, nella scheda **Ricezione**, nel gruppo **Gestione qualità** , selezionare **Ordini di controllo qualità** per aprire la pagina **Ordini di controllo qualità**. Qui è possibile visualizzare, creare o aggiornare gli ordini di controllo qualità correlati all'ordine fornitore.
- Aprire un ordine fornitore e quindi nella scheda **Intestazione**, seleziona la scheda dettaglio **Generale**. Il campo **Stato ordine di controllo qualità** mostra lo stato generale di tutti gli ordini di controllo qualità correlati all'ordine fornitore.
- Aprire un ordine fornitore e quindi nella scheda **Righe**, seleziona la scheda dettaglio **Righe ordine fornitore**. La colonna **Stato ordine di controllo qualità** mostra lo stato di ogni riga dell'ordine fornitore.

### <a name="from-production-orders"></a>Da ordini di produzione

Per lavorare con gli ordini di controllo qualità correlati ai tuoi ordini di produzione, vai a **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** e quindi segui uno di questi passaggi:

- Apri un ordine di produzione o selezionalo nella griglia. Quindi, nel riquadro azioni, nella scheda **Visualizza**, nel gruppo **Gestisci qualità** , selezionare **Ordini di controllo qualità** per aprire la pagina **Ordini di controllo qualità**. Qui è possibile visualizzare, creare o aggiornare gli ordini di controllo qualità correlati all'ordine di produzione.
- Apri un ordine di produzione o selezionalo nella griglia. Quindi, nel riquadro azioni, nella scheda **Ordine di produzione**, nel gruppo **Dettagli produzione** seleziona **Ciclo di lavorazione** per aprire la pagina **Ciclo di lavorazione produzione**. Per visualizzare gli ordini di controllo qualità relativi a un'operazione di ciclo di lavorazione, attenersi a uno di questi passaggi:

    - Selezionare l'operazione di ciclo di lavorazione di destinazione nella griglia. Quindi, nel riquadro azioni, selezionare **Richiesta di informazioni \> Ordini di controllo qualità**.
    - Seleziona il valore nel campo **Oper. n.** per l'operazione ciclo di lavorazione di destinazione per aprire la relativa pagina dei dettagli **Ciclo di lavorazione produzione**. Nella scheda dettagli **Generale**, il campo **Stato ordine di controllo qualità** mostra lo stato degli ordini di controllo qualità relativi all'operazione di ciclo di lavorazione.

- Apri un ordine di produzione e seleziona il scheda dettaglio **Generale**. Il campo **Stato ordine di controllo qualità** mostra lo stato del gli ordini di controllo qualità correlati all'ordine di produzione.

### <a name="from-quarantine-orders"></a>Da ordini di quarantena

Per lavorare con gli ordini di controllo qualità correlati ai tuoi ordini di quarantena, vai a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di quarantena** e quindi segui uno di questi passaggi:

- Rivedi i valori nella colonna **Stato ordine di controllo qualità**. In questo modo, è possibile apprendere lo stato generale di tutti gli ordini di controllo qualità correlati a ciascun ordine di quarantena nella griglia.
- Selezionare un ordine di quarantena nella griglia e quindi, nel riquadro azioni, selezionare **Ordini di qualità** per visualizzare, creare o aggiornare gli ordini di controllo qualità correlati all'ordine di quarantena.

## <a name="advanced-actions-for-quality-orders"></a>Azioni avanzate per gli ordini di controllo qualità

È possibile eseguire diverse azioni sugli ordini di controllo qualità per gestire lo stato, generare documenti e richiedere ulteriori dettagli.

### <a name="reopen-a-quality-order"></a>Riaprire un ordine di controllo qualità

Per impostazione predefinita, non è più possibile modificare o aggiornare un ordine di controllo qualità dopo che è stato convalidato e i test sono stati superati. Tuttavia, in alcuni casi, potrebbe essere necessario riaprire un ordine di controllo qualità dopo che è stato completato.

Per riaprire un ordine di controllo qualità, attieniti alla procedura seguente:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.
1. Apri un ordine di controllo qualità convalidato o selezionalo nella griglia.
1. Nel riquadro azioni, selezionare **Riapri ordine di controllo qualità**.

### <a name="create-a-certificate-of-analysis-for-a-quality-order"></a>Creare un certificato di analisi per un ordine di controllo qualità

Un CoA è un report generato dal team di garanzia della qualità di un'organizzazione. Convalida che un prodotto soddisfa normative o requisiti specifici. I tuoi clienti o le istituzioni normative nella tua area geopolitica potrebbero richiedere certificati di analisi. Potrebbero anche essere richiesti in base al tuo settore e al tipo di prodotti che gestisci, acquisti, produci o vendi.

Supply Chain Management consente di generare un certificato di analisi da un ordine di controllo qualità. Il report includerà i risultati di tutti i test sull'ordine di controllo qualità in cui l'opzione **Report certificato di analisi** è impostata su *Sì*. Questa opzione può essere impostata per impostazione predefinita, in base al test definito nella pagina **Test**. Tuttavia, è possibile sostituire l'impostazione per test specifici per uno specifico ordine di controllo qualità.

Per generare un CoA per un ordine di controllo qualità, attieniti alla procedura seguente:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.
1. Seleziona l'ordine di controllo qualità per cui desideri creare un certificato di analisi.
1. Nel riquadro azioni selezionare **Richiesta di informazioni \> Certificato di analisi**.
1. Nella pagina  **Certificato di analisi**, nel riquadro azioni seleziona **Nuovo**.
1. Facoltativo: in **Contatto** selezionare la persona di contatto a cui deve essere indirizzato il certificato.
1. Nel riquadro azioni fare clic su **Stampa**.
1. Nella finestra di dialogo **Certificato di analisi**, definire la modalità di stampa del report. Quindi seleziona **OK** per inviare il report a una stampante, allo schermo, su un file o tramite posta elettronica.
1. Chiudere le pagine.

### <a name="block-or-unblock-inventory-for-a-quality-order"></a>Bloccare o sbloccare le scorte per un ordine di controllo qualità

Quando un ordine di controllo qualità viene generato automaticamente da un'associazione di controllo qualità, il campionamento degli articoli assegnato all'associazione di controllo qualità può essere configurato per bloccare l'intera quantità di scorte del riferimento che viene testato. Per ulteriori informazioni sui campionamenti degli articoli, vedere [Campionamento degli articoli per la gestione della qualità](quality-item-sampling.md).

Se non si utilizza il blocco completo o se si sta creando manualmente un ordine di controllo qualità, il sistema crea automaticamente un record di blocco delle scorte per la quantità dell'articolo che viene testata nell'ordine di controllo qualità. Nel record creato nella pagina **Blocco scorte** il campo **Tipo di blocco scorte** è impostato su *Ordine di controllo qualità*.

Per visualizzare e modificare il blocco scorte per un ordine di controllo qualità selezionato nella pagina **Blocco scorte**, selezionare **Richiesta di informazioni \> Blocco scorte** nel riquadro azioni. Per ulteriori informazioni, vedere [Blocco scorte](inventory-blocking.md).

### <a name="inquire-about-the-details-of-a-quality-order"></a>Richiedere informazioni sui dettagli di un ordine di controllo qualità

Utilizzare i seguenti pulsanti nel riquadro azioni della pagina **Ordini di controllo qualità** per visualizzare ulteriori informazioni su o relative a un ordine di controllo qualità:

- **Richieste di informazioni \> Dettagli lavoro** - Apre una pagina in cui è possibile visualizzare il lavoro di magazzino correlato all'ordine di controllo qualità.
- **Richieste di informazioni \> Non conformità** - Apre una pagina in cui è possibile visualizzare eventuali non conformità correlate all'ordine di controllo qualità.
- **Inventario** - I comandi di questo menu sono comuni a tutte le transazioni di magazzino. È possibile utilizzarli per visualizzare o aggiornare dettagli come transazioni, scorte disponibili, prenotazioni e contrassegni.

### <a name="create-cases-related-to-quality-orders"></a>Creare casi relativi agli ordini di controllo qualità

È possibile creare casi correlati agli ordini di controllo qualità. In questo modo, puoi tenere traccia dei dettagli sui problemi e lavorare per una risoluzione. È quindi possibile utilizzare le funzionalità del flusso di lavoro della gestione dei casi per instradare un caso attraverso un processo aziendale predefinito per ottenere ulteriori approvazioni o ottenere maggiori informazioni su un problema specifico. È inoltre possibile utilizzare la funzionalità di file di caratteristiche del caso per creare una knowledge base di soluzioni per problemi comuni.

## <a name="case-management-examples-for-quality-management"></a>Esempi di gestione dei casi per la gestione della qualità

### <a name="example-1"></a>Esempio 1

Lavori per un'azienda manifatturiera che deve seguire rigide normative relative alla produzione di prodotti regolamentati come il cibo. Gli ordini di controllo qualità vengono utilizzati per registrare e tenere traccia dei dettagli sulla qualità degli articoli durante il processo di produzione. Se un ordine di controllo qualità non supera test specifici, potrebbe esserci un problema con l'apparecchiatura. I casi vengono utilizzati per seguire un processo aziendale e riassegnare il problema ai tecnici corretti in modo che sia possibile determinarne la causa principale. Per rendere i processi aziendali più facili da seguire, l'azienda mantiene una knowledge base dei problemi comuni correlati agli ordini di controllo qualità e ai problemi delle apparecchiature.

### <a name="example-2"></a>Esempio 2

Lavori per una società di distribuzione che spedisce prodotti che possono essere personalizzati per vari paesi e aree geografiche. Alcuni clienti hanno specifiche rigorose che devono essere seguite. In caso contrario, potrebbero essere addebitati costi e resi o rifiuti di addebito. Gli ordini di controllo qualità vengono utilizzati per tenere traccia dei dettagli di ogni test e dei risultati che corrispondono ai requisiti del cliente. I casi vengono utilizzati per esaminare e approvare i dettagli per il certificato di analisi prima che il documento venga generato e allegato insieme ad altri documenti di spedizione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Processi di gestione qualità](quality-management-processes.md)
- [Test di qualità](quality-tests.md)
- [Gruppi di test di qualità](quality-test-groups.md)
- [Associazioni di controllo qualità](quality-associations.md)
- [Processi di gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
