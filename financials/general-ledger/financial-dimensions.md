---
title: Dimensioni finanziarie
description: Questo argomento illustra i vari tipi di dimensioni finanziarie e come impostarle.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: b5615a6d9003554593981ce65be0283a249a7d93
ms.contentlocale: it-it
ms.lasthandoff: 08/01/2017

---

# <a name="financial-dimensions"></a>Dimensioni finanziarie

[!include[banner](../includes/banner.md)]

Questo argomento spiega i vari tipi di dimensioni finanziarie e come impostarle.

Utilizzare la pagina **Dimensioni finanziarie** per creare le dimensioni finanziarie che è possibile utilizzare come segmenti di conto per i piani dei conti. Sono disponibili due tipi di dimensioni finanziarie: dimensioni personalizzate e dimensioni supportate da un'entità. Le dimensioni personalizzate sono condivise tra le persone giuridiche e i valori sono immessi e gestiti dagli utenti. Per le dimensioni supportate da un'entità, i valori sono definiti in altre aree del sistema, ad esempio le entità Clienti o Punti vendita. Alcune dimensioni supportate da entità sono condivise tra le persone giuridiche, mentre alcune sono specifiche della società. 

Dopo avere creato le dimensioni finanziarie, utilizzare la pagina **Valori di dimensione finanziaria** per assegnare proprietà aggiuntive a ciascuna dimensione finanziaria. 

È possibile utilizzare le dimensioni finanziarie per rappresentare le persone giuridiche. Non è necessario creare le persone giuridiche in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Tuttavia, le dimensioni finanziarie non sono progettate per soddisfare i requisiti aziendali o operativi delle persone giuridiche. La funzionalità di contabilizzazione interunità in Finance and Operations è stata progettata per gestire solo le voci contabili create da ciascuna transazione. 

Prima di impostare le dimensioni finanziarie come persone giuridiche, valutare i processi aziendali nelle seguenti aree per determinare se questa impostazione verrà eseguita per l'organizzazione:

- Magazzino
- Vendite e acquisti tra le dimensioni finanziarie e le persone giuridiche
- Calcolo IVA e report
- Report operativo

Di seguito sono riportate alcune limitazioni:

- È possibile utilizzare la funzionalità IVA solo con le persone giuridiche, senza dimensioni finanziarie.
- Alcuni report non includono le dimensioni finanziarie. Pertanto, per la dichiarazione per dimensione finanziaria, potrebbe essere necessario modificare il report.

## <a name="custom-dimensions"></a>Dimensioni personalizzate

Per creare una dimensione finanziaria definita dall'utente, nel campo **Usa valori da** selezionare **&lt; Dimensione personalizzata &gt;**. È anche possibile specificare una maschera conto per limitare la quantità e il tipo di informazioni che è possibile immettere per i valori di dimensione. È possibile immettere caratteri rimanenti uguali per ciascun valore di dimensione, ad esempio le lettere o un trattino (-). È inoltre possibile immettere i segni di numero(\#) ed e commerciale (&) come segnaposto per le lettere e i numeri che cambieranno ogni volta che un valore di dimensione viene creato. Utilizzare un segno di numero (\#) come segnaposto per un numero e la e commerciale  (&) come segnaposto per una lettera. Il campo per la maschera formato è disponibile solo se si seleziona **&lt; Dimensione personalizzata &gt;** nel campo **Usa valori da**.

**Esempio**

Per limitare il valore della dimensione alle lettere "CC" e a tre numeri, immettere **CC-\#\#\#** come maschera formato.

## <a name="entity-backed-dimensions"></a>Dimensioni supportate da un'entità

Per creare una dimensione finanziaria supportata da un'entità, nel campo **Usa valori da** selezionare un'entità definita dal sistema su cui basare la dimensione finanziaria. I valori di dimensioni finanziaria vengono creati da questa entità. Ad esempio, per creare i valori di dimensione per i progetti, selezionare **Progetti**. Viene creato un valore di dimensione per ciascun nome di progetto. Verrà visualizzata la pagina **Valori di dimensione finanziaria** con i valori dell'entità. Se questi valori sono specifici della società, la pagina mostra anche la società.

## <a name="activating-dimensions"></a>Attivazione di dimensioni

Se si attiva una dimensione finanziaria, la tabella viene aggiornata in modo da includere il nome della dimensione finanziaria. Le dimensioni eliminate vengono rimosse. È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria. Tuttavia, una dimensione finanziaria non può essere utilizzata finché non viene attivata. Non è possibile ad esempio aggiungere una dimensione finanziaria a una struttura dei conti fino a quando la dimensione non sia stata attivata. Quando si fa clic su **Attiva**, tutte le dimensioni vengono aggiornate e indica le modifiche dello stato. 

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


Per ulteriori informazioni, vedere i seguenti argomenti:
- [Definire dimensioni finanziarie](tasks/define-financial-dimensions.md)
- [Gestire modelli predefiniti di dimensione finanziaria](tasks/maintain-financial-dimension-default-templates.md)

