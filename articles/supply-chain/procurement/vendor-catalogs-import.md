---
title: Importa cataloghi fornitore
description: In questo argomento viene descritto il processo di importazione dei dati del catalogo fornitore.
author: RichardLuan
manager: tfehr
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: riluan
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: f752e6c42653d7ac39e011e71d0d31f936996499
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260529"
---
# <a name="import-vendor-catalogs"></a>Importa cataloghi fornitore

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>Importazione cataloghi fornitore

In Dynamics 365 Supply Chain Management, i professionisti degli acquisti possono creare e gestire cataloghi che i dipendenti possono utilizzare quando ordinano articoli e servizi per uso interno. Per creare un catalogo di approvvigionamento, è possibile aggiungere gli articoli e i servizi che si desidera rendere disponibili ai dipendenti, importando i dati del catalogo prodotti oppure aggiungendo manualmente i dati del catalogo prodotti alla rappresentazione generale prodotto. 

È possibile caricare i dati del catalogo inviati da un fornitore dal client di Microsoft Dynamics 365.

I dati dei prodotti che un fornitore invia all'utente sotto forma di un file di richiesta di gestione catalogo devono essere in formato XML. Il file di richiesta di gestione catalogo deve contenere i dettagli dei prodotti che il fornitore fornisce alla società.

## <a name="import-vendor-catalog-data"></a>Importare i dati del catalogo fornitore

Per importare i dati del catalogo fornitore, è necessario completare le attività seguenti:

1. Impostare un progetto nell'area di lavoro Gestione dati in cui sono state definite le regole di mapping dei dati. Selezionare **Gestione dati** e quindi **Imposta ruoli per progetti dati**.

2. Impostare una gerarchia di categorie di approvvigionamento e assegnare i fornitori alle categorie di approvvigionamento. Se si utilizzano codici di voce doganale, aggiungere i codici alle categorie di approvvigionamento. Per informazioni su come impostare una gerarchia di categorie di approvvigionamento, vedere [Impostare una gerarchia di categorie di approvvigionamento](../procurement/tasks/set-up-procurement-category-hierarchy.md).

3. Configurare il fornitore per l'importazione del catalogo. Selezionare un fornitore e quindi **Approvvigionamento** > **Impostazione** > **Configura fornitore per importazione catalogo**.

4. Configurare il flusso di lavoro per l'importazione del catalogo. Creare un modello di file di richiesta di gestione catalogo e condividerlo con il fornitore.

5. Selezionare **Approvvigionamento** \> **Comune** \> **Cataloghi** \> **Cataloghi fornitore** per creare un catalogo fornitore. I file di richiesta di gestione catalogo ricevuti dal fornitore vengono raggruppati in questo catalogo. 

6. Caricare il file di richiesta di gestione catalogo.

7. Verificare, approvare o rifiutare i prodotti del catalogo fornitore. I prodotti vengono mappati automaticamente alle categorie di approvvigionamento. 

I prodotti approvati vengono aggiunti alla rappresentazione generale prodotto e vengono rilasciati alle persone giuridiche selezionate. Solo i prodotti approvati possono essere aggiunti al catalogo di approvvigionamento.

## <a name="generate-a-catalog-import-file-template"></a>Generazione di un modello di file di importazione catalogo

Il modello di file di importazione catalogo è un file XSD utilizzabile per creare un file di richiesta di gestione catalogo per i prodotti di un fornitore. È possibile utilizzare il file di richiesta di gestione catalogo per creare un nuovo catalogo oppure sostituire o modificare un catalogo esistente.

1. Selezionare **Approvvigionamento** \> **Cataloghi** \> **Cataloghi fornitore** e fare doppio clic sul catalogo che si desidera utilizzare.

2. Scaricare un modello di importazione catalogo corrente (file XSD). Nella pagina **Aggiorna catalogo**, nel **Riquadro azioni**, scheda **Cataloghi**, nel gruppo **Informazioni correlate**, fare clic su **Genera modello catalogo** e selezionare **Categoria di approvvigionamento**.

    - Con l'opzione **Categoria di approvvigionamento** è possibile generare un modello di catalogo che include le categorie di approvvigionamento in cui il fornitore è autorizzato a fornire prodotti.

3. Nella finestra di dialogo **Salva con nome** selezionare il percorso in cui si desidera archiviare il modello di file di catalogo e salvare il file.

Per esempi e ulteriori informazioni, vedere questo post di blog: [Cataloghi fornitore in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]