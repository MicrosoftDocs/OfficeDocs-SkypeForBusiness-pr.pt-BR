---
title: Expansor de configurações SBA do Registrador Avançado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Edite as configurações para resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: b5c5982dc0a49d1d2002465f4f7a2c6381dd5370
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819343"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="0ea04-103">Expansor de configurações SBA do Registrador Avançado</span><span class="sxs-lookup"><span data-stu-id="0ea04-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="0ea04-104">Edite as configurações para **resiliência** e configure as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0ea04-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="0ea04-105">Selecione o **serviço de usuário associado e o pool de registradores de backup** na lista.</span><span class="sxs-lookup"><span data-stu-id="0ea04-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="0ea04-106">Opcionalmente, marque a caixa de seleção **failover automático e failback para voz** .</span><span class="sxs-lookup"><span data-stu-id="0ea04-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="0ea04-107">Configurar o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**.</span><span class="sxs-lookup"><span data-stu-id="0ea04-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="0ea04-108">Por padrão, os intervalos são de 120 segundos para a detecção de falha de voz e 240 segundos para failback de voz.</span><span class="sxs-lookup"><span data-stu-id="0ea04-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="0ea04-109">O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="0ea04-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="0ea04-110">Definir o intervalo como baixo (ou seja, menos de 120 segundos) ou o failover e o failback definidos com mais detalhes podem resultar no failover real e o failback não funcionando como esperado.</span><span class="sxs-lookup"><span data-stu-id="0ea04-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="0ea04-111">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0ea04-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="0ea04-112">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0ea04-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="0ea04-113">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="0ea04-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ea04-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ea04-114">See also</span></span>

[<span data-ttu-id="0ea04-115">Planejando a resiliência do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="0ea04-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
