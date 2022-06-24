---
title: Gestione dei clienti nei punti vendita
description: In questo articolo viene descritto come i rivenditori possono abilitare le funzionalità di gestione dei clienti presso il POS in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 805d0b5894b18e2fc34f481bdc32ada7a4b1aee0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863489"
---
# <a name="customer-management-in-stores"></a>Gestione dei clienti nei punti vendita

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come i rivenditori possono abilitare le funzionalità di gestione dei clienti presso il POS in Microsoft Dynamics 365 Commerce.

È importante che i dipendenti del punto vendita possano creare e modificare i record cliente nel POS. In tal modo, possono acquisire eventuali aggiornamenti delle informazioni sui clienti come indirizzo e-mail, numero di telefono e indirizzo. Queste informazioni sono utili nei sistemi a valle come il marketing, perché l'efficacia di tali sistemi dipende dall'accuratezza dei dati dei loro clienti.

Gli addetti alle vendite possono attivare il flusso di lavoro di creazione di clienti da due punti di ingresso POS. Possono selezionare un pulsante che è mappato all'operazione **Aggiunta cliente**, oppure possono selezionare **Crea cliente** nella barra dell'applicazione nella pagina dei risultati di ricerca. In entrambi i casi, viene visualizzata la finestra di dialogo **Nuovo cliente** in cui gli addetti alle vendite possono inserire i dettagli del cliente richiesti, come il nome, l'indirizzo e-mail, il numero di telefono, l'indirizzo e qualsiasi altra informazione rilevante per l'attività. Tali informazioni aggiuntive possono essere acquisite utilizzando gli attributi associati al cliente. Per ulteriori informazioni sugli attributi del cliente, vedere [Attributi cliente](dev-itpro/customer-attributes.md).

Gli addetti alle vendite possono anche acquisire indirizzi e-mail e numeri di telefono secondari. Inoltre, possono acquisire la preferenza del cliente sulla ricezione di informazioni di marketing tramite uno qualsiasi di questi indirizzi e-mail o numeri di telefono secondari. Per abilitare questa funzionalità, i rivenditori devono attivare la funzionalità **Acquisisci più e-mail e numeri di telefono e acconsenti attività di marketing per questi contatti** nell'area di lavoro **Gestione funzionalità** in Commerce Headquarters (**Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**).

## <a name="default-customer-properties"></a>Proprietà cliente predefinite

I rivenditori possono utilizzare la pagina **Tutti i punti vendita** in Commerce Headquarters (**Retail e Commerce \> Canali \> Punti vendita**) per associare un cliente predefinito a ogni punto vendita. Commerce copia quindi le proprietà definite per il cliente predefinito in tutti i nuovi record cliente creati. Ad esempio, la finestra di dialogo **Crea cliente** mostra le proprietà ereditate dal cliente predefinito associato al punto vendita. Tali proprietà includono il **tipo di cliente**, il **gruppo di clienti**, l'**opzione di ricevuta**, la **posta elettronica ricevuta**, la **valuta** e la **lingua**. Anche eventuali **affiliazioni** (raggruppamenti di clienti) vengono ereditate dal cliente predefinito. Tuttavia, le **dimensioni finanziarie** vengono ereditate dal gruppo di clienti associato al cliente predefinito, non dal cliente predefinito stesso.

> [!NOTE]
> Il valore **posta elettronica ricevuta** viene copiato dal cliente predefinito solo se l'ID e-mail di ricevuta non viene fornito per i clienti appena creati. Ciò significa che se l'ID di posta elettronica ricevuta è presente sul cliente predefinito, tutti i clienti creati dal sito di e-commerce riceveranno lo stesso ID e-mail di ricevuta poiché non esiste un'interfaccia utente per acquisire l'ID e-mail di ricevuta dal cliente. È consigliabile mantenere il campo **posta elettronica di ricevuta** vuoto per il cliente predefinito del punto vendita e di utilizzarlo solo se si dispone di un processo aziendale che dipende dalla presenza di un indirizzo email di ricevuta. 

Gli addetti alle vendite possono acquisire più indirizzi per un cliente. Il nome e il numero di telefono del cliente vengono ereditati dalle informazioni di contatto associate a ciascun indirizzo. La Scheda dettaglio **Indirizzi** di un record cliente include un campo **Scopo** che gli addetti alle vendite possono modificare. Se il tipo di cliente è **Persona**, il valore predefinito è **Domicilio**. Se il tipo di cliente è **Organizzazione**, il valore predefinito è **Azienda**. Altri valori supportati da questo campo includono **Domicilio**, **Ufficio** e **Casella postale**. Il valore del campo **Paese** per un indirizzo viene ereditato dall'indirizzo principale specificato nella pagina **Unità operativa** di Commerce headquarters in **Amministrazione organizzazione \> Organizzazioni \> Unità operative**.



## <a name="additional-resources"></a>Risorse aggiuntive

[Modalità di creazione clienti asicroni](async-customer-mode.md)

[Convertire i clienti asincroni in clienti sincroni](convert-async-to-sync.md)

[Attributi cliente](dev-itpro/customer-attributes.md)

[Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
