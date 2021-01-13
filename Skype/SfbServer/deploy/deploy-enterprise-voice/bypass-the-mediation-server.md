---
title: Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o Servidor de Mediação
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilita o bypass de mídia para sempre ignorar o Servidor de Mediação no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804211"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="d1ff1-103">Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="d1ff1-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="d1ff1-104">Habilita o bypass de mídia para sempre ignorar o Servidor de Mediação no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="d1ff1-105">Se você usar as etapas deste tópico para definir as configurações globais para o bypass de mídia, a suposição é de que você tem uma boa conectividade entre os pontos de extremidade do Skype for Business e qualquer ponto para o qual tenha configurado o bypass de mídia na conexão de tronco.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="d1ff1-106">Se você não tiver uma boa conectividade entre os pontos de extremidade do Skype for Business e todos os pontos do Servidor de Mediação cujas respectivas conexões de tronco foram habilitadas para bypass de mídia, você deve definir configurações globais de bypass de mídia para usar informações de site e região ao empregar bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="d1ff1-107">Isso permite maior controle ao determinar quando a mídia desvia do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="d1ff1-108">Para fazer isso, use as etapas em Configurar definições globais de bypass de mídia no [Skype for Business Server](use-site-and-region-information.md) para usar informações de site e região e associar uma [sub-rede a](deploy-network.md#BKMK_AssociateSubnets) um site de rede.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="d1ff1-109">Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="d1ff1-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="d1ff1-110">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="d1ff1-111">Na barra de navegação da esquerda, clique em **Configuração da Rede**.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="d1ff1-112">Clique duas vezes na configuração **Global** na lista.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="d1ff1-113">Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="d1ff1-114">Clique em **Sempre desviar**.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="d1ff1-115">Clique em **Comprometer**.</span><span class="sxs-lookup"><span data-stu-id="d1ff1-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d1ff1-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="d1ff1-116">See also</span></span>

[<span data-ttu-id="d1ff1-117">Planejar bypass de mídia no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1ff1-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="d1ff1-118">Implantar bypass de mídia no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d1ff1-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

