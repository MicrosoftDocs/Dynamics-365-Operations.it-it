---
title: ER configura le destinazioni
description: Questa procedura mostra come impostare e utilizzare destinazioni diverse per i componenti di output per la creazione di report elettronici (ER), ad esempio una cartella o un file.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERFormatDestinationTable, SysLookupPicklist, ERFormatDestinationSettings, ERFormatDestinationEmailSettings, ERExpressionDesignerFormula, SRSPrintDestinationTokens
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83c6b8db609b83f94b51800616976eb9ce08d79b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544865"
---
# <a name="er-configure-destinations"></a>ER configura le destinazioni

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come impostare e utilizzare destinazioni diverse per i componenti di output per la creazione di report elettronici (ER), ad esempio una cartella o un file. La società di dati dimostrativi utilizzata per creare questa procedura è DEMF. La Germania è il paese dell'indirizzo principale della persona giuridica, comunque è possibile utilizzare qualsiasi persona giuridica per questa procedura. 

Il formato utilizzato in questo esempio è Bonifico ISO20022, ma è possibile usare qualsiasi formato che sia già stato importato. Questa procedura è un esempio di un'impostazione di destinazione e file singoli. Ulteriori informazioni sulla gestione delle destinazioni per la creazione di report elettronici sono disponibili nella Guida di Dynamics 365 for Finance and Operations.

1. Passare a Amministrazione organizzazione > Creazione di report elettronici > Destinazione report elettronici.
2. Fare clic su Nuovo per creare un nuovo set di destinazioni per un formato.
3. Nel campo Riferimento selezionare un formato per il quale si desidera configurare destinazioni.
    * Se non si deve selezionare un valore, significa che non sono state importate le configurazioni del formato dei report elettronici. È necessario importare una configurazione del formato prima di impostare le destinazioni.  
4. Fare clic su Nuovo per creare una nuova destinazione file.
    * È possibile creare una destinazione del file per ciascun componente di output dello stesso formato, ad esempio una cartella o un file. Sarà possibile abilitare e disabilitare separatamente i destinatari nelle impostazioni.  
5. Nel campo Nome immettere il nome semplice da usare del componente di output.
    * Si consiglia di utilizzare nomi significativi, ad esempio "File di pagamento" o "Report di controllo". Questi nomi verranno presentati agli utenti in fase di runtime della configurazione insieme alle impostazioni di destinazione.  
6. Nel Nome file selezionare un file o una cartella specifica per il formato.
7. Fare clic su Impostazioni.
8. Selezionare Sì nel campo Attivate.
    * La casella di controllo Attivata in ogni scheda abilita e disabilita separatamente ogni destinazione. In questo esempio sarà consentito l'invio di un file di output al destinatario della posta elettronica quando il file verrà generato.  
9. Fare clic su Modifica, per impostare i destinatari di posta elettronica.
10. Scegliere Aggiungi.
11. Fare clic su Gestione stampa posta elettronica.
12. Selezionare un'opzione nel campo Origine posta elettronica.
    * È possibile selezionare diversi tipi di origine di posta elettronica, ad esempio un cliente o un tipo di fornitore. Ciò definisce il tipo di argomento che verrà restituito dalla formula del conto di origine posta elettronica. La formula del conto di origine posta elettronica, descritta in un passaggio successivo, è il punto in cui verrà associata un'origine della posta elettronica. Selezionare Fornitore se la formula restituirà un conto fornitore. Utilizzare Fornitore se si usa l'esempio di configurazione del bonifico ISO 20022.  
13. Fare clic sul pulsante Associa origine posta elettronica.
14. Nella Formula immettere un riferimento specifico per il documento a un tipo di parte selezionato in precedenza.
    * Anziché digitare, è possibile cercare un nodo di origine dati che rappresenti il conto della parte e fare clic sul pulsante Aggiungi origine dati per aggiornare la formula. Ad esempio: se si utilizza la configurazione del bonifico ISO 20022, il nodo che rappresenta un conto fornitore è '$PaymentsForCoveringLetter'.Creditor.Identification.SourceID. In caso contrario, immettere qualsiasi valore di stringa, ad esempio "DE-001" per salvare una formula.  
15. Fare clic su Salva.
16. Chiudere la pagina.
17. Fare clic su Modifica per configurare i dettagli di contatto per la parte.
18. Selezionare Sì nel campo Contatto primario.
    * È possibile utilizzare opzioni diverse per indicare il tipo di contatto della parte da utilizzare come indirizzo di posta elettronica per la destinazione. Utilizziamo il contatto primario in questo esempio.  
19. Fare clic su OK.
20. Fare clic su OK.
21. Digitare un valore nel campo Oggetto.
22. Fare clic su OK.

