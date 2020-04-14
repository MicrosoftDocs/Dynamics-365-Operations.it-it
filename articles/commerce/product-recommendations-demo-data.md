---
title: Crea suggerimenti con dati dimostrativi
description: Questo documento fornisce una guida su come sfruttare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.
author: bebeale
manager: AnnBe
ms.date: 03/19/20
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 59cb5e5c9b59ff2127149e3e47b6c30c9c938a27
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154251"
---
# <a name="create-recommendations-with-demo-data"></a>Crea suggerimenti con dati dimostrativi

[!include [banner](includes/banner.md)]

Questo documento fornisce una guida su come sfruttare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.

I suggerimenti sul prodotto omnicanale forniscono un set di elenchi di prodotti curati in modo editoriale o generati a livello di programmazione. Gli elenchi possono essere utilizzati in vari scenari, in base alle esigenze aziendali. Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).

Per gli ambienti Dynamics 365 di livello 2 e superiore, i suggerimenti sui prodotti vengono calcolati automaticamente in base ai dati dei clienti. L'uso dei dati dimostrativi dei suggerimenti sui prodotti non disabilita alcuna soluzione di suggerimenti sui prodotti già predisposta nell'ambiente e i costi associati al suo utilizzo.

Per gli ambienti di livello 1, i suggerimenti sui prodotti si basano solo sui dati dimostrativi statici memorizzati in un file CSV.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Abilitazione dei dati dimostrativi dei suggerimenti sui prodotti in un ambiente
Per abilitare i dati dimostrativi dei suggerimenti sui prodotti, è necessario distribuire l'Estensione dimostrativa dell'anteprima di Dynamics 365 Commerce al rispettivo ambiente. In questo modo, si abilitano i dati dimostrativi dei suggerimenti sui prodotti.

## <a name="default-demo-data"></a>Dati dimostrativi predefiniti
Ogni ambiente di tipo Onebox viene fornito con un set precaricato di dati dimostrativi di suggerimenti sui prodotti memorizzati nel file "reco_demo_data.csv", situato in Commerce Scale Unit.

I dati sono strutturati nelle seguenti colonne.

| Nome colonna         | Obbligatorio          | Descrizione                                                                                                                                 | Valori possibili                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | Il tipo di elenco di suggerimenti sul prodotto specifico che deve essere generato dal punto dei dati dimostrativi.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Il numero specifico dell'unità operativa in cui sono previsti i suggerimenti sui prodotti.                                        |                                                                              |
| Categoria            |                    |    La categoria per cui deve essere restituito l'elenco specifico. Se non viene specificata alcuna categoria, l'elenco è solo per la parte superiore della gerarchia di navigazione.    |                                                                              |
| SeedItemId          |                    |    Per gli elenchi che richiedono seed (RecoPeopleAlsoBuy e RecoCart) il prodotto per cui tali elenchi devono mostrare prodotti aggiuntivi.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Uno o più prodotti da restituire come risultato, separati da ";".                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Personalizzare i dati dimostrativi
Puoi modificare i dati dimostrativi predefiniti con qualsiasi informazione su prodotto e categoria configurata nella sede centrale. Una volta aggiornato il file CSV, i suggerimenti sul prodotto restituiti ai clienti rifletteranno immediatamente le modifiche.

L'estensione contiene un file di dati chiamato RecoMockDataset.csv che consente di controllare il set di dati utilizzato per potenziare i risultati dei suggerimenti simulati. Il nome del file può essere controllato tramite la configurazione dell'estensione usando l'impostazione **ext.Recommendations.DemoFilePath**. In tal modo è possibile disporre di più set di dati che possono essere commutati facilmente attraverso la configurazione.


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare ADLS in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Aggiungere suggerimenti sul prodotto su POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)
