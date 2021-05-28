---
title: Risoluzione dei problemi relativi al Connettore pagamenti di Dynamics 365 per Adyen
description: Questo argomento fornisce informazioni per ottenere assistenza in caso di problemi con il Connettore pagamenti di Microsoft Dynamics 365 per Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 707efeba9553b996e4e33a4754e42a9d22643e33
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019591"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a><span data-ttu-id="058f5-103">Risoluzione dei problemi relativi al Connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="058f5-103">Troubleshoot Dynamics 365 Payment Connector for Adyen issues</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="058f5-104">Questo argomento fornisce informazioni per ottenere assistenza in caso di problemi con il Connettore pagamenti di Microsoft Dynamics 365 per Adyen.</span><span class="sxs-lookup"><span data-stu-id="058f5-104">This topic provides troubleshooting guidance that can help you get support when you have issues with the Microsoft Dynamics 365 Payment Connector for Adyen.</span></span>

## <a name="description"></a><span data-ttu-id="058f5-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="058f5-105">Description</span></span>

<span data-ttu-id="058f5-106">Hai problemi con il Connettore di pagamento Dynamics 365 per Adyen nelle seguenti aree e necessiti assistenza da parte del team di Adyen:</span><span class="sxs-lookup"><span data-stu-id="058f5-106">You have issues with the Dynamics 365 Payment Connector for Adyen in the following areas, and you require support from the Adyen team:</span></span>

- <span data-ttu-id="058f5-107">Configurazione di POS, Modern POS (MPOS), servizio clienti o Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="058f5-107">Configuration of Point of sale (POS), Modern point of sale (MPOS), call center, or Dynamics 365 Commerce</span></span>
- <span data-ttu-id="058f5-108">Il numero di riferimento del provider di servizi di pagamento Adyen (PSP) (ad esempio, se si hanno domande su rifiuti, inclusi i rifiuti \[MKE\] di immissione manuale con tasti)</span><span class="sxs-lookup"><span data-stu-id="058f5-108">The Adyen payment service provider (PSP) reference number (for example, if you have questions about refusals, including manual key entry \[MKE\] refusals)</span></span>
- <span data-ttu-id="058f5-109">Tutto ciò che non funziona in ambienti di prova o di commercio live</span><span class="sxs-lookup"><span data-stu-id="058f5-109">Anything that isn't working in test or live merchant environments</span></span>

## <a name="resolution"></a><span data-ttu-id="058f5-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="058f5-110">Resolution</span></span>

<span data-ttu-id="058f5-111">Utilizzare il seguente modello di messaggio di posta elettronica per avviare il processo di supporto con il team di Adyen.</span><span class="sxs-lookup"><span data-stu-id="058f5-111">Use the following email template to start the support process with the Adyen team.</span></span> <span data-ttu-id="058f5-112">Per velocizzare la risoluzione dei problemi, assicurarsi che il messaggio di posta elettronica contenga tutti i dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="058f5-112">To expedite troubleshooting, make sure that the email contains all the required details.</span></span>

| <span data-ttu-id="058f5-113">Campo</span><span class="sxs-lookup"><span data-stu-id="058f5-113">Field</span></span>        | <span data-ttu-id="058f5-114">Valore</span><span class="sxs-lookup"><span data-stu-id="058f5-114">Value</span></span> |
|--------------|-------|
| <span data-ttu-id="058f5-115">Ora di fine</span><span class="sxs-lookup"><span data-stu-id="058f5-115">To</span></span>           | `support@adyen.com` |
| <span data-ttu-id="058f5-116">Cc</span><span class="sxs-lookup"><span data-stu-id="058f5-116">Cc</span></span>           | |
| <span data-ttu-id="058f5-117">Riga oggetto</span><span class="sxs-lookup"><span data-stu-id="058f5-117">Subject line</span></span> | <span data-ttu-id="058f5-118">Richiesta di supporto di Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="058f5-118">Microsoft Dynamics Support Request</span></span> |
| <span data-ttu-id="058f5-119">Corpo</span><span class="sxs-lookup"><span data-stu-id="058f5-119">Body</span></span>         | <p><span data-ttu-id="058f5-120">Buongiorno</span><span class="sxs-lookup"><span data-stu-id="058f5-120">Hi Support,</span></span></p><p><span data-ttu-id="058f5-121">Vorrei ricevere supporto per il seguente problema:</span><span class="sxs-lookup"><span data-stu-id="058f5-121">Please provide support for the following issue:</span></span></p><ul><li><span data-ttu-id="058f5-122">Conto esercente</span><span class="sxs-lookup"><span data-stu-id="058f5-122">Merchant account</span></span></li><li><span data-ttu-id="058f5-123">Ambiente (test/produzione)</span><span class="sxs-lookup"><span data-stu-id="058f5-123">Environment (Test/Prod)</span></span></li><li><span data-ttu-id="058f5-124">Canale (POS/servizio clienti/e-commerce Commerce)</span><span class="sxs-lookup"><span data-stu-id="058f5-124">Channel (POS/call center/Commerce e-commerce)</span></span></li><li><span data-ttu-id="058f5-125">Numero di riferimento PSP, se il problema riguardava una transazione specifica (puoi trovare il numero di riferimento PSP sullo scontrino, nell'Area clienti Adyen o nel menu delle transazioni sul terminale POS).</span><span class="sxs-lookup"><span data-stu-id="058f5-125">PSP reference number, if the issue involved a specific transaction (You can find the PSP reference number on the receipt, in the Adyen Customer Area, or on the transactions menu on the POS terminal.)</span></span></li><li><span data-ttu-id="058f5-126">Screenshot o foto del messaggio di errore, se applicabile</span><span class="sxs-lookup"><span data-stu-id="058f5-126">Screenshot or photo of the error message, if applicable</span></span></li><li><span data-ttu-id="058f5-127">Registri del visualizzatore eventi (in formato .txt)</span><span class="sxs-lookup"><span data-stu-id="058f5-127">Event Viewer logs (in .txt format)</span></span></li><li><span data-ttu-id="058f5-128">Descrizione del problema e operazioni per la risoluzione del problema effettuate</span><span class="sxs-lookup"><span data-stu-id="058f5-128">Description of the issue and troubleshooting steps that you've tried</span></span></li></ul> |

## <a name="additional-resources"></a><span data-ttu-id="058f5-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="058f5-129">Additional resources</span></span>

[<span data-ttu-id="058f5-130">Accettare pagamenti con il connettore Adyen per Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="058f5-130">Accept payments with the Adyen connector for Dynamics 365 Commerce</span></span>](https://www.adyen.com/partners/dynamics-365-commerce)

[<span data-ttu-id="058f5-131">Connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="058f5-131">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="058f5-132">Impostare il connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="058f5-132">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
