---
title: Configurare i parametri di gestione dei benefit per azienda
description: Configurare i parametri di gestione dei benefit per azienda in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2943d0095e4c9421725b90e579b7cbb841038ab7
ms.sourcegitcommit: fd097f6f76f0d8428038fa3655b3188bf093b517
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692747"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Configurare i parametri di gestione dei benefit per azienda

Per ogni organizzazione che offre benefit, è necessario configurare le impostazioni per i messaggi di posta elettronica di conferma dei benefit.

## <a name="configure-confirmation-email-settings"></a>Configurare impostazioni di posta elettronica per la conferma

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri Risorse umane**.

2. Nella scheda **Gestione benefit** specificare i valori per i seguenti campi: 

   | Campo | descrizione |
   | --- | --- |
   | **Invia messaggio di posta elettronica di conferma** | Quando questa funzione è attiva, verrà inviata un messaggio di posta elettronica di conferma ai dipendenti quando effettuano il check-out dall'esperienza di registrazione dei vantaggi in self-service dei dipendenti. |
   | **Modello di messaggio di posta elettronica di conferma** | Selezionare il modello di posta elettronica dell'organizzazione da utilizzare quando si invia la conferma di registrazione. Se non si seleziona un modello, verrà inviata il seguente messaggio di posta elettronica generico:<br><br>%EmployeeFirstName%,<br><br>Congratulazioni. L'iscrizione ai benefit è stata completata.<br><br>Grazie,<br>Benefit di <Nome azienda/Organizzazione>. |
   | **Indirizzo mittente di posta elettronica predefinito** | L'indirizzo di posta elettronica da utilizzare quando si invia il messaggio di posta elettronica di conferma. |

3. Selezionare **Salva**.