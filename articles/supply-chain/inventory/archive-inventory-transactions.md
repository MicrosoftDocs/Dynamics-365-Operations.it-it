---
title: Archiviare le transazioni di magazzino
description: In questo argomento viene descritto come archiviare i dati delle transazioni di magazzino per migliorare le prestazioni del sistema.
author: yufeihuang
ms.date: 05/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8b766d306f31fc531f33aa29e1f96048bbd90085
ms.sourcegitcommit: e18ea2458ae042b7d83f5102ed40140d1067301a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8736063"
---
# <a name="archive-inventory-transactions"></a>Archiviare le transazioni di magazzino

[!include [banner](../../includes/banner.md)]

Nel tempo, la tabella delle transazioni di magazzino (`InventTrans`) continuerà a crescere e a utilizzare più spazio nel database. Pertanto, le query eseguite sulla tabella diventeranno gradualmente più lente. In questo argomento viene descritto come utilizzare la funzionalità *Archivio transazioni di magazzino* per archiviare i dati relativi alle transazioni di magazzino e migliorare le prestazioni del sistema.

> [!NOTE]
> Solo le transazioni di magazzino aggiornate finanziariamente possono essere archiviate in un periodo contabile chiuso selezionato. Per essere archiviate, le transazioni di magazzino in uscita aggiornate finanziariamente devono avere lo stato *Venduto* e le transazioni di magazzino in entrata devono avere lo stato *Acquistato*.

Quando si archiviano transazioni di magazzino, tutte le transazioni correlate vengono spostate nella tabella `InventTransArchive`. Le transazioni di magazzino in uscita e quelle in entrata sono archiviate separatamente, in base alla combinazione di ID articolo (`itemId`) e ID dimensione inventario (`inventDimId`) e sono inserite nel riepilogo delle transazioni in uscita e in entrata.

Se una combinazione di `itemId` e `inventDimId` contiene solo una transazione in entrata o in uscita, la transazione non verrà archiviata.

## <a name="turn-on-the-feature-in-your-system"></a>Attiva la funzionalità nel tuo sistema

Se il sistema in uso non include già le funzionalità descritte in questo argomento, vedere [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attivare la funzionalità *Archivio transazioni di magazzino*. Da notare che questa funzionalità non può essere disabilitata una volta abilitata.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Aspetti da considerare prima di archiviare le transazioni di magazzino

Prima di archiviare le transazioni di magazzino, è necessario considerare i seguenti scenari aziendali, poiché saranno interessati dall'operazione:

- Quando si controllano le transazioni di magazzino di documenti correlati, come righe di ordine fornitore, queste verranno visualizzate come archiviate. Per esaminare le transazioni archiviate, selezionare **Gestione articoli \> Attività periodiche \> Pulisci \> Archivio transazioni di magazzino**.
- La chiusura dell'inventario non può essere annullata per periodi archiviati. Per poter annullare la chiusura di un inventario, è necessario stornare l'archivio delle transazioni di magazzino per il periodo pertinente.
- La conversione in costo standard non può essere eseguita per periodi archiviati. Per poter eseguire la conversione in costo standard, è necessario stornare l'archivio delle transazioni di magazzino per il periodo pertinente.
- I report relativi alle scorte originati da transazioni di magazzino verranno modificati quando si archiviano le transazioni di magazzino. Questi report includono il report sull'aging delle scorte e i rapporti sui valori di inventario.
- Le previsioni di magazzino potrebbero essere alterate se vengono eseguite durante l'orizzonte temporale dei periodi archiviati.

## <a name="prerequisites"></a>Prerequisiti

Le transazioni di magazzino possono essere archiviate solo durante i periodi in cui vengono soddisfatte le seguenti condizioni:

- Il periodo contabile deve essere chiuso.
- La chiusura dell'inventario deve essere eseguita alla data di fine periodo dell'archivio o successivamente.
- Il periodo deve essere almeno un anno prima della data di inizio periodo dell'archivio.
- Non devono esistere ricalcoli di inventario.

## <a name="archive-inventory-transactions"></a>Archiviare transazioni di magazzino

Per archiviare transazioni di magazzino, attenersi alla seguente procedura.

1. Selezionare **Gestione articoli** \> **Attività periodiche** \> **Pulisci** \> **Archivio transazioni di inventario**.

    Viene visualizzata la pagina **Archivio transazioni di magazzino** con un elenco dei record di processo archiviati.

    ![Pagina Archivio transazioni di magazzino.](media/archive-inventory-empty.png "Pagina Archivio transazioni di magazzino")

1. Nel riquadro Azioni selezionare **Archivio transazioni di magazzino** per creare un archivio delle transazioni di magazzino.
1. Nella finestra di dialogo **Archivio transazioni di magazzino**, nella scheda dettaglio **Parametri**, impostare i seguenti campi:

    - **Data di inizio del periodo contabile chiuso** - Selezionare la data della prima transazione da includere nell'archivio.
    - **Data di fine del periodo contabile chiuso** - Selezionare la data dell'ultima transazione da includere nell'archivio.

    ![Finestra di dialogo Archivio transazioni di magazzino.](media/archive-inventory-dates.png "Finestra di dialogo Archivio transazioni di magazzino")

    > [!NOTE]
    > Solo i periodi che soddisfano i [prerequisiti](#prerequisites) saranno selezionabili.

1. Nella Scheda dettaglio **Esecuzione in background**, impostare i dettagli dell'elaborazione batch come necessario. Seguire i passaggi usuali per i processi batch in Microsoft Dynamics 365 Supply Chain Management.
1. Selezionare **OK**.
1. Viene visualizzato un messaggio che richiede di confermare se si desidera continuare. Leggere attentamente il messaggio, quindi selezionare **Sì** per continuare.

    Viene visualizzato un messaggio che informa che il processo di archiviazione delle transazioni di magazzino è stato aggiunto alla coda batch. Il processo inizierà ad archiviare le transazioni di magazzino del periodo selezionato.

## <a name="view-archived-inventory-transactions"></a>Visualizza transazioni di magazzino archiviate

La pagina **Archivio transazioni di magazzino** mostra la cronologia di archiviazione completa. Ogni riga della griglia mostra informazioni come la data in cui l'archivio è stato creato, l'utente che lo ha creato e il relativo stato.

![Cronologia di archiviazione nella pagina Archivio transazioni di magazzino.](media/archive-inventory-full.png "Cronologia di archiviazione nella pagina Archivio transazioni di magazzino")

Nell'elenco a discesa nella parte superiore della pagina selezionare uno dei seguenti valori per filtrare gli archivi visualizzati nella griglia:

- **Attivi** - Mostra solo gli archivi attivi, non gli archivi stornati.
- **Tutti** - Mostra tutti gli archivi, sia attivi che stornati.

Per ogni archivio nella griglia vengono fornite le seguenti informazioni:

- **Attivo** - Un segno di spunta indica che l'archivio è attivo.
- **Data iniziale** - La data della transazione più vecchia che può essere inclusa nell'archivio.
- **Data finale** - La data della transazione più recente che può essere inclusa nell'archivio.
- **Programmato da** - L'account utente che ha creato l'archivio.
- **Elaborato** - La data di creazione dell'archivio.
- **Storno** - Un segno di spunta indica che l'archivio è stato stornato.
- **Interrompi aggiornamento corrente** - Un segno di spunta indica che l'archiviazione è in corso, ma che è stata sospesa.
- **Stato** - Lo stato di elaborazione dell'archivio. I valori possibili sono *In attesa*, *In corso* e *Finito*.

La barra degli strumenti sopra la griglia include i seguenti pulsanti utilizzabili con un archivio selezionato:

- **Transazioni archiviate** - Visualizza i dettagli completi dell'archivio selezionato. La pagina **Transazioni archiviate** visualizzata mostra tutte le transazioni presenti nell'archivio.

    ![Pagina Transazioni archiviate.](media/archive-inventory-transactions.png "Pagina Transazioni archiviate")

    Per visualizzare ulteriori informazioni su una transazione specifica nella pagina **Transazioni archiviate**, selezionarla nella griglia, quindi, nel riquadro azioni, selezionare **Dettagli transazione archiviata**. La pagina **Dettagli transazione archiviata** visualizzata mostra informazioni quali la registrazione contabile, i riferimenti della contabilità secondaria correlati e le dimensioni finanziarie.

- **Sospendi archiviazione** - Sospende un archivio selezionato che è attualmente in fase di elaborazione. La sospensione viene attivata solo dopo la generazione dell'attività di archiviazione. Pertanto, potrebbe esserci un breve ritardo prima della sospensione dell'archiviazione. Se un archivio è stato sospeso, viene visualizzato un segno di spunta nel campo **Interrompi aggiornamento corrente**.
- **Riprendi archiviazione** - Riprende l'elaborazione di un archivio selezionato attualmente sospeso.
- **Storno** - Esegue lo storno dell'archivio selezionato. È possibile stornare un archivio solo se il campo **Stato** è impostato su *Finito*. Se un archivio è stato stornato, viene visualizzato un segno di spunta nel campo **Storno**.

## <a name="extend-your-code-to-support-custom-fields"></a>Estendere il codice per supportare i campi personalizzati

Se la tabella `InventTrans` contiene uno o più campi personalizzati, potrebbe essere necessario estendere il codice per supportarli, a seconda di come sono denominati.

- Se i campi personalizzati della tabella `InventTrans` hanno gli stessi nomi dei campi nella tabella `InventtransArchive`, ciò significa che sono mappati 1:1. Pertanto, è possibile inserire semplicemente i campi personalizzati nel gruppo di campi `InventoryArchiveFields` della tabella `inventTrans`.
- Se i nomi dei campi personalizzati nella tabella `InventTrans` non corrispondono ai nomi dei campi nella tabella `InventtransArchive`, è necessario aggiungere il codice per mapparli. Ad esempio, se si dispone di un campo di sistema chiamato `InventTrans.CreatedDateTime`, è necessario creare un campo nella tabella `InventTransArchive` con un nome diverso (come `InventtransArchive.InventTransCreatedDateTime`) e aggiungere le estensioni alle classi `InventTransArchiveProcessTask` e `InventTransArchiveSqlStatementHelper`, come illustrato nel codice di esempio seguente.

Nel seguente codice di esempio viene illustrato un modo per aggiungere l'estensione richiesta alla classe `InventTransArchiveProcessTask`.

```xpp
[ExtensionOf(classStr(InventTransArchiveProcessTask))]
Final class InventTransArchiveProcessTask_Extension
{

    protected void addInventTransFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTrans, ModifiedBy))
            .add(fieldStr(InventTrans, CreatedBy)).add(fieldStr(InventTrans, CreatedDateTime));

        next addInventTransFields(_selectionObject);
    }


    protected void addInventTransArchiveFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTransArchive, InventTransModifiedBy))
            .add(fieldStr(InventTransArchive, InventTransCreatedBy)).add(fieldStr(InventTransArchive, InventTransCreatedDateTime));

        next addInventTransArchiveFields(_selectionObject);
    }
}
```

Nel seguente codice di esempio viene illustrato un modo per aggiungere l'estensione richiesta alla classe `InventTransArchiveSqlStatementHelper`.

```xpp
[ExtensionOf(classStr(InventTransArchiveSqlStatementHelper))]
final class InventTransArchiveSqlStatementHelper_Extension
{
    private str     inventTransModifiedBy;  
    private str     inventTransCreatedBy;
    private str     inventTransCreatedDateTime;

    protected void initialize()
    {
        next initialize();
        inventTransModifiedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, ModifiedBy)).name(DbBackend::Sql);
        inventTransCreatedDateTime = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedDateTime)).name(DbBackend::Sql);
        inventTransCreatedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedBy)).name(DbBackend::Sql);
    }

    protected str buildInventTransArchiveSelectionFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransArchiveSelectionFieldsStatement();
        
        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransModifiedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedDateTime)).name(DbBackend::Sql));
        }

        return ret;
    }

    protected str buildInventTransTargetFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransTargetFieldsStatement();

        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransModifiedBy);
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedBy);
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedDateTime);
        }

        return ret;
    }
}
```
