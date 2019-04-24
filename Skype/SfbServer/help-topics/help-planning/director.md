---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Um diretor é um servidor que executa o Skype Business Server 2015 software de comunicações que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário.
ms.openlocfilehash: b6cdecd01183f8e249aaf97e6b4e7bbbbfcbe7cd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200292"
---
# <a name="director-planning-tool"></a><span data-ttu-id="1f5f2-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="1f5f2-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="1f5f2-104">Um diretor é um servidor que executa o Skype Business Server 2015 software de comunicações que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="1f5f2-105">Essa função é opcional, que você escolheria implantar um diretor em dois cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="1f5f2-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="1f5f2-106">Se você habilitar o acesso por usuários externos implantando servidores de borda, você também deve implantar um diretor.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="1f5f2-107">Neste cenário, o Diretor autentica os usuários externos e, em seguida, passa o tráfego para os servidores internos.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="1f5f2-108">Quando um diretor é usado para autenticar usuários externos, ele libera os servidores de pool de Front-End da sobrecarga de realizar a autenticação desses usuários.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="1f5f2-109">Isso também ajuda a isolar os pools de Front-End internos contra tráfego malicioso, como ataques de negação de serviço.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="1f5f2-110">Se a rede é inundada com o tráfego externo inválido nesse ataque, esse tráfego termina no diretor.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="1f5f2-111">Se você implantar vários pools de Front-End em um site central, adicionando um diretor para esse site pode simplificar a solicitações de autenticação e melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="1f5f2-112">Neste cenário, todas as solicitações vão primeira para o diretor, que, em seguida, encaminha-los para o pool de Front-End correto.</span><span class="sxs-lookup"><span data-stu-id="1f5f2-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

