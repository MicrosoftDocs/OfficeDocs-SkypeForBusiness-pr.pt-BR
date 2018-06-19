---
title: Configurar o bypass de mídia no Skype para negócios 2015 de servidor para sempre ignorar o servidor de mediação
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilite bypass de mídia para sempre ignorar o servidor de mediação no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 9e28af8bd794c3c0924e9a6688eeca159c435d28
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500431"
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a><span data-ttu-id="53725-103">Configurar o bypass de mídia no Skype para negócios 2015 de servidor para sempre ignorar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="53725-103">Configure media bypass in Skype for Business Server 2015 to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="53725-104">Habilite bypass de mídia para sempre ignorar o servidor de mediação no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="53725-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="53725-105">Se você usar as etapas deste tópico para definir as configurações globais para o media bypass, pressupõe-se que você tem boa conectividade entre Skype para pontos de extremidade de negócios e qualquer ponto para o qual você configurou o desvio de mídia na conexão do tronco.</span><span class="sxs-lookup"><span data-stu-id="53725-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="53725-106">Se você não tem boa conectividade entre Skype para pontos de extremidade de negócios e todos os pares para o servidor de mediação cujas conexões de tronco respectivos tiverem sido habilitados para bypass de mídia, você deve configurar as definições de desvio de mídia global para usar as informações do site e da região Quando desvio de mídia empregando.</span><span class="sxs-lookup"><span data-stu-id="53725-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="53725-107">Isso permite que mais controle na determinação quando a mídia ignora o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="53725-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="53725-108">Para fazer isso, use as etapas em [configurações globais no Skype para o servidor de negócios 2015 usem informações de site e a região de bypass de mídia de configurar](use-site-and-region-information.md) e [associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="53725-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server 2015 to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="53725-109">Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="53725-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="53725-110">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="53725-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="53725-111">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="53725-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="53725-112">Clique duas vezes na configuração **Global** na lista.</span><span class="sxs-lookup"><span data-stu-id="53725-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="53725-113">Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="53725-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="53725-114">Clique em **Sempre desviar**.</span><span class="sxs-lookup"><span data-stu-id="53725-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="53725-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="53725-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="53725-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53725-116">See also</span></span>

[<span data-ttu-id="53725-117">Planejar o bypass de mídia no Skype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="53725-117">Plan for media bypass in Skype for Business 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="53725-118">Implantar o bypass de mídia no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="53725-118">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)