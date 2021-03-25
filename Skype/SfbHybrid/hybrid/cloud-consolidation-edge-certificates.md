---
title: Atualizar o certificado de borda
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para atualizar o certificado de borda como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120340"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="95a21-103">Atualizar o certificado de borda</span><span class="sxs-lookup"><span data-stu-id="95a21-103">Update the edge certificate</span></span>

<span data-ttu-id="95a21-104">Atualizar o certificado de borda é a etapa fundamental para garantir que um ambiente local com SipDomain1 possa ingressar em um ambiente de nuvem com SipDomain2 e garantir o roteamento adequado em um ambiente de espaço de endereço compartilhado entre os dois domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="95a21-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="95a21-105">Consulte a etapa 14 em [Consolidação de](cloud-consolidation.md) nuvem para o Teams e o Skype for Business para contexto no qual você pode executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="95a21-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="95a21-106">Em nossos exemplos, SipDomain1 é AcquiredCompany. <span> com e SipDomain2 é OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="95a21-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="95a21-107">O nome alternativo do assunto (SAN) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP existentes no locatário online puro (excluindo qualquer onmicrosoft. <span> domínios com), no formato "sip. \<domain> ".</span><span class="sxs-lookup"><span data-stu-id="95a21-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="95a21-108">Em nosso exemplo, isso é sip. OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="95a21-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="95a21-109">Esta etapa é fundamental antes de migrar qualquer usuário para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="95a21-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="95a21-110">**Etapas:**</span><span class="sxs-lookup"><span data-stu-id="95a21-110">**Steps:**</span></span>

1.  <span data-ttu-id="95a21-111">Obtenha um novo certificado de Borda Externa para a borda que tenha todas as entradas existentes mais entradas adicionais na SAN para todos os domínios SIP no ambiente de nuvem (excluindo \*.onmicrosoft.com domínios) no formato "sip. <DomainName> ".</span><span class="sxs-lookup"><span data-stu-id="95a21-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="95a21-112">Instale o certificado localmente em cada servidor de borda e atribua-o ao serviço de Borda do Skype em cada um dos serviços de borda.</span><span class="sxs-lookup"><span data-stu-id="95a21-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="95a21-113">Para etapas detalhadas, consulte a seção "Certificados de interface de borda externa" em [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="95a21-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span></span>
3.  <span data-ttu-id="95a21-114">Reinicie o serviço de Borda em cada um dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="95a21-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="95a21-115">Você pode fazer isso por uma única caixa com os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="95a21-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="95a21-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="95a21-116">See also</span></span>

[<span data-ttu-id="95a21-117">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="95a21-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)