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
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Edite as propriedades dos servidores de mediação nesta caixa de diálogo. Ao longo do lado esquerdo, há um conjunto de links rápidos que levam você às configurações para configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:'
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215152"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="f761d-105">Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f761d-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="f761d-106">Edite as propriedades dos servidores de mediação nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f761d-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="f761d-107">Ao longo do lado esquerdo, há um conjunto de links rápidos que levam você às configurações para configurações gerais, configurações de próximo salto e configurações de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f761d-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="f761d-108">Em cada seção estão as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f761d-108">In each section are the following settings:</span></span>

 <span data-ttu-id="f761d-109">**Geral**:</span><span class="sxs-lookup"><span data-stu-id="f761d-109">**General**:</span></span>

- <span data-ttu-id="f761d-110">**FQDN**: você edita o nome de domínio totalmente qualificado do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="f761d-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="f761d-111">**Associações**: marque a caixa de seleção **associar pool de borda (para componentes de mídia)** e selecione um servidor de borda ou um pool de borda para o servidor de mediação usar como o caminho de mídia para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="f761d-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="f761d-112">**Próximo salto**:</span><span class="sxs-lookup"><span data-stu-id="f761d-112">**Next hop**:</span></span>

- <span data-ttu-id="f761d-113">**Seleção do próximo salto**: selecione de uma lista o servidor front-end ou o pool de front-ends a ser usado como o caminho para o servidor de mediação usar para a comunicação com sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f761d-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="f761d-114">**Gateway PSTN**:</span><span class="sxs-lookup"><span data-stu-id="f761d-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="f761d-115">**Gateway PSTN do servidor de mediação**:</span><span class="sxs-lookup"><span data-stu-id="f761d-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="f761d-116">**Portas de escuta**: defina as portas nas quais o servidor de mediação escutará.</span><span class="sxs-lookup"><span data-stu-id="f761d-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="f761d-117">É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol.</span><span class="sxs-lookup"><span data-stu-id="f761d-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="f761d-118">Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="f761d-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f761d-119">Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos.</span><span class="sxs-lookup"><span data-stu-id="f761d-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="f761d-120">O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f761d-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="f761d-121">Nem todos os gateways PSTN suportam TLS.</span><span class="sxs-lookup"><span data-stu-id="f761d-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="f761d-122">Uma lista de troncos SIP e os gateways definidos e configurados para sua implantação são listados.</span><span class="sxs-lookup"><span data-stu-id="f761d-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="f761d-123">Se nenhuma entrada estiver presente, não haverá troncos SIP ou gateways PSTN configurados para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f761d-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="f761d-124">Você define e configura troncos e gateways em **componentes compartilhados** no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f761d-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="f761d-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="f761d-125">See also</span></span>

[<span data-ttu-id="f761d-126">Visão geral dos troncos SIP</span><span class="sxs-lookup"><span data-stu-id="f761d-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="f761d-127">Opções de implantação do gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="f761d-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
