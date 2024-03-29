---
title: 'ER Usare file di gestione documenti in output di formato (Parte 1: Preparare il modello dati)'
description: In questo articolo viene descritto come configurare un formato di reporting elettronico (ER) per utilizzare i file di gestione dei documenti (allegati) nell'output ER. (Parte 1)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form:
- ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
- ERSolutionTable, ERSolutionCreateDropDialog
ms.openlocfilehash: f407555eca4c4bd08d09047e9d8f8512cb99d254
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291026"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>ER Usare file di gestione documenti in output di formato (Parte 1: Preparare il modello dati)

[!include [banner](../../includes/banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici. Questi passaggi possono essere eseguiti in qualsiasi società.

Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Ottenere l'accesso all'elenco delle configurazioni fornite da Microsoft
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.

    Assicurarsi che il provider Litware, Inc. sia disponibile e contrassegnato come attivo.  

2. Selezionare il provider Litware, Inc .
3. Fare clic su Archivi.

    Se un archivio di tipo 'Risorse operative' esiste già, ignorare i passaggi restanti della sottoattività corrente.  

4. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
5. Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.
6. Fare clic su Crea archivio.
7. Fare clic su OK.

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>Ottenere le configurazioni del modello fattura cliente fornite da Microsoft
1. Fare clic su Mostra filtri.
2. Applicare filtri i seguenti: Immettere un valore di filtro "Risorse operative" nel campo "Nome" utilizzando l'operatore di filtro "inizia con"; Immettere un valore di filtro di "" nel campo "Descrizione" utilizzando l'operatore di filtro "inizia con"
3. Fare clic su Mostra filtri.
4. Fare clic su Apri.
5. Nella struttura selezionare 'Modello fattura cliente'.

    Selezionare la configurazione modello 'Modello fattura cliente' per importarla.  

6. Fare clic su Importa.

    Fare clic su Importa per la versione 1 della configurazione selezionata.  

7. Fare clic su Sì.
8. Chiudere la pagina.
9. Chiudere la pagina.
10. Fare clic su Configurazioni report.
11. Nella struttura selezionare 'Modello fattura cliente'.

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>Creare il modello derivato per supportare l'accesso ai file di gestione documenti.
Si creerà una propria configurazione del modello fattura cliente derivandola dalla configurazione fornita da Microsoft. Si userà questa configurazione per implementare l'accesso ai file di gestione documenti e renderli disponibili per i documenti elettronici che verranno creati in base a tale modello.  
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
2. Nel campo Nuovo, immettere 'Deriva da nome: Modello fattura cliente, Microsoft'.
3. Nel campo Nome digitare 'Modello fattura cliente (personalizzato)'.
4. Fare clic su Crea configurazione.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
