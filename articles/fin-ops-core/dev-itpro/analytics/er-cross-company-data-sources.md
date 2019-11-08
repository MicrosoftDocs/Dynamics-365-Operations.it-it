---
title: Origini dati interaziendali nella creazione di report elettronici (ER)
description: In questo argomento viene descritto come utilizzare le origini dati interaziendali nella creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: f2e6b4f20464993f736b013dde40527aba2258ed
ms.sourcegitcommit: 564aa8eec89defdbe2abaf38d0ebc4cca3e28109
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "2667646"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>Origini dati interaziendali nella creazione di report elettronici (ER)

[!include[banner](../includes/banner.md)]

È possibile progettare formati di report elettronici (ER) per generare documenti in uscita in vari formati. Quando viene generato un documento, un formato di ER chiama le origini dati che sono state configurate in un mapping di modelli di ER corrispondente. Per configurare l'accesso alle tabelle dell'applicazione per il recupero di record, è possibile utilizzare le origini dati di ER di tipo **Record di tabella**. Quando la tabella cui di deve accedere è condivisa (vale a dire una tabella in cui i dati sono salvati senza un identificatore della società), questa origine dati restituisce tutti i record. Quando la tabella di accesso è una tabella dipendente dalla società (vale a dire una tabella in cui i dati vengono salvati per società), l'origine dati restituisce solo i record che sono stati salvati per la società corrente (vale a dire il contesto aziendale in cui viene eseguito il formato di ER).

Ogni origine dati di tipo **Record di tabella** in un mapping di modello può a questo punto essere contrassegnata come origine dati interaziendale. Si può quindi utilizzare le origini dati di tipo **Record di tabella** per accedere ai dati interaziendali nelle tabelle dell'applicazione.

Se si contrassegna un'origine dati come interaziendale, si verifica il comportamento seguente:

- Per un'origine dati che fa riferimento a una qualsiasi tabella condivisa eccetto CompanyInfo, l'origine dati restituisce tutti i record presenti nella tabella di riferimento. 
- Per un'origine dati che fa riferimento alla tabella CompanyInfo, anche se CompanyInfo è una tabella condivisa, l'origine dati restituisce i record contenenti l'identificatore di una società dall'ambito definito.
- Per qualsiasi tabella dipendente dalla società, l'origine dati restituisce i record della tabella di riferimento che contengono l'identificatore di una società dall'ambito definito.

Nella finestra di dialogo delle query di sistema, quando l'opzione **Chiedi query** è attivata per una qualsiasi origine dati che è contrassegnata come interaziendale, è possibile selezionare manualmente una o più società da includere nella scheda **Intervallo società**.

> [!IMPORTANT]
> Come altri filtri, il filtro dalla società è persistente come valore utilizzato per ultimo per le query quando si esegue un formato di ER. Il filtro non cambia automaticamente se si modifica il valore interaziendale per un'origine dati. Per utilizzare un valore interaziendale diverso per un'altra origine dati, eliminare la selezione specifica dell'utente corrispondente.

Per ogni origine dati contrassegnata come interaziendale, è possibile selezionare i record desiderati utilizzando le funzioni **FILTER** e **WHERE** nelle espressioni di ER. Anche il campo **dataAreaID** viene utilizzato come identificatore di società. Attualmente, il campo **dataAreaID** è limitato ai seguenti tipi di condizioni quando viene utilizzata la funzione **FILTER**:

- Sono supportate solo le condizioni che hanno un singolo confronto del campo **dataAreaID**.
- Sono consentiti solo i confronti con espressioni che non dipendono da elementi dell'elenco di record.

L'espressione seguente è pertanto valida.

```
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

Per impostazione predefinita, l'ambito include tutte le società dell'applicazione corrente. Tuttavia, è possibile limitarlo. Per limitare l'ambito di accesso ai dati interaziendali per un formato di ER, assegnare una gerarchia organizzativa specifica al formato. Quando una gerarchia viene definita per un formato di ER, vengono restituiti solo i record per le persone giuridiche presentate nella gerarchia assegnata, anche se il formato chiama origini dati interaziendali. Quando si definisce un riferimento a una gerarchia non più disponibile per un formato di ER, viene applicato l'ambito predefinito e il formato chiama origini dati interaziendali. In questo caso, vengono restituiti i record di tutte le società dell'applicazione.

Quando l'opzione **Usa bozza** viene attivata per una gerarchia organizzativa assegnata a un singolo formato di ER, le persone giuridiche dalla versione bozza di questa gerarchia verranno utilizzate per identificare l'ambito per le origini dati interaziendali. Se la versione bozza non è disponibile, verranno utilizzate le persone giuridiche dell'ultima versione pubblicata della gerarchia organizzativa.

Quando l'opzione **Usa bozza** viene disattivata per una gerarchia organizzativa assegnata a un singolo formato di ER, le persone giuridiche dall'ultima versione pubblicata di questa gerarchia organizzativa verranno utilizzate per identificare l'ambito per le origini dati interaziendali. La validità delle date per le gerarchie organizzative non è ancora supportata nel framework di ER.

La gerarchia può essere assegnata a un formato in una pagina specifica a cui è possibile accedere dall'area di lavoro di ER o scegliendo **Amministrazione organizzazione \> Creazione di report elettronici \> Filtro persona giuridica per i formati**. Per accedere alla pagina, all'utente deve essere concesso il privilegio **Mantieni filtri persona giuridica per i formati** (ERMaintainFormatMappingLegalEntityFilters). La restrizione dell'ambito delle persone giuridiche basate sulla gerarchia per il formato viene applicata insieme alla restrizione che l'utente può specificare manualmente nella finestra di dialogo di query del sistema. L'intersezione di queste restrizioni viene utilizzata quando il formato viene eseguito.

Per ulteriori informazioni su questa funzionalità, riprodurre la guida attività **ER Accedere ai record di tabelle dipendenti dalla società nella modalità interaziendale**, che fa parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677) e che può essere scaricata dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Questa guida attività illustra in dettaglio il processo di configurazione di un mapping di modello di ER e il formato ER per accedere alle tabelle dell'applicazione nella modalità interaziendale.

Scaricare i seguenti file per completare la guida attività:

- [Configurazione del modello di ER - CrossCompanyDataAccessModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Configurazione del formato di ER - CrossCompanyDataAccessFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)
