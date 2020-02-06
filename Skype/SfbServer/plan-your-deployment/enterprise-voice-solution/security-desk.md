---
title: Inclua a central de segurança no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planejando como incluir a segurança da sua organização em uma implantação do E9-1-1, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 19fc8a01fcb51be3ce36435a5a657c3253716b2c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802451"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="4c23b-103">Inclua a central de segurança no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4c23b-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="4c23b-104">Planejando como incluir a segurança da sua organização em uma implantação do E9-1-1, no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4c23b-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="4c23b-p101">Sua empresa pode exigir que a central de segurança se envolva em uma chamada de emergência. Para ajudar a decidir como integrar a Central de Segurança à sua implantação do E9-1-1, você deve responder às perguntas a seguir.</span><span class="sxs-lookup"><span data-stu-id="4c23b-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="4c23b-107">**Você deseja que o suporte de segurança seja notificado quando houver uma chamada de emergência?**</span><span class="sxs-lookup"><span data-stu-id="4c23b-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="4c23b-108">Você pode configurar a política de localização para que o Skype for Business Server envie alertas de mensagem instantânea aos endereços SIP do Skype for Business de um ou mais funcionários de segurança.</span><span class="sxs-lookup"><span data-stu-id="4c23b-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="4c23b-109">Esses alertas contêm o nome, o número e o local da pessoa que está fazendo a chamada de emergência e facilitam a segurança na assistência com a situação de emergência.</span><span class="sxs-lookup"><span data-stu-id="4c23b-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="4c23b-110">**Deseja estabelecer conferência com o suporte de segurança em cada chamada de emergência?**</span><span class="sxs-lookup"><span data-stu-id="4c23b-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="4c23b-p103">Se tiver suporte do provedor de serviços de emergência, você poderá configurar a política de local para incluir um número de retorno de chamada com cada chamada de emergência. Esse número é usado pelo provedor para estabelecer conferência com a equipe de segurança da sua organização em chamadas de emergência. Essa conferência pode ser configurada na política de local para ser unidirecional (somente escuta) ou bidirecional.</span><span class="sxs-lookup"><span data-stu-id="4c23b-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4c23b-p104">Se desejar, você pode configurar uma equipe de segurança diferente para cada política de local. Isso permite personalizar a resposta para áreas diferentes da empresa ou criar um comportamento diferente para chamadas de emergência que originam da parte interna em oposição à parte externa da rede. Você pode usar grupos de distribuição para especificar o pessoal que deseja notificar.</span><span class="sxs-lookup"><span data-stu-id="4c23b-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

