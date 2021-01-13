---
title: Práticas recomendadas para sua infraestrutura principal no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Provavelmente, você já executou etapas para designar a tolerância a falha em seu sistema, usando práticas como a garantia da redundância de hardware, proteção contra perda de energia, instalação rotineira de atualizações de segurança e medidas antivírus, e atividade do Monitoring Server. Essas práticas beneficiam não apenas a infraestrutura do Skype for Business Server, mas também toda a rede. Se você não implementou essas práticas, recomendamos que o faça antes de implantar o Skype for Business Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832241"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="e4a5d-105">Práticas recomendadas para sua infraestrutura principal no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e4a5d-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="e4a5d-106">Provavelmente, você já executou etapas para designar a tolerância a falha em seu sistema, usando práticas como a garantia da redundância de hardware, proteção contra perda de energia, instalação rotineira de atualizações de segurança e medidas antivírus, e atividade do Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="e4a5d-107">Essas práticas beneficiam não apenas a infraestrutura do Skype for Business Server, mas também toda a rede.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="e4a5d-108">Se você não implementou essas práticas, recomendamos que o faça antes de implantar o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="e4a5d-109">Para ajudar a proteger os servidores em sua implantação do Skype for Business Server contra danos acidentais ou proposital que possam resultar em tempo de inatividade, tome as seguintes precauções:</span><span class="sxs-lookup"><span data-stu-id="e4a5d-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="e4a5d-110">Mantenha em dia as atualizações de segurança nos servidores.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="e4a5d-111">Inscreva-se no serviço Microsoft Security Notification Service para receber uma notificação imediata do lançamento de boletins de segurança referentes a qualquer produto da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="e4a5d-112">Para se inscrever, acesse o site de Notificações de Segurança Técnica [da Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=145202)</span><span class="sxs-lookup"><span data-stu-id="e4a5d-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="e4a5d-113">Certifique-se de que os direitos de acesso estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="e4a5d-p104">Mantenha os servidores em um ambiente físico que evite o acesso não autorizado. Verifique se um software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do aplicativo antivírus para deixar essas assinaturas sempre em dia.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="e4a5d-118">Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não são necessários nos computadores em que você instala o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="e4a5d-119">Criptografe os sistemas operacionais e as unidades de disco nos quais os dados são armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir um controle constante e completo dos servidores, isolamento físico total e descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="e4a5d-120">Desabilite todas as portas DMA (Acesso direto à memória) externas do servidor, a menos que você possa garantir um controle muito rígido sobre o acesso físico aos servidores.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="e4a5d-121">Os ataques baseados em DMA, que podem ser iniciados com bastante facilidade, podem expor informações muito confidenciais, como chaves de criptografia privadas.</span><span class="sxs-lookup"><span data-stu-id="e4a5d-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

