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
description: Este apêndice inclui etapas detalhadas para a atualização do certificado de borda como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: c4339eec5fa303429fdf8f42a7273c8f20f94e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762849"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="6acb4-103">Atualizar o certificado de borda</span><span class="sxs-lookup"><span data-stu-id="6acb4-103">Update the edge certificate</span></span>

<span data-ttu-id="6acb4-104">A atualização do certificado de borda é a etapa principal para garantir que um ambiente local com o SipDomain1 possa ingressar em um ambiente de nuvem com o SipDomain2 e garantir o roteamento adequado em um ambiente de espaço de endereçamento compartilhado nos dois domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="6acb4-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="6acb4-105">Confira a etapa 14 em [consolidação de nuvem para o Microsoft Teams e o Skype for Business](cloud-consolidation.md) para o contexto no qual você pode executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="6acb4-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="6acb4-106">Nos nossos exemplos, SipDomain1 é AcquiredCompany. <span>com e SipDomain2 é OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="6acb4-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="6acb4-107">O nome alternativo de entidade (SAN) do certificado em todos os servidores de borda no ambiente local deve ser atualizado para incluir todos os domínios SIP existentes no locatário online puro (excluindo qualquer onmicrosoft.<span> Domínios com), no formato "SIP. \<> de domínio ".</span><span class="sxs-lookup"><span data-stu-id="6acb4-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="6acb4-108">No nosso exemplo, é SIP. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="6acb4-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="6acb4-109">Esta etapa é crítica para fazer antes de migrar qualquer usuário para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="6acb4-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="6acb4-110">**Necessárias**</span><span class="sxs-lookup"><span data-stu-id="6acb4-110">**Steps:**</span></span>

1.  <span data-ttu-id="6acb4-111">Obtenha um novo certificado de borda externo para a borda que tenha todas as entradas existentes, além de entradas adicionais na SAN para todos os domínios SIP no ambiente de nuvem (excluindo os domínios \*. onmicrosoft.com) no formato "SIP. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="6acb4-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="6acb4-112">Instale o certificado localmente em cada servidor de borda e atribua-o ao serviço de borda do Skype em cada um dos serviços de borda.</span><span class="sxs-lookup"><span data-stu-id="6acb4-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="6acb4-113">Para obter etapas detalhadas, consulte a seção "certificados de interface de borda externa" em [implantar serviço de borda no Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="6acb4-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="6acb4-114">Reinicie o serviço de borda em cada um dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="6acb4-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="6acb4-115">Você pode fazer isso para uma única caixa com os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6acb4-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="6acb4-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="6acb4-116">See also</span></span>

[<span data-ttu-id="6acb4-117">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6acb4-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
