---
title: Expansor de Configurações de Serviço de Mediação
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Para o servidor de mediação, você pode especificar o seguinte:'
ms.openlocfilehash: e322b2ffd383c2bd0170852a6fec6c3122251700
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="5c0ac-103">Expansor de Configurações de Serviço de Mediação</span><span class="sxs-lookup"><span data-stu-id="5c0ac-103">Mediation Service Settings Expander</span></span>
 
<span data-ttu-id="5c0ac-104">Em **Servidor de Mediação**, você pode especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5c0ac-104">For **Mediation Server**, you can specify the following:</span></span>
  
<span data-ttu-id="5c0ac-105">Se você estiver colocando o servidor de mediação para o pool de Front-End ou servidor Standard Edition, marque a caixa de seleção **servidor de mediação posicionado habilitado**.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="5c0ac-106">Se você escolher não coloque o servidor de mediação, não há nenhuma configuração definíveis nesta seção.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span> 
  
<span data-ttu-id="5c0ac-107">Se você tiver habilitado a colocação do servidor de mediação, você precisará definir o intervalo de portas de escuta do servidor para a segurança de camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="5c0ac-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="5c0ac-108">Por padrão, essa porta é a 5067.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-108">By default, this port is 5067.</span></span> <span data-ttu-id="5c0ac-109">Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="5c0ac-110">Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="5c0ac-111">Por padrão, o valor de porta TCP é 5068.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-111">By default, the TCP port value is 5068.</span></span>
  
<span data-ttu-id="5c0ac-112">Você define os gateways PSTN associados com o servidor de mediação colocado.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="5c0ac-113">Se você já tenha definido gateways, eles estarão disponíveis para associar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> 
  
<span data-ttu-id="5c0ac-114">Se você tiver mais de um gateway associado a um servidor de mediação, o primeiro gateway associado será o gateway padrão.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="5c0ac-115">Se precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="5c0ac-116">Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.</span><span class="sxs-lookup"><span data-stu-id="5c0ac-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>
  
<span data-ttu-id="5c0ac-117">Para obter detalhes sobre como definir e configurar as definições para o pool de Front End do Enterprise Edition ou servidor Standard Edition, consulte [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c0ac-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  

