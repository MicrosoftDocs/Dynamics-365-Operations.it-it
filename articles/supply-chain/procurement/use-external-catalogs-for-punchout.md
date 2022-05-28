---
title: Usare cataloghi esterni per PunchOut e-procurement
description: In questo argomento viene descritto come utilizzare i cataloghi esterni per creare e inviare richieste.
author: GalynaFedorova
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17c473a93b7451879f1478a8c0c46fe9d8351fc4
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679277"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a>Usare cataloghi esterni per PunchOut e-procurement

[!include [banner](../includes/banner.md)]

Se si utilizzano i cataloghi esterni per PunchOut eProcurement, non è necessario gestire le informazioni sui prodotti dei fornitori nei propri dati master. Il carrello nel sito Web del fornitore viene invece convertito in righe di richiesta con le informazioni sul prodotto corrette. 

È consigliabile evitare di conservare le descrizioni e i prezzi dei prodotti dei fornitori nei propri dati master. Utilizzare invece i cataloghi esterni per PunchOut e-procurement. Quando i dipendenti creano le richieste, possono accedere al sito esterno del fornitore (in altre parole lasciano il sistema per accedere al sito del fornitore). I prodotti aggiunti al carrello nel sito Web del fornitore possono quindi essere convertiti in righe di richiesta. Si ottengono così le informazioni corrette sul prodotto: ID prodotto, nome, prezzo e così via.

Per utilizzare i cataloghi esterni, un dipendente deve creare una richiesta nella pagina **Richieste di acquisto personali**.

Il dipendente che crea la richiesta è definito il preparatore della richiesta. Un preparatore può completare le attività seguenti.

Utilizzare l'azione di riga **Cataloghi esterni** per aprire una pagina che includa tutti i cataloghi esterni disponibili per il richiedente specificato, la persona giuridica acquirente e l'unità operativa ricevente.

In base alle autorizzazioni, modificare il richiedente, la persona giuridica acquirente e l'unità operativa ricevente. Una modifica a tali valori può modificare l'elenco dei cataloghi esterni disponibili a un richiedente. I cataloghi esterni che sono disponibili variano in base ai criteri di acquisto attivi correnti per la persona giuridica acquirente o l'unità operativa ricevente. Questi criteri possono consentire o impedire l'accesso a categorie di approvvigionamento specifiche. Di conseguenza, l'elenco dei cataloghi esterni che sono mappati a queste categorie di approvvigionamento può rimanerne influenzato.

Per ulteriori informazioni sui criteri, vedere [Panoramica dei criteri di acquisto](../procurement/purchase-policies.md).

- Per individuare cataloghi esterni per categorie di approvvigionamento specifiche, immettere il testo nel campo di ricerca catalogo.
- Per aggiungere i prodotti di un catalogo esterno disponibile nel sito Web del fornitore, fare clic sul catalogo esterno. Aggiungere quindi i prodotti al carrello ed effettuare il check out. Le righe del carrello verranno trasferite in Microsoft Dynamics 365.

Se sono disponibili più opzioni per le categorie di approvvigionamento, selezionare la categoria di approvvigionamento corretta prima di aggiungere le righe alla richiesta.
Dopo che le righe sono state aggiunte a una richiesta, è possibile aggiungere altre righe senza utilizzare i cataloghi esterni. In alternativa, è possibile continuare a utilizzare i cataloghi esterni per aggiungere le righe.

Quando la richiesta è pronta, utilizzare l'azione **Flusso di lavoro** > **Invia** per inoltrare la richiesta per l'approvazione.

### <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare un catalogo esterno per PunchOut e-procurement](set-up-external-catalog-for-punchout.md)
- [Miglioramenti cXML per gli acquisti](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]