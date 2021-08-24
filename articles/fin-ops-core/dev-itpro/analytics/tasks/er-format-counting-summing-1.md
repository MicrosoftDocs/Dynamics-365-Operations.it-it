---
title: 'ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 1: creare il formato)'
description: Questo argomento descrive come configurare un formato di report elettronico per eseguire il conteggio e la somma in base ai dati dell'output di testo già generato. (Parte 1)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d1a90c0949e98b4c1e9ccb356d39de9c23b670c518ad14a99974ae2aed7301
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728191"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 1: creare il formato)

[!include [banner](../../includes/banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato. Questi passaggi possono essere eseguiti in qualsiasi società.

Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Ottenere l'accesso all'elenco delle configurazioni fornite da Microsoft
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Assicurarsi che il provider "Litware, Inc." sia disponibile e contrassegnato come attivo.  
2. Selezionare il provider "Litware, Inc." .
3. Fare clic su Archivi.
    * Se un archivio di tipo 'Risorse operative' esiste già, ignorare i passaggi restanti della sottoattività corrente.  
4. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
5. Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.
6. Fare clic su Crea archivio.
7. Fare clic su OK.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Ottenere le configurazioni Intrastat fornite da Microsoft
1. Fare clic su Apri.
2. Nella struttura, selezionare 'Modello Intrastat\Intrastat (DE)'.
3. Fare clic su Importa.
    * Fare clic su Importa per la versione 1.1 della configurazione selezionata.  
4. Fare clic su Sì.
5. Chiudere la pagina.
6. Chiudere la pagina.
7. Fare clic su Configurazioni report.
8. Nella struttura espandere 'Modello Intrastat'.
9. Nella struttura, selezionare 'Modello Intrastat\Intrastat (DE)'.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]