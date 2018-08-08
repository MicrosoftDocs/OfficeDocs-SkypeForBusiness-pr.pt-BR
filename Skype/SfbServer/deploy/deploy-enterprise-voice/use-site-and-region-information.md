---
title: Configurar as configurações globais de desvio de mídia no Skype para Business Server usem informações de site e da região
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configure o bypass de mídia a ser usado para apenas alguns sites e regiões Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 081be80d969c2503abc7e2de4e9865b6057a363b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995976"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="6e8fc-103">Configurar as configurações globais de desvio de mídia no Skype para Business Server usem informações de site e da região</span><span class="sxs-lookup"><span data-stu-id="6e8fc-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="6e8fc-104">Configure o bypass de mídia a ser usado para apenas alguns sites e regiões Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="6e8fc-105">Se você usar as etapas deste tópico para definir as configurações globais para o media bypass, pressupõe-se que você não tem boa conectividade entre todos os Skype para pontos de extremidade de negócios e qualquer ponto para o qual você configurou o desvio de mídia na conexão do tronco.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e8fc-p101">As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o bypass de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do bypass de chamada.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="6e8fc-109">Bypass de mídia para funcionar corretamente deve haver consistência entre um site conforme definido no construtor de topologia e como ele é definido quando você configura regiões de rede e locais de rede.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="6e8fc-110">Por exemplo, se você tiver um site de filial que você definiu no construtor de topologias como tendo apenas um gateway PSTN implantado e esse site de filial deve ser configurado com uma política do Enterprise Voice que permite aos usuários do site de filial ter suas chamadas PSTN roteadas pela PSTN gateway no site da filial.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="6e8fc-111">Para configurar informações de site e de região para bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="6e8fc-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="6e8fc-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="6e8fc-113">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6e8fc-114">Dê dois cliques na configuração **Global** na tabela.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="6e8fc-115">Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar bypass de mídia**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="6e8fc-116">Clique em **Usar as configurações de sites e região**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="6e8fc-117">Se necessário, marque a caixa de seleção **Habilitar bypass de mídia para sites não mapeados**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e8fc-p103">Marque essa caixa de seleção somente se você tiver um ou mais sites grandes associados na mesma região e que não possuem restrições de largura de banda (por exemplo, um grande site central), mas também tem sites de filial associados à mesma região e que possuem restrições de largura de banda. Ao habilitar o bypass para sites não mapeados, a configuração é simplificada de forma que você especifica apenas as sub-redes associadas com os sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque essa caixa de seleção se o controle de admissão de chamadas estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="6e8fc-121">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-121">Click **Commit**.</span></span>
    
<span data-ttu-id="6e8fc-p104">Em seguida, adicione sub-redes ao site da rede, conforme descrito em [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). Depois que você associar todas as sub-redes aos locais de rede, a implantação do bypass de mídia estará completa.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="6e8fc-124">Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="6e8fc-125">Para obter detalhes, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="6e8fc-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e8fc-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6e8fc-126">See also</span></span>

[<span data-ttu-id="6e8fc-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="6e8fc-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

