---
title: Atualizar o certificado de borda
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui as etapas detalhadas para atualizar o certificado de borda como parte da consolidação de nuvem para equipes e Skype para negócios.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247594"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="02283-103">Atualizar o certificado de borda</span><span class="sxs-lookup"><span data-stu-id="02283-103">Update the edge certificate</span></span>

<span data-ttu-id="02283-104">Atualizar o certificado de borda é a etapa de chave para garantir que um ambiente em prem com SipDomain1 pode ingressar em um ambiente de nuvem com SipDomain2 e garantir o roteamento apropriado em um ambiente de espaço de endereçamento compartilhado entre os dois domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="02283-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="02283-105">Consulte a etapa 14 da [consolidação de nuvem para equipes e Skype para negócios](cloud-consolidation.md) de contexto no qual você pode executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="02283-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="02283-106">Em nossos exemplos, SipDomain1 é AcquiredCompany. <span>SipDomain2 e com é OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="02283-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="02283-107">Nome alternativo da entidade (SAN) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP que existem no locatário online puro (excluindo qualquer onmicrosoft.<span> domínios com), no formato "sip. \<domínio > ".</span><span class="sxs-lookup"><span data-stu-id="02283-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="02283-108">No nosso exemplo, este é o sip. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="02283-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="02283-109">Esta etapa é fundamental para fazer antes de migrar todos os usuários para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="02283-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="02283-110">**Etapas:**</span><span class="sxs-lookup"><span data-stu-id="02283-110">**Steps:**</span></span>

1.  <span data-ttu-id="02283-111">Obter um novo certificado de borda externa da borda que tenha todas as suas entradas plus entradas adicionais no SAN para todos os domínios SIP no ambiente de nuvem (excluindo \*. onmicrosoft.com domínios) no formato "sip. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="02283-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="02283-112">Instale o certificado localmente em cada servidor de borda e atribuí-lo para o serviço de borda do Skype em cada um do serviço de borda.</span><span class="sxs-lookup"><span data-stu-id="02283-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="02283-113">Para obter etapas detalhadas, consulte a seção "Certificados de interface de borda externa" em [Implantar o serviço de borda no Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="02283-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="02283-114">Reinicie o serviço de borda em cada um dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="02283-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="02283-115">Você pode fazer isso para uma única caixa com os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="02283-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="02283-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="02283-116">See also</span></span>

[<span data-ttu-id="02283-117">Consolidação de nuvem para equipes e Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="02283-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)