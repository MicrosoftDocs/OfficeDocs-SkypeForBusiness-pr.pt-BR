---
title: Expansor de configurações SBA do registrador
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Você pode edita as configurações de resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: f4237972f271ed65e323d67637d9428631c9a899
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375875"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="9cd44-103">Expansor de configurações SBA do registrador</span><span class="sxs-lookup"><span data-stu-id="9cd44-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="9cd44-104">Você pode edita as configurações de **resiliência** e configure as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="9cd44-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="9cd44-105">Selecione o **serviço de usuário associados e o pool de registradores de backup** na lista.</span><span class="sxs-lookup"><span data-stu-id="9cd44-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="9cd44-106">Como opção, marque a caixa de seleção **failover automático e failback para voz** .</span><span class="sxs-lookup"><span data-stu-id="9cd44-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="9cd44-107">Configure o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**.</span><span class="sxs-lookup"><span data-stu-id="9cd44-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="9cd44-108">Por padrão, os intervalos são 120 para detecção de falha de voz e 240 segundos para failback de voz.</span><span class="sxs-lookup"><span data-stu-id="9cd44-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="9cd44-109">O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="9cd44-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="9cd44-110">Definir o intervalo para baixo (ou seja, menos de 120 segundos) ou o failover e failback definir muito parecido podem resultar na real failover e failback não funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="9cd44-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="9cd44-111">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9cd44-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="9cd44-112">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9cd44-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="9cd44-113">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="9cd44-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cd44-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9cd44-114">See also</span></span>

[<span data-ttu-id="9cd44-115">Planejamento para o Enterprise Voice Resiliency</span><span class="sxs-lookup"><span data-stu-id="9cd44-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)