---
title: Estendere Talent con Power Apps e Power Automate
description: In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Talent - Attract che utilizzano Microsoft Power Apps e Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529636"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Estendere Talent con Power Apps e Power Automate

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Talent: Attract che utilizzano Microsoft Power Apps e Microsoft Power Automate. È possibile importare il pacchetto di soluzioni associato a ogni esempio nell'ambiente di Power Apps. È quindi possibile utilizzare i pacchetti come riferimento o punto di partenza per implementare scenari applicabili all'organizzazione.

> [!IMPORTANT]
> Se si desidera utilizzare i modelli e l'app descritti in questo articolo "così come sono", testarli per assicurarsi che coprano tutti gli scenari specifici dell'implementazione.


## <a name="prerequisites"></a>Prerequisiti

- Per importare pacchetti, gli utenti devono disporre dell'autorizzazione **Creazione ambiente**.
- Per esportare o importare app, gli utenti devono disporre di una licenza di Power Apps Piano 2 o una licenza di valutazione di Power Apps Piano 2.

## <a name="power-automate--form-connect"></a>Power Automate – Connessione a modulo

Il modello **Power Automate – Connessione a modulo** può essere utilizzato per leggere i dati in Microsoft Forms e archiviarli in un'entità Common Data Service.

Questo modello può essere esteso in modo da poterlo utilizzare per altri scenari. Di seguito sono riportati alcuni esempi.

- Acquisire valutazioni di candidati.
- Acquisire risultati da questionari di corsi.
- Compilare una libreria di domande di colloqui per gli amministratori delle Risorse umane.
- Acquisire la valutazione del colloquio di un candidato

In Microsoft Dynamics 365: Attract, è possibile utilizzare moduli nel portale del candidato, ovvero dove i candidati immettono i dettagli. È anche possibile incorporare moduli come attività in un modello posizioni lavorative.

Quando un candidato invia un modulo, Microsoft Power Automate lo acquisisce, legge i dati e li archivia nell'entità Common Data Service.

Per scaricare il modello **Power Automate – Connessione a modulo** e Custom Entity Structure, andare a [Power Automate – Connessione a modulo](https://go.microsoft.com/fwlink/?linkid=2081988) nell'Area download Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Power Automate – Integrazione di SharePoint

Il modello **Power Automate – Integrazione di SharePoint** può essere utilizzato per leggere dati in un elenco di Microsoft SharePoint, confrontare l'elenco con valori di campi per qualsiasi entità Common Data Service e inviare i risultati del confronto in forma di messaggio di posta elettronica di notifica. 

Un'organizzazione potrebbe avere un insieme di competenze che richiede urgentemente. Queste competenze possono essere archiviate in SharePoint come elenco di SharePoint. Quando un candidato si candida a una mansione per la quale è elencato un insieme di competenze, se è presente una corrispondenza significativa tra le competenze del candidato e quelle archiviate in SharePoint, viene inviato un messaggio di posta elettronica di notifica. In questo modo, le posizioni urgenti vengono coperte più rapidamente in quanto le notifiche consentono ai selezionatori di assumere i candidati nell'intera organizzazione.

Questo modello può essere esteso di modo che sia possibile utilizzarlo per qualsiasi scenario che comporta l'integrazione di SharePoint.

Per scaricare il modello **Power Automate – Integrazione di SharePoint**, andare a [Power Automate – Integrazione di SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) nell'Area download Microsoft.

## <a name="referral-app"></a>Referral App

È possibile utilizzare Referral App per aggiungere candidati a un pool di talenti condiviso. Il referente può immettere **Nome**, **Cognome**, **E-mail** e **URL LinkedIn** quando invia un candidato. I metadati di origine del candidato vengono quindi completati con le informazioni del referente.

È possibile incorporare questa app in Dipendente self-service per inviare referenze oppure è possibile utilizzarla come collegamento ipertestuale nel portale aziendale ed eseguirla come applicazione autonoma.

Per scaricare **Referral App**, accedere a [Soluzione di estensibilità Dynamics 365 Talent: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) nell'Area download Microsoft. È possibile importare questa app e personalizzarla per aggiungere altre funzionalità.

## <a name="additional-resources"></a>Risorse aggiuntive

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migrare app tra tenant e ambienti](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)


[!INCLUDE[footer-include](../includes/footer-banner.md)]