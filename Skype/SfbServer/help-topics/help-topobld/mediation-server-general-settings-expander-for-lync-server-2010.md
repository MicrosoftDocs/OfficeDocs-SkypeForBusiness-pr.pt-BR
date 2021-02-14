---
title: Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Edite as propriedades dos Servidores de Mediação nesta caixa de diálogo. No lado esquerdo há um conjunto de links rápidos para levar você às configurações de Configurações Gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:'
ms.openlocfilehash: db7964826a50f462435769d66ddfab3804462541
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806741"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="25431-105">Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="25431-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="25431-106">Edite as propriedades dos Servidores de Mediação nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="25431-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="25431-107">No lado esquerdo há um conjunto de links rápidos para levar você às configurações de Configurações Gerais, configurações de próximo salto e configurações de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="25431-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="25431-108">Em cada seção estão as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="25431-108">In each section are the following settings:</span></span>

 <span data-ttu-id="25431-109">**Geral**:</span><span class="sxs-lookup"><span data-stu-id="25431-109">**General**:</span></span>

- <span data-ttu-id="25431-110">**FQDN**: edite o nome de domínio totalmente qualificado do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="25431-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="25431-111">**Associações:** marque a caixa de seleção Associar Pool de Borda (para componentes de **mídia)** e selecione um Servidor de Borda ou pool de Borda para o Servidor de Mediação a ser usado como o caminho de mídia para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="25431-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="25431-112">**Próximo salto:**</span><span class="sxs-lookup"><span data-stu-id="25431-112">**Next hop**:</span></span>

- <span data-ttu-id="25431-113">**Seleção de próximo salto:** selecione em uma lista o Servidor front-end ou pool de front-end a ser usado como o caminho para o Servidor de Mediação a ser usado para comunicação com sua implantação.</span><span class="sxs-lookup"><span data-stu-id="25431-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="25431-114">**Gateway PSTN:**</span><span class="sxs-lookup"><span data-stu-id="25431-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="25431-115">**Gateway PSTN do Servidor de Mediação:**</span><span class="sxs-lookup"><span data-stu-id="25431-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="25431-116">**Portas de** escuta: defina as portas nas quais o Servidor de Mediação escutará.</span><span class="sxs-lookup"><span data-stu-id="25431-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="25431-117">É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol.</span><span class="sxs-lookup"><span data-stu-id="25431-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="25431-118">Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="25431-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="25431-119">Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos.</span><span class="sxs-lookup"><span data-stu-id="25431-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="25431-120">O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o Servidor de Mediação e o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="25431-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="25431-121">Nem todos os gateways PSTN suportam TLS.</span><span class="sxs-lookup"><span data-stu-id="25431-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="25431-122">Uma listagem de troncos SIP e gateways definidos e configurados para sua implantação é listada.</span><span class="sxs-lookup"><span data-stu-id="25431-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="25431-123">Se não houver entradas, não haverá troncos SIP ou gateways PSTN configurados para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="25431-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="25431-124">Você define e configura troncos e gateways em **Componentes Compartilhados** no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="25431-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="25431-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="25431-125">See also</span></span>

[<span data-ttu-id="25431-126">Visão geral dos troncos SIP</span><span class="sxs-lookup"><span data-stu-id="25431-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="25431-127">Opções de implantação do gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="25431-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
