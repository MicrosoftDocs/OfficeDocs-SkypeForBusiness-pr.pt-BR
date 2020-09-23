---
title: Expansor de Configurações SBA do Registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Edite as configurações para Resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: 6424b43ea7c56760bb8d58ee35d9804c49c435dd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217212"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="d916a-103">Expansor de Configurações SBA do Registrador</span><span class="sxs-lookup"><span data-stu-id="d916a-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="d916a-104">Edite as configurações para **Resiliência** e configure as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="d916a-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="d916a-105">Selecione **Pool associado de Serviço de usuário Registradores de backup** na lista.</span><span class="sxs-lookup"><span data-stu-id="d916a-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="d916a-106">Como opção, marque a caixa de seleção **Failover e failback automático para Voice**.</span><span class="sxs-lookup"><span data-stu-id="d916a-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="d916a-p101">Configure o **Intervalo de detecção de falha do Voice (seg.)** e o **Intervalo de failback do Voice (seg.)**. Por padrão, os intervalos são de 120 segundos para detecção de falha do Voice e 240 segundos para failback do Voice.</span><span class="sxs-lookup"><span data-stu-id="d916a-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="d916a-p102">O número de segundos definido para os intervalos de failover e failback deve ser testado com cuidado a fim de assegurar que a resiliência funcione conforme o esperado. Configurar o intervalo de forma muito baixa (ou seja, menos de 120 segundos) ou o failover e failback definidos de forma muito próxima pode resultar no não funcionamento real e conforme o esperado do failover e do failback.</span><span class="sxs-lookup"><span data-stu-id="d916a-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="d916a-111">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d916a-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="d916a-112">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d916a-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="d916a-113">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="d916a-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="d916a-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="d916a-114">See also</span></span>

[<span data-ttu-id="d916a-115">Planejamento da resiliência do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="d916a-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
