---
title: Dimensioni finanziarie
description: Questo argomento illustra i vari tipi di dimensioni finanziarie e come impostarle.
author: aprilolson
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ems.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 0715d3e4e4cb167c55d9c7d98cdf599187bf3b43
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444899"
---
# <a name="financial-dimensions"></a>Dimensioni finanziarie

[!include [banner](../includes/banner.md)]

Questo argomento spiega i vari tipi di dimensioni finanziarie e come impostarle.

Utilizzare la pagina **Dimensioni finanziarie** per creare le dimensioni finanziarie che è possibile utilizzare come segmenti di conto per i piani dei conti. Sono disponibili due tipi di dimensioni finanziarie: dimensioni personalizzate e dimensioni supportate da un'entità. Le dimensioni personalizzate sono condivise tra le persone giuridiche e i valori sono immessi e gestiti dagli utenti. Per le dimensioni supportate da un'entità, i valori sono definiti in altre aree del sistema, ad esempio nelle entità Clienti o Punti vendita. Alcune dimensioni supportate da entità sono condivise tra le persone giuridiche, mentre alcune sono specifiche della società.

Dopo avere creato le dimensioni finanziarie, utilizzare la pagina **Valori di dimensione finanziaria** per assegnare proprietà aggiuntive a ciascuna dimensione finanziaria.

È possibile utilizzare le dimensioni finanziarie per rappresentare le persone giuridiche. Non è necessario creare le persone giuridiche in Dynamics 365 Finance. Tuttavia, le dimensioni finanziarie non sono progettate per soddisfare i requisiti aziendali o operativi delle persone giuridiche. La funzionalità di contabilità interunità in Finance è stata progettata per inviare solo le voci contabili create da ciascuna transazione.

Prima di impostare le dimensioni finanziarie come persone giuridiche, valutare i processi aziendali nelle seguenti aree per determinare se questa impostazione verrà eseguita per l'organizzazione:

- Magazzino
- Vendite e acquisti tra le dimensioni finanziarie e le persone giuridiche
- Calcolo IVA e report
- Report operativo

Di seguito sono riportate alcune limitazioni:

- È possibile utilizzare la funzionalità IVA solo con le persone giuridiche, senza dimensioni finanziarie.
- Alcuni report non includono le dimensioni finanziarie. Pertanto, per la dichiarazione per dimensione finanziaria, potrebbe essere necessario modificare il report.

## <a name="custom-dimensions"></a>Dimensioni personalizzate

Per creare una dimensione finanziaria definita dall'utente, nel campo **Usa valori da** selezionare **Dimensione personalizzata**.

È anche possibile specificare una maschera conto per limitare la quantità e il tipo di informazioni che è possibile immettere per i valori di dimensione. È possibile immettere caratteri rimanenti uguali per ciascun valore di dimensione, ad esempio le lettere o un trattino (-). È inoltre possibile immettere i segni di numero (\#) ed e commerciale (&) come segnaposto per i caratteri che cambieranno ogni volta che un valore di dimensione viene creato. Utilizzare un segno di numero (\#) come segnaposto per un numero e la e commerciale  (&) come segnaposto per una lettera. Il campo per la maschera formato è disponibile solo se si seleziona **Dimensione personalizzata** nel campo **Usa valori da**.

**Esempio**

Per limitare il valore della dimensione alle lettere "CC" e a tre numeri, immettere **CC-\#\#\#** come maschera formato.

## <a name="entity-backed-dimensions"></a>Dimensioni supportate da un'entità

Per creare una dimensione finanziaria supportata da un'entità, nel campo **Usa valori da** selezionare un'entità definita dal sistema su cui basare la dimensione finanziaria. I valori di dimensioni finanziaria vengono creati da questa entità. Ad esempio, per creare i valori di dimensione per i progetti, selezionare **Progetti**. Viene creato un valore di dimensione per ciascun nome di progetto. Verrà visualizzata la pagina **Valori di dimensione finanziaria** con i valori dell'entità. Se questi valori sono specifici della società, la pagina mostra anche la società.

## <a name="activating-dimensions"></a>Attivazione di dimensioni

Se si attiva una dimensione finanziaria, la tabella viene aggiornata in modo da includere il nome della dimensione finanziaria. Le dimensioni eliminate vengono rimosse. È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria. Tuttavia, una dimensione finanziaria non può essere utilizzata finché non viene attivata. Non è possibile ad esempio aggiungere una dimensione finanziaria a una struttura dei conti fino a quando la dimensione non sia stata attivata. Quando si seleziona **Attiva**, tutte le dimensioni vengono aggiornate e vengono mostrate le modifiche dello stato.

## <a name="translations"></a>Traduzioni

Nella pagina **Traduzione testo**, è possibile immettere il testo per la dimensione finanziaria selezionata in diverse lingue. Nella pagina **Conversione conto principale**, è possibile immettere il testo per il conto principale in diverse lingue. 

## <a name="legal-entity-overrides"></a>Sostituzioni persona giuridica

Non tutte le dimensioni sono valide per tutte le persone giuridiche. Inoltre, alcune dimensioni potrebbero essere pertinenti solo per un periodo specifico. In questi casi, è possibile usare la sezione **Sostituzioni persona giuridica** per specificare quali sono le società per cui è necessario sospendere la dimensione, l'identità del proprietario e il periodo di tempo durante il quale la dimensione è attiva.

## <a name="deleting-financial-dimensions"></a>Eliminazione di dimensioni finanziarie

Per contribuire a garantire l'integrità referenziale dei dati, le dimensioni finanziarie possono essere eliminate raramente. Se si tenta di eliminare una dimensione finanziaria, i seguenti criteri vengono valutati:

- La dimensione finanziaria è stata utilizzata nelle transazioni registrate o non registrate o in un tipo di combinazione di valori di dimensione?
- La dimensione finanziaria è utilizzata in una struttura dei conti attiva, una struttura di regole avanzate o un set di dimensioni finanziarie?
- La dimensione finanziaria fa parte di un formato di integrazione predefinito della dimensione finanziaria?
- La dimensione finanziaria è stata impostata come dimensione predefinita?

Se uno dei criteri viene soddisfatto, non sarà possibile eliminare la dimensione finanziaria.

## <a name="default-dimension-values"></a>Valori di dimensione predefiniti

È possibile utilizzare i valori dei record di dati master, ad esempio cliente e fornitore, come valori predefiniti nelle nuove dimensioni. Quando vengono create le nuove dimensioni, l'ID record master viene immesso nei valori delle dimensioni per i record di dati master. Quando ad esempio si crea un nuovo cliente, l'ID cliente viene immesso nella dimensione del cliente. Quando si creano ordini cliente, fatture o altri documenti che necessitano di un ID cliente, vengono utilizzate le regole delle impostazioni predefinite esistenti e l'ID cliente viene aggiunto al documento.

Questa funzionalità è controllata da un'impostazione nella dimensione. Questa impostazione è denominata **Copiare i valori nella dimensione per ogni nuovo NomeDimensione creato**, dove **NomeDimensione** è il nome della dimensione. Per impostazione predefinita, la funzionalità è disattivata. Tuttavia, è possibile attivarla in qualsiasi momento.

Se esistono già record per la dimensione, i record master vengono aggiornati quando viene attivata la funzionalità. Tuttavia, i documenti e le transazioni esistenti non vengono aggiornati.

Se si utilizza un modello per creare un record master, verificare che il valore del modello per la dimensione master sia vuoto. Ad esempio, se si creano clienti da un modello, verificare che la dimensione del cliente nel modello sia vuota. Il valore della dimensione del cliente passerà dal nuovo numero di cliente a quello predefinito quando si crea il nuovo cliente.  

## <a name="derived-dimensions"></a>Dimensioni derivate

È possibile configurare una dimensione in modo che le informazioni per altre dimensioni vengano inserite automaticamente quando si immette la dimensione in un documento. Ad esempio, se si immette il centro di costo 10, un valore **20** può essere inserito automaticamente nella dimensione del reparto.

È possibile impostare i valori derivati nella pagina delle dimensioni.

1. Selezionare una dimensione e quindi selezionare **Dimensioni derivate**.

    La pagina **Dimensioni derivate** include una griglia. Il segmento di dimensione selezionato è la prima colonna nella griglia.

2. Aggiungere i segmenti che devono essere derivati. Ogni segmento appare come una colonna.

Immettere le combinazioni di dimensioni che devono essere derivate dalla dimensione nella prima colonna. Ad esempio, per utilizzare il centro di costo come dimensione da cui vengono derivati il reparto e l'ubicazione, immettere centro di costo 10, reparto 20 e ubicazione 30. In seguito, quando si immette il centro di costo 10 in un record master o in una pagina di transazione, il reparto 20 e l'ubicazione 30 vengono immessi per impostazione predefinita.

### <a name="overriding-existing-values-with-derived-dimensions"></a>Sostituire i valori esistenti con dimensioni derivate
 
Per impostazione predefinita, Il processo delle dimensioni derivate non sostituisce i valori esistenti per le dimensioni derivate. Se ad esempio si immette il centro di costo 10 e non si immettono altre dimensioni, il reparto 20 e l'ubicazione 30 vengono immessi per impostazione predefinita. Tuttavia, se si modifica il centro di costo, i valori che sono già stati stabiliti non vengono modificati. Di conseguenza, è possibile impostare le dimensioni predefinite nei record master e le dimensioni non verranno modificate dalle dimensioni derivate.

È possibile modificare il comportamento delle dimensioni derivate per sostituire i valori esistenti selezionando la casella  controllo **Sostituire i valori di dimensione esistenti con valori derivati** nella pagina **Dimensioni derivate**. Se questo campo è selezionato, è possibile immettere una dimensione con i valori delle dimensioni derivate e tali valori di dimensioni derivate sostituiranno tutti i valori già presenti. Utilizzando l'esempio precedente, se si immette il centro di costo 10 e non si immettono altre dimensioni, il reparto 20 e l'ubicazione 30 vengono immessi per impostazione predefinita. Tuttavia, se i valori erano già reparto 50 e l'ubicazione 60, i valori verranno modificati nel reparto 20 e nell'ubicazione 30.
 
Le dimensioni derivate con questa impostazione non sostituiscono automaticamente i valori di dimensioni predefinite esistenti quando i valori delle dimensioni vengono assunti per impostazione predefinita. I valori delle dimensioni verranno sostituiti solo solo se si immette un nuovo valore di dimensione in una pagina e ci sono valori derivati esistenti per la dimensione nella pagina.

### <a name="preventing-changes-with-derived-dimensions"></a>Impedire le modifiche alle dimensioni derivate
 
Quando si utilizza **Aggiungi segmento"** nella pagina **Dimensioni derivate** per aggiungere un segmento come dimensione derivata, un'opzione viene fornita nella parte inferiore della pagina **Aggiungi segmento** che consente di impedire modifiche alla dimensione quando viene derivata in una pagina. L'impostazione predefinita è non selezionata, in modo che non impedisce la modifica dei valori di dimensioni derivate. Cambiare l'Impostazione su **Sì** se si desidera impedire la modifica della dimensione dopo che è stato derivata. Ad esempio, se il valore della dimensione del reparto è derivato dal valore della dimensione centro di costo, il valore del reparto non può essere modificato se il campo **Impedisci modifiche** è **Sì**. 
 
Questa impostazione non impedisce le modifiche se il valore di dimensione è valido ma non è presente nell'elenco di dimensioni derivate. Ad esempio, se il reparto 20 deriva dal centro di costo 10 e si immette il centro di costo 10, allora non si potrà modificare il reparto 20. Tuttavia, se si immette il centro di costo 20 e non è presente nell'elenco delle dimensioni derivate per il centro di costo, è possibile modificare il valore del reparto. 
 
In tutti i casi, il valore del conto e tutti i valori di dimensioni ancora verranno convalidati rispetto alle strutture dei conti dopo l'applicazione dei valori delle dimensioni derivate. Se si utilizza le dimensioni derivate e la convalida ha esito negativo quando utilizzate in una pagina, è necessario modificare i valori delle dimensioni derivae nella pagina relativa prima di utilizzarli nelle transazioni. 
 
Quando si modificano le dimensioni nella scheda dettaglio **Dimensioni  finanziarie**, la dimensione contrassegnata per impedire modifiche non è modificabile. Se si immettono un conto e le dimensioni nel controllo di voci segmentato di una pagina, le dimensioni sono modificabili. Tuttavia, quando si sposta l'evidenziazione dal controllo di voci segmentato su un altro campo o si esegue un'azione, il conto e le dimensioni verranno convalidati rispetto all'elenco di dimensioni derivate e le strutture dei conti per assicurare di avere immesso i valori appropriati. 

### <a name="derived-dimensions-and-entities"></a>Dimensioni derivate ed entità

È possibile impostare i segmenti e i valori di dimensioni derivate tramite le entità.

- L'entità dimensioni derivate imposta le dimensioni moventi e i segmenti utilizzati per tali dimensioni.
- L'entità del valore delle dimensioni derivate consente di importare i valori che dovrebbero essere derivati per ogni dimensione movente.

Quando si utilizza un'entità per l'importazione dei dati, se tale entità importa dimensioni, vengono applicate le regole delle dimensioni derivate durante l'importazione a meno che l'entità non sostituisca specificamente tali dimensioni.

Per ulteriori informazioni, vedere i seguenti argomenti:

- [Definire dimensioni finanziarie](tasks/define-financial-dimensions.md)
- [Gestire modelli predefiniti di dimensione finanziaria](tasks/maintain-financial-dimension-default-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]