---
title: Utilizzare un percorso relativo nelle associazioni dati dei modelli e dei formati ER
description: Lo strumento di creazione di report elettronici (ER) consente agli utenti di definire le strutture dei formati elettronici e quindi descrivere come tali strutture devono essere riempite utilizzando dati e algoritmi disponibili nell'applicazione.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c08e81b6e2983a8f16104698944820e93ba3852d
ms.sourcegitcommit: 139c8007e68d279d7ca9aa302598217522abb8cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2020
ms.locfileid: "3331326"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>Utilizzare un percorso relativo nelle associazioni dati dei modelli e dei formati ER

[!include[banner](../includes/banner.md)]

Lo strumento di creazione di report elettronici (ER) consente agli utenti di definire le strutture dei formati elettronici e quindi descrivere come tali strutture devono essere riempite utilizzando dati e algoritmi disponibili nell'applicazione. Per ulteriori informazioni, vedere [Creare configurazioni di creazione di report elettronici (ER)](electronic-reporting-configuration.md). Per specificare il flusso dati per il recupero dei dati di Finance and Operations e utilizzarlo per generare un documento elettronico, è necessario effettuare le seguenti operazioni:

- Associare le origini dati configurate agli elementi del [modello di dati](general-electronic-reporting.md#data-model-and-model-mapping-components) specifico del dominio progettato. La struttura di modello e le origini dati selezionate potrebbero far parte di una struttura gerarchica complessa. Per questo motivo, le associazioni finali possono essere molto grandi e contenere molti elementi di vari tipi (ad esempio relazioni, tabelle e metodi). Le associazioni possono diventare meno leggibili e molto difficili da esaminare e comprendere, in particolare per i non proprietari. 
- Associare gli elementi del modello di dati ai componenti di [formato](general-electronic-reporting.md#FormatComponentOutbound) per definire quali dati verranno inseriti dal modello di dati nell'output del formato generato.

Per migliorare la possibilità di utilizzo delle progettazioni di mapping di modello, è stata introdotta la funzionalità del [percorso relativo](er-formula-language.md#relative-path). Per impostazione predefinita, l'opzione di rappresentazione del percorso è attivata per qualsiasi nuova istanza dell'applicazione dove l'esperienza di progettazione ER è abilitata (Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service). Abbiamo implementato il parametro del percorso relativo di modo che gli utenti possano continuare a utilizzare il percorso completo quando utilizzano questa presentazione delle associazioni ER.

[![Parametri utente](./media/relative-path-01.png)](./media/relative-path-01.png)

 
Quando il parametro di utilizzo del percorso relativo è attivato, un singolo carattere @ sostituisce il percorso all'articolo padre nell'associazione dell'elemento del modello corrente. L'intero percorso di associazione diventa più breve, rendendo l'intero mapping più ovvio e di più facile comprensione. Nella maggior parte dei casi, non è necessario un ulteriore scorrimento nella progettazione ER per visualizzare tutte le associazioni del modello di dati.

[![Progettazione mapping modello](./media/relative-path-02.png)](./media/relative-path-02.png)
 
Quando si avvia la progettazione di una nuova espressione ER, è necessario immettere solo un carattere per definire un'associazione a un campo dell'articolo padre.

[![Designer formula](./media/relative-path-03.png)](./media/relative-path-03.png)
 
Quando si decide di modificare l'origine dati dell'articolo del modello padre, con l'utilizzo del percorso assoluto, è necessario associare di nuovo manualmente questo articolo del modello, nonché tutti gli articoli nidificati, a una nuova origine dati. Quando l'utilizzo del percorso relativo è attivato e si seleziona una nuova origine dati da associare a un articolo padre, viene visualizzata un'opzione per associare automaticamente tutti gli elementi nidificati di questo articolo padre con un clic.

[![Sostituire il messaggio del percorso esistente](./media/relative-path-04.png)](./media/relative-path-04.png)
 
Se si conferma la nuova associazione degli articoli nidificati, il nuovo articolo padre sarà posizionato nel percorso di ogni articolo nidificato contenente l'articolo padre esistente.
Questa funzionalità non annulla la compatibilità con le versioni precedenti del framework ER. Tutte le configurazioni ER progettate in precedenza potranno essere utilizzate con questa nuova funzionalità e non saranno necessari aggiornamenti o conversioni.

> [!NOTE]
> Tutte le modifiche introdotte dalla modifica di massa delle associazioni di elementi nidificati nei mapping di modelli vengono salvate correttamente in un delta di configurazione (traccia di modifiche). Ciò consente ai clienti di riassegnare la relativa versione derivata dei mapping di modello a qualsiasi nuova versione di base modificata utilizzando questa nuova funzionalità.

## <a name="additional-resources"></a>Risorse aggiuntive

[Linguaggio della formula ER](er-formula-language.md)
