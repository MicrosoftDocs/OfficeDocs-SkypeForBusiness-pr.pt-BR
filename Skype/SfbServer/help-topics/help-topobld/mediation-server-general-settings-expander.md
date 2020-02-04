---
title: Expansor de Configurações Gerais de Servidor de Mediação
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a460cfcaf696740fa108be451156d53bec96f95d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696996"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="899a0-102">Expansor de Configurações Gerais de Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="899a0-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="899a0-103">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="899a0-103">General settings</span></span>

<span data-ttu-id="899a0-104">Nome de domínio totalmente qualificado (FQDN) do pool do servidor de mediação ou do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="899a0-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="899a0-105">Edite o FQDN do servidor para alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="899a0-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="899a0-106">É necessário ter um registro (A) de host de Sistema de Nomes de Domínio (DNS) que coincida com o novo valor.</span><span class="sxs-lookup"><span data-stu-id="899a0-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="899a0-107">Na seção **associações** , selecione um servidor de borda ou um pool de servidores de borda para associar ao pool do servidor de mediação ou ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="899a0-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="899a0-108">Você seleciona a borda que os componentes de mídia do servidor de mediação usarão para o usuário externo de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="899a0-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="899a0-109">Se você não tiver um servidor de borda atualmente definido e precisar associar o servidor de mediação a um servidor de borda, clique em **novo** e defina o novo servidor de borda ou o pool de servidor de borda no assistente definir o novo pool de borda.</span><span class="sxs-lookup"><span data-stu-id="899a0-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="899a0-110">Configurações de próximo salto</span><span class="sxs-lookup"><span data-stu-id="899a0-110">Next hop settings</span></span>

<span data-ttu-id="899a0-111">Você especifica o pool do servidor de mediação ou o servidor de mediação próximo nó, selecionando o pool de front-end Enterprise Edition definido ou o servidor front-end Standard Edition na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="899a0-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="899a0-112">Um diretor ou um pool de diretor não é uma seleção válida para um pool do servidor de mediação ou servidor de mediação próximo salto e não aparecerá na lista.</span><span class="sxs-lookup"><span data-stu-id="899a0-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="899a0-113">Clique em **OK** para aceitar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="899a0-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="899a0-114">Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="899a0-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="899a0-115">Configurações de gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="899a0-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="899a0-116">Você define os gateways PSTN associados ao pool do servidor de mediação ou ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="899a0-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="899a0-117">Se você já definiu gateways, eles estarão disponíveis para serem associados ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="899a0-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="899a0-118">Se você habilitar a colocação do Servidor de Mediação, defina o intervalo de porta de escuta nos servidores do pool para TLS.</span><span class="sxs-lookup"><span data-stu-id="899a0-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="899a0-119">Por padrão, essa porta é a 5067.</span><span class="sxs-lookup"><span data-stu-id="899a0-119">By default, this port is 5067.</span></span> <span data-ttu-id="899a0-120">Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado.</span><span class="sxs-lookup"><span data-stu-id="899a0-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="899a0-121">Essa é uma configuração opcional, e você deverá verificar seus requisitos de gateway ou PSTN a fim de determinar se isso é necessário.</span><span class="sxs-lookup"><span data-stu-id="899a0-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="899a0-122">Por padrão, o valor da porta TCP é 5068.</span><span class="sxs-lookup"><span data-stu-id="899a0-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="899a0-p105">Troncos associados ao Servidor de Mediação colocado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="899a0-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="899a0-125">Se você tiver mais de um tronco associado a um servidor de mediação, poderá especificar um tronco padrão selecionando o tronco e, em seguida, clicando em **tornar padrão**.</span><span class="sxs-lookup"><span data-stu-id="899a0-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="899a0-126">Para desmarcar um gateway como padrão, clique em **Desfazer Padrão**.</span><span class="sxs-lookup"><span data-stu-id="899a0-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

