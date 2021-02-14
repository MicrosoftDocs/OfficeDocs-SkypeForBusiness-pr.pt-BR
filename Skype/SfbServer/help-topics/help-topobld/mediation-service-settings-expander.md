---
title: Expansor de Configurações de Serviço de Mediação
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Para o  Servidor de Mediação, você pode especificar:'
ms.openlocfilehash: 0e6e9101b8b0a530b0f47411f1d8ce1eaa2e01b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810271"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="12f99-103">Expansor de Configurações de Serviço de Mediação</span><span class="sxs-lookup"><span data-stu-id="12f99-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="12f99-104">Para o  **Servidor de Mediação**, você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="12f99-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="12f99-105">Se você estiver posicionada o Servidor de Mediação no pool de Front-End ou no servidor Standard Edition, marque a caixa de seleção Servidor de Mediação **Alocado habilitado.**</span><span class="sxs-lookup"><span data-stu-id="12f99-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="12f99-106">Se você escolher não posicionar o Servidor de Mediação, não haverá configurações para definição nesta seção.</span><span class="sxs-lookup"><span data-stu-id="12f99-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="12f99-p102">Se você tiver habilitado o posicionamento do Servidor de Mediação, será necessário definir o intervalo de porta de escuta no servidor para Transport Layer Security (TLS). Por padrão, essa porta é 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP (Transmission Control Protocol) para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.</span><span class="sxs-lookup"><span data-stu-id="12f99-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="12f99-p103">Defina os gateways PSTN associados ao Servidor de Mediação posicionado. Se você já tiver definido os gateways, eles estarão disponíveis para associação com o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="12f99-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="12f99-p104">Se houver mais de um gateway associado ao Servidor de Mediação, o primeiro gateway associado será o gateway padrão. Se você precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**. Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.</span><span class="sxs-lookup"><span data-stu-id="12f99-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="12f99-117">Para obter detalhes sobre como definir e definir as configurações para o pool de front-end Enterprise Edition ou servidor Standard Edition, consulte [Definindo](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e configurando a topologia e implantando servidores de mediação e [definindo pares.](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)</span><span class="sxs-lookup"><span data-stu-id="12f99-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


