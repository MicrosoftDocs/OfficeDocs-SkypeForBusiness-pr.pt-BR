---
title: Expansor de Configurações de Tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:'
ms.openlocfilehash: aa3c8dd622e64bcd063e84d1f6e19278af9a6cff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819143"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="6a8e2-103">Expansor de Configurações de Tronco</span><span class="sxs-lookup"><span data-stu-id="6a8e2-103">Trunk Settings Expander</span></span>

<span data-ttu-id="6a8e2-104">Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6a8e2-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="6a8e2-105">**Nome do tronco** é uma entrada necessária e identifica exclusivamente o tronco SIP na implantação.</span><span class="sxs-lookup"><span data-stu-id="6a8e2-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="6a8e2-106">**Gateway PSTN associado**: selecione um gateway PSTN existente definido na implantação.</span><span class="sxs-lookup"><span data-stu-id="6a8e2-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="6a8e2-p101">**Porta de escuta para gateway IP/PSTN**: indica em qual porta TCP/IP o gateway escutará as solicitações. O valor necessário pode variar com base no fornecedor do gateway, mas o padrão é a porta 5067.</span><span class="sxs-lookup"><span data-stu-id="6a8e2-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="6a8e2-p102">**Protocolo de Transporte SIP**: protocolo usado pode ser TCP ou TLS. TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o suporte incluído no seu gateway. Como o padrão é TLS, ele deve ser considerado a seleção mais segura, caso o gateway ofereça suporte para TLS.</span><span class="sxs-lookup"><span data-stu-id="6a8e2-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="6a8e2-113">**Servidor de mediação associado**: selecione um servidor de mediação existente na implantação para associá-lo ao tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="6a8e2-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="6a8e2-114">Somente o tronco raiz podem ser associados a um servidor do Lync Server 2010 ou ao Lync Server 2013 Media Server.</span><span class="sxs-lookup"><span data-stu-id="6a8e2-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="6a8e2-115">**Porta do servidor de mediação associada**: um valor obrigatório; isso é definido como o valor que o servidor de mediação está configurado para escuta.</span><span class="sxs-lookup"><span data-stu-id="6a8e2-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Expansor de Configurações de Tronco](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="6a8e2-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="6a8e2-117">See also</span></span>

[<span data-ttu-id="6a8e2-118">Lista de verificação de implantação de entroncamento SIP</span><span class="sxs-lookup"><span data-stu-id="6a8e2-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="6a8e2-119">Componentes e topologias para entroncamento SIP</span><span class="sxs-lookup"><span data-stu-id="6a8e2-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
