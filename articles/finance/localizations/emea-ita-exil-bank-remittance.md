---
title: Profili registrazione configurabili per banche e tipi di rimessa
description: Questo argomento fornisce informazioni su come configurare i profili di registrazione per banche e tipi di rimesse.
author: ilkond
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: a57870201fd36369eac4276af05c4be697ac4dbe
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408112"
---
# <a name="configurable-posting-profiles-for-banks-and-remittance-types"></a>Profili registrazione configurabili per banche e tipi di rimessa

[!include [banner](../includes/banner.md)]

Oltre a definire le impostazioni di funzionalità generali, è possibile impostare diversi profili di registrazione per la rimessa di un effetto attivo (rimessa per incasso e rimessa per sconto) e la rimessa di un effetto passivo nei conti bancari dell'azienda. Per ulteriori informazioni, vedere [Impostare gli effetti attivi](../accounts-receivable/set-up-bills-exchange.md).

## <a name="prerequisites"></a>Prerequisiti

Prima di poter utilizzare diversi profili di registrazione per la rimessa di un effetto attivo e la rimessa di un effetto passivo nei conti bancari della società, devono essere soddisfatti i seguenti requisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzionalità **Profili di registrazione configurabili per banche e tipi di rimesse** deve essere attivata nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-a-posting-profile-for-a-remittance-journal-line-offset-account"></a>Impostare un profilo di registrazione per un conto di contropartita della riga del giornale di registrazione rimesse

Per impostare i profili di registrazione, è necessario aprire un conto bancario aziendale. Quando il sistema registra un effetto attivo o un effetto passivo nel giornale di registrazione rimesse, utilizza i profili di registrazione nelle righe giornale di registrazione rimesse per un conto di contropartita.

1. Per impostare il profilo di pubblicazione, andare a **Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari**.
2. Nella scheda dettaglio **Generale**, nella sezione **Profili di registrazione**, nei campi **Rimessa per incasso**, **Rimessa per sconto** e **Rimessa effetto passivo**, selezionare un profilo di registrazione, come richiesto.

![Impostazione del conto bancario](media/emea-ita-exil-different-accounts-per-company-bank.png)

## <a name="use-posting-profiles-in-remittance-journal-posting"></a>Utilizzare i profili di registrazione nella registrazione del giornale di registrazione rimesse

Se i profili di registrazione sono stati impostati nel conto bancario, il sistema li utilizzerà per specificare il conto di contropartita quando viene registrato un giornale di registrazione rimesse. Se i profili di registrazione non sono stati impostati, il sistema seleziona il profilo di registrazione nella scheda **Contabilità generale e IVA** delle pagine **Parametri contabilità clienti** e **Parametri contabilità fornitori**.
