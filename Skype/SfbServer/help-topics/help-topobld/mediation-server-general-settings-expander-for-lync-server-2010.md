---
title: Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Você edita as propriedades dos servidores de mediação nesta caixa de diálogo. Ao longo do lado esquerdo, há um conjunto de links rápidos para levá-lo às configurações gerais, às próximas configurações de salto e configurações de gateway PSTN. Em cada seção, encontram-se as seguintes configurações:'
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684544"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="cea3a-105">Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cea3a-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="cea3a-106">Você edita as propriedades dos servidores de mediação nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cea3a-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="cea3a-107">Ao longo do lado esquerdo, há um conjunto de links rápidos para levá-lo às configurações gerais, às próximas configurações de salto e configurações de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="cea3a-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="cea3a-108">Em cada seção, encontram-se as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="cea3a-108">In each section are the following settings:</span></span>

 <span data-ttu-id="cea3a-109">**Geral**:</span><span class="sxs-lookup"><span data-stu-id="cea3a-109">**General**:</span></span>

- <span data-ttu-id="cea3a-110">**FQDN**: você edita o nome de domínio totalmente qualificado do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="cea3a-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="cea3a-111">**Associações**: marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** e selecione um servidor de borda ou um pool de bordas para o servidor de mediação usar como o caminho de mídia para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="cea3a-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="cea3a-112">**Próximo salto**:</span><span class="sxs-lookup"><span data-stu-id="cea3a-112">**Next hop**:</span></span>

- <span data-ttu-id="cea3a-113">**Seleção do próximo salto**: selecione em uma lista o servidor front-end ou o pool de front-end a ser usado como o caminho para o servidor de mediação usar para se comunicar com sua implantação.</span><span class="sxs-lookup"><span data-stu-id="cea3a-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="cea3a-114">**Gateway PSTN**:</span><span class="sxs-lookup"><span data-stu-id="cea3a-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="cea3a-115">**Gateway PSTN do servidor de mediação**:</span><span class="sxs-lookup"><span data-stu-id="cea3a-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="cea3a-116">**Portas de escuta**: defina as portas que o servidor de mediação escutará.</span><span class="sxs-lookup"><span data-stu-id="cea3a-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="cea3a-117">Você pode definir uma porta para **TLS** ou Transport Layer Security ou **TCP**ou protocolo de controle de transporte.</span><span class="sxs-lookup"><span data-stu-id="cea3a-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="cea3a-118">Para que a entrada de porta TCP esteja disponível, você deve marcar a caixa de seleção **habilitar porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="cea3a-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cea3a-119">Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se você precisa habilitar e definir valores de porta TLS, TCP ou ambos.</span><span class="sxs-lookup"><span data-stu-id="cea3a-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="cea3a-120">O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="cea3a-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="cea3a-121">Nem todos os gateways PSTN dão suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="cea3a-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="cea3a-122">Uma lista de troncos SIP e os gateways definidos e configurados para a sua implantação está listada.</span><span class="sxs-lookup"><span data-stu-id="cea3a-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="cea3a-123">Se não houver entradas presentes, não há troncos SIP ou gateways PSTN configurados para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="cea3a-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="cea3a-124">Você define e configura troncos e gateways em **componentes compartilhados** no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="cea3a-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="cea3a-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="cea3a-125">See also</span></span>

[<span data-ttu-id="cea3a-126">Visão geral do entroncamento SIP</span><span class="sxs-lookup"><span data-stu-id="cea3a-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="cea3a-127">Opções de implantação do gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="cea3a-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
