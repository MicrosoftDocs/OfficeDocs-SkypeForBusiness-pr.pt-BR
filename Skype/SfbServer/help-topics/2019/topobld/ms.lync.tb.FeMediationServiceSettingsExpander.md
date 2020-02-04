---
title: Expansor de Configurações de Serviço de Mediação
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'No caso do Servidor de Mediação, você pode especificar o seguinte:'
ms.openlocfilehash: badc56265dfab1e8c1a46f7a3d9f122ec845d162
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702176"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="71232-103">Expansor de Configurações de Serviço de Mediação</span><span class="sxs-lookup"><span data-stu-id="71232-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="71232-104">No caso do **Servidor de Mediação**, você pode especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71232-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="71232-105">Se você estiver posicionando o servidor de mediação no pool de front-ends ou o servidor Standard Edition, marque a caixa de seleção **servidor de mediação posicionado habilitado**.</span><span class="sxs-lookup"><span data-stu-id="71232-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="71232-106">Se você optar por não colocar o servidor de mediação, não haverá configurações definíveis nesta seção.</span><span class="sxs-lookup"><span data-stu-id="71232-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="71232-107">Se você tiver habilitado a colocação do servidor de mediação, será necessário definir o intervalo de portas de escuta no servidor para a segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="71232-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="71232-108">Por padrão, essa porta é a 5067.</span><span class="sxs-lookup"><span data-stu-id="71232-108">By default, this port is 5067.</span></span> <span data-ttu-id="71232-109">Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado.</span><span class="sxs-lookup"><span data-stu-id="71232-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="71232-110">Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso.</span><span class="sxs-lookup"><span data-stu-id="71232-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="71232-111">Por padrão, o valor de porta TCP é 5068.</span><span class="sxs-lookup"><span data-stu-id="71232-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="71232-112">Você define os gateways PSTN associados ao servidor de mediação posicionado.</span><span class="sxs-lookup"><span data-stu-id="71232-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="71232-113">Se você já definiu gateways, eles estarão disponíveis para serem associados ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="71232-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="71232-114">Se você tiver mais de um gateway associado a um servidor de mediação, o primeiro gateway associado será o gateway padrão.</span><span class="sxs-lookup"><span data-stu-id="71232-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="71232-115">Se precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**.</span><span class="sxs-lookup"><span data-stu-id="71232-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="71232-116">Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.</span><span class="sxs-lookup"><span data-stu-id="71232-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="71232-117">Para obter detalhes sobre como definir e definir as configurações do pool de front-end do Enterprise Edition ou do servidor Standard Edition, consulte [definindo e configurando a topologia](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [implantando servidores de mediação e definindo pares](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="71232-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


