---
title: Expansor de Configurações Gerais de Servidor de Mediação
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a00573b06c1900718fd670c96a21ffab069b491e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806721"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="0bc40-102">Expansor de Configurações Gerais de Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="0bc40-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="0bc40-103">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="0bc40-103">General settings</span></span>

<span data-ttu-id="0bc40-p101">FQDN (nome de domínio totalmente qualificado) do Servidor de Mediação ou pool de Servidor de Mediação. Edite o FQDN do servidor para alterar o valor. Você deve ter um registro de hospedeiro (A) DNS (Domain Name System) coincidente com o novo valor.</span><span class="sxs-lookup"><span data-stu-id="0bc40-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="0bc40-107">Na seção **Associações** , você seleciona um pool de Servidor de Borda ou Servidor de Borda para associar ao pool de Servidor de Mediação ou Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="0bc40-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="0bc40-108">Selecione a Borda que os componentes de mídia do Servidor de Mediação usarão para o Enterprise Voice do usuário externo.</span><span class="sxs-lookup"><span data-stu-id="0bc40-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="0bc40-109">Caso você não possua um Servidor de Borda atualmente definido e precise associar o Servidor de Mediação com um Servidor de Borda, clique em **Novo** e defina o novo pool de Servidor de Borda ou Servidor de Borda no assistente Definir Novo pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="0bc40-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="0bc40-110">Configurações de próximo salto</span><span class="sxs-lookup"><span data-stu-id="0bc40-110">Next hop settings</span></span>

<span data-ttu-id="0bc40-111">Você especifica o próximo salto do pool de Servidor de Mediação ou Servidor de Mediação selecionando o pool de Front-Ends Enterprise Edition, ou Servidor Front-Ends Standard Edition, definido a partir da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="0bc40-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="0bc40-112">Um Diretor ou pool de Diretores não é uma seleção válida para um próximo salto de pool de Servidores de Mediação ou de Servidor de Mediação e não aparecerá na lista.</span><span class="sxs-lookup"><span data-stu-id="0bc40-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="0bc40-113">Clique **em OK** para aceitar e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="0bc40-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="0bc40-114">Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="0bc40-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="0bc40-115">Configurações de gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="0bc40-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="0bc40-p104">Defina os gateways PSTN associados ao pool de Servidores de Mediação ou ao Servidor de Mediação. Se você já tiver definido gateways, eles estarão disponíveis para associação com o Servidor de Mediação. Se você habilitar a colocação do Servidor de Mediação, defina o intervalo de porta de escuta nos servidores do pool para Transport Layer Security (TLS). Por padrão, essa porta é 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP (Transmission Control Protocol) para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deve consultar os requisitos de seu gateway ou requisitos PSTN a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.</span><span class="sxs-lookup"><span data-stu-id="0bc40-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="0bc40-p105">Troncos associados ao Servidor de Mediação posicionado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="0bc40-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="0bc40-p106">Se você tiver mais de um tronco associado a um Servidor de Mediação, poderá especificar um tronco padrão selecionando o tronco e clicando em **Tornar Padrão**. Para desmarcar um gateway como padrão, clique em **Desfazer Padrão**.</span><span class="sxs-lookup"><span data-stu-id="0bc40-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

