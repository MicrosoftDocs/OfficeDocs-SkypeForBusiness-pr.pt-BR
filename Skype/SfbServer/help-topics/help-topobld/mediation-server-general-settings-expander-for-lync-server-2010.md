---
title: Expansor de configurações gerais do servidor de mediação do Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Você editar as propriedades dos servidores de mediação nessa caixa de diálogo. No lado esquerdo é um conjunto de links rápidos para orientá-lo às definições de configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção são as seguintes configurações:'
ms.openlocfilehash: 0d3601731473b3d48b8199ee69f1e3ed18e806b9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967793"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ddef9-105">Expansor de configurações gerais do servidor de mediação do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ddef9-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ddef9-106">Você editar as propriedades dos servidores de mediação nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ddef9-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="ddef9-107">No lado esquerdo é um conjunto de links rápidos para orientá-lo às definições de configurações gerais, configurações de próximo salto e configurações de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ddef9-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="ddef9-108">Em cada seção são as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="ddef9-108">In each section are the following settings:</span></span>
  
 <span data-ttu-id="ddef9-109">**Geral**:</span><span class="sxs-lookup"><span data-stu-id="ddef9-109">**General**:</span></span>
  
- <span data-ttu-id="ddef9-110">**FQDN**: editar o nome de domínio totalmente qualificado do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="ddef9-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>
    
- <span data-ttu-id="ddef9-111">**Associações**: marque a caixa de seleção **associar pool de borda (para componentes de mídia)** e selecione um servidor de borda ou o pool de borda para o servidor de mediação para usar como o caminho de mídia para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="ddef9-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>
    
 <span data-ttu-id="ddef9-112">**Próximo salto**:</span><span class="sxs-lookup"><span data-stu-id="ddef9-112">**Next hop**:</span></span>
  
- <span data-ttu-id="ddef9-113">**Seleção do próximo salto**: selecione em uma lista ao pool do servidor Front-End ou Front-End para usar como o caminho para o servidor de mediação a ser usado para comunicação com sua implantação.</span><span class="sxs-lookup"><span data-stu-id="ddef9-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>
    
 <span data-ttu-id="ddef9-114">**Gateway PSTN**:</span><span class="sxs-lookup"><span data-stu-id="ddef9-114">**PSTN gateway**:</span></span>
  
 <span data-ttu-id="ddef9-115">**Gateway PSTN do servidor de mediação**:</span><span class="sxs-lookup"><span data-stu-id="ddef9-115">**Mediation Server PSTN gateway**:</span></span>
  
- <span data-ttu-id="ddef9-116">**Portas de escuta**: definir as portas que o servidor de mediação escutará.</span><span class="sxs-lookup"><span data-stu-id="ddef9-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="ddef9-117">Você pode definir uma porta para segurança de camada de transporte ou **TLS** ou **TCP**, ou o protocolo de controle de transporte.</span><span class="sxs-lookup"><span data-stu-id="ddef9-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="ddef9-118">Para a entrada de porta para TCP esteja disponível, você deve selecionar a caixa de seleção para **Habilitar TCP porta**.</span><span class="sxs-lookup"><span data-stu-id="ddef9-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ddef9-119">Consulte as configurações de documentação e configuração de seu gateway PSTN (rede) telefônica pública comutada para determinar se você precisa habilitar e definir valores de portas TLS, TCP ou ambos.</span><span class="sxs-lookup"><span data-stu-id="ddef9-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="ddef9-120">O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ddef9-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="ddef9-121">Nem todos os gateways PSTN suportam TLS.</span><span class="sxs-lookup"><span data-stu-id="ddef9-121">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="ddef9-122">Uma lista de troncos SIP e gateways que são definidos e configurados para sua implantação está listada.</span><span class="sxs-lookup"><span data-stu-id="ddef9-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="ddef9-123">Se nenhuma entrada estiverem presente, não existem configurados para sua implantação de gateways PSTN ou troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="ddef9-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="ddef9-124">Definir e configurar gateways em **Componentes compartilhados** e troncos no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="ddef9-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ddef9-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ddef9-125">See also</span></span>

[<span data-ttu-id="ddef9-126">Visão geral dos troncos SIP</span><span class="sxs-lookup"><span data-stu-id="ddef9-126">Overview of SIP Trunking</span></span>](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[<span data-ttu-id="ddef9-127">Opções de implantação de Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="ddef9-127">PSTN Gateway Deployment Options</span></span>](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)