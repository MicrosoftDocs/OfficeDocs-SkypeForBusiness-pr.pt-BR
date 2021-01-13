---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Um Diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015 que pode autenticar solicitações de usuário, mas não tem contas de usuário.
ms.openlocfilehash: 9809a6293c212a52dd87476069125540848ee2a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810541"
---
# <a name="director-planning-tool"></a><span data-ttu-id="16daf-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="16daf-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="16daf-104">Um Diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015 que pode autenticar solicitações de usuário, mas não tem contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="16daf-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="16daf-105">Essa função é opcional, você pode optar por implantar um Diretor nos dois cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="16daf-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="16daf-106">Se você habilitar o acesso por usuários externos implantando Servidores de Borda, também deverá implantar um Diretor.</span><span class="sxs-lookup"><span data-stu-id="16daf-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="16daf-107">Nesse cenário, o Diretor autentica os usuários externos e, em seguida, passa seu tráfego para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="16daf-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="16daf-108">Quando um Diretor é usado para autenticar usuários externos, libera os servidores do pool de Front End da sobrecarga de executar a autenticação desses usuários.</span><span class="sxs-lookup"><span data-stu-id="16daf-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="16daf-109">Ele também ajuda a isolar pools de Front-End internos de tráfego mal-intencionado, como ataques de negação de serviço.</span><span class="sxs-lookup"><span data-stu-id="16daf-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="16daf-110">Se a rede é preenchida com tráfego externo inválido em tal ataque, este tráfego termina no Diretor.</span><span class="sxs-lookup"><span data-stu-id="16daf-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="16daf-111">Se você implantar vários pools de Front-End em um site central, adicionando um Diretor a esse site, você poderá simplificar as solicitações de autenticação e melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="16daf-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="16daf-112">Nesse cenário, todas as solicitações vão primeiro para o Diretor, que as encaminha para o pool de Front-End correto.</span><span class="sxs-lookup"><span data-stu-id="16daf-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

