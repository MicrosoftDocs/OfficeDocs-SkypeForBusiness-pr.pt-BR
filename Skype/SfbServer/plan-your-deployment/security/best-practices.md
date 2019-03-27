---
title: Práticas recomendadas para a infraestrutura principal no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server. Essas práticas beneficiam não apenas sua Skype infra-estrutura de servidor de negócios, mas também toda a sua rede. Se você não implementou essas práticas, recomendamos que você faça isso antes de implantar o Skype para Business Server.
ms.openlocfilehash: 86d18e1d9d34b5f65f4cb938e13a9829af1646bb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885803"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="d5b14-105">Práticas recomendadas para a infraestrutura principal no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d5b14-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="d5b14-106">Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="d5b14-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="d5b14-107">Essas práticas beneficiam não apenas sua Skype infra-estrutura de servidor de negócios, mas também toda a sua rede.</span><span class="sxs-lookup"><span data-stu-id="d5b14-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="d5b14-108">Se você não implementou essas práticas, recomendamos que você faça isso antes de implantar o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5b14-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="d5b14-109">Para ajudar a proteger os servidores no seu Skype para implantação de servidor de negócios contra danos acidentais ou intencionais que possam resultar na inatividade do sistema, tome as seguintes precauções:</span><span class="sxs-lookup"><span data-stu-id="d5b14-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="d5b14-110">Mantenha os servidores atualizados com atualizações de segurança.</span><span class="sxs-lookup"><span data-stu-id="d5b14-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="d5b14-111">A assinatura do Microsoft Security Notification Service ajuda a garantir que você receba notificações imediatas de versões de boletim de segurança de qualquer produto da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5b14-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="d5b14-112">Para assinar, visite o [site de notificações de segurança técnica da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="d5b14-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="d5b14-113">Verifique se os direitos de acesso estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="d5b14-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="d5b14-p104">Mantenha os servidores em um ambiente físico que impeça o acesso não autorizado. Verifique se o software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do seu aplicativo antivírus para manter as assinaturas de vírus atuais.</span><span class="sxs-lookup"><span data-stu-id="d5b14-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="d5b14-118">Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não forem necessários nos computadores onde você instala o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5b14-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="d5b14-119">Criptografe os sistemas operacionais e as unidades de disco em que os dados estiverem armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir o controle constante e completo dos servidores, o isolamento típico total e o descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.</span><span class="sxs-lookup"><span data-stu-id="d5b14-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="d5b14-120">Desabilite todas as portas de DMA (Acesso Remoto Direto à Memória) externas do servido, a menos que você possa garantir o controle muito rigoroso sobre o acesso físico aos servidores.</span><span class="sxs-lookup"><span data-stu-id="d5b14-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="d5b14-121">Ataques baseados em DMA, que podem ser iniciados de modo razoavelmente fácil, podem expor informações confidenciais, como chaves de criptografia privada.</span><span class="sxs-lookup"><span data-stu-id="d5b14-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

