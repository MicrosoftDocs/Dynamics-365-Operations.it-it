---
title: Metodologia della convenzione di ammortamento semestrale
description: In questo argomento viene descritto il metodo utilizzato dai cespiti per calcolare l'ammortamento utilizzando la convenzione semestrale, che calcola sei mesi di ammortamento durante il primo e l'ultimo anno di utilizzo di un cespite.
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 5e71beb316494d05a3d8ce6066f2a4c72e32a2ad3d75a4ba3560cb0aebfe4cc8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746442"
---
# <a name="half-year-depreciation-convention-methodology"></a>Metodologia della convenzione di ammortamento semestrale

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene descritto il metodo utilizzato nei cespiti per calcolare l'ammortamento utilizzando la convenzione semestrale. La convenzione semestrale calcola sei mesi di ammortamento durante il primo e l'ultimo anno di utilizzo di un cespite. Per ulteriori informazioni sulle convenzioni di ammortamento, vedere [Metodi e convenzioni di ammortamento](Fixed-asset-depreciation-conventions.md). 

Quando si utilizza la convenzione di ammortamento semestrale, il sistema utilizza l'anno di acquisizione o l'anno in cui il cespite è stato messo in uso, quindi calcola cinque anni di ammortamento da quell'anno e aggiunge sei mesi. Per illustrare questo processo, si consideri un cespite che è stato acquistato al prezzo di 50.000 e messo in uso nell'aprile 2020. Si supponga inoltre che il cespite abbia una durata di utilizzo di cinque anni.

Il primo anno di utilizzo si concluderà a dicembre 2020, il che significa che la fine della vita utile di cinque anni del cespite sarà dicembre 2024. La convenzione sull'ammortamento semestrale aggiungerà sei mesi alla vita del cespite, il che significa che la sua vita utile terminerà nel giugno 2025. 

> Ammortamento annuale 50.000/5 = 10.000 ammortamento mensile 10.000/12 = 833,33 <br>
> Ammortamento primo anno 10.000/2 = 5.000 e successivo ammortamento mensile 5.000/9 = 555,56

   [![Piano di ammortamento per convenzione di ammortamento semestrale.](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

I periodi di ammortamento estesi aggiunti dalla convenzione semestrale forniscono un'allocazione più accurata dell'ammortamento. La convenzione semestrale rappresenta le spese di ammortamento in modo più equo, utile per la rendicontazione del conto economico.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]