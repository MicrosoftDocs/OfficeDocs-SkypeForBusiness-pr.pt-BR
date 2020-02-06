---
title: Solicitar, Instalar ou Atribuir Certificados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: 'Etapa 3: solicitar, instalar ou atribuir certificados inicia o Assistente de Certificado quando você clica em Executar. Os certificados configurados por meio do assistente são baseados na definição da topologia do Skype for Business Server 2015 configurada e publicada pelo construtor de topologias para o repositório de gerenciamento central. Para executar com êxito o Assistente de Certificado para uma autoridade de certificação (AC) online em sua organização, é necessário estar conectado ao computador como usuário membro do grupo de administradores local do computador. Também é necessário ser um Usuário de Domínio autenticado no domínio no qual o computador e a AC existem. O assistente de certificado fornece a capacidade de especificar credenciais alternativas para acessar a autoridade de certificação da sua organização.'
ms.openlocfilehash: c407a0809b4cd3a71b0e1e15a3a5ac33176b9cc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823405"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="390b2-107">Solicitar, Instalar ou Atribuir Certificados</span><span class="sxs-lookup"><span data-stu-id="390b2-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="390b2-108">**Etapa 3: solicitar, instalar ou atribuir certificados** inicia o Assistente de Certificado quando você clica em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="390b2-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="390b2-109">Os certificados configurados por meio do assistente são baseados na definição da topologia do Skype for Business Server 2015 configurada e publicada pelo construtor de topologias para o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="390b2-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="390b2-110">Para executar com êxito o Assistente de Certificado para uma autoridade de certificação (AC) online em sua organização, é necessário estar conectado ao computador como usuário membro do grupo de administradores local do computador.</span><span class="sxs-lookup"><span data-stu-id="390b2-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="390b2-111">Também é necessário ser um Usuário de Domínio autenticado no domínio no qual o computador e a AC existem.</span><span class="sxs-lookup"><span data-stu-id="390b2-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="390b2-112">O assistente de certificado fornece a capacidade de especificar credenciais alternativas para acessar a autoridade de certificação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="390b2-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="390b2-p103">Também é possível usar o Assistente de Certificado para solicitar e processar as solicitações de certificado offline enviadas a uma AC pública ou outra PKI (infraestrutura de chave pública) offline. Não há associações de grupo específicas, além das necessárias para fazer logon no computador, para gerar uma solicitação offline. Para processar a resposta da AC pública e atribuir o certificado ao computador e função, é necessário estar conectado como membro do grupo local Administradores ou equivalente.</span><span class="sxs-lookup"><span data-stu-id="390b2-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

