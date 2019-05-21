---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Um diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015, que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário.
ms.openlocfilehash: a551e2568b814f1811ebc84a8d187c8554cc1542
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288646"
---
# <a name="director-planning-tool"></a><span data-ttu-id="8f3f6-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="8f3f6-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="8f3f6-104">Um diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015, que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="8f3f6-105">Esta função é opcional, você optaria por implantar um diretor nos dois cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="8f3f6-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="8f3f6-106">Se você habilitar o acesso por usuários externos implantando servidores de borda, também deverá implantar um diretor.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="8f3f6-107">Nesse cenário, o diretor autentica os usuários externos e, em seguida, passa o tráfego deles para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="8f3f6-108">Quando um diretor é usado para autenticar usuários externos, ele libera os servidores de pool de front-end da sobrecarga de execução de autenticação desses usuários.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="8f3f6-109">Também ajuda a proteger pools de front-end internos contra tráfego mal-intencionado, como ataques de negação de serviço.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="8f3f6-110">Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, esse tráfego terminará no diretor.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="8f3f6-111">Se você implantar vários pools de front-end em um site central, adicionando um diretor ao site, você pode simplificar solicitações de autenticação e melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="8f3f6-112">Nesse cenário, todas as solicitações entram primeiro no director, que, em seguida, as roteia para o pool de front-end correto.</span><span class="sxs-lookup"><span data-stu-id="8f3f6-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

