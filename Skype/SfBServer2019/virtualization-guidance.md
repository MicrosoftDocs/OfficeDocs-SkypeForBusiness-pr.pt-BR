---
title: 'Suporte à virtualização do Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: saiba mais sobre o suporte à virtualização do Skype for Business Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509028"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="004c9-103">Suporte à virtualização do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="004c9-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="004c9-104">O Skype for Business Server 2019 tem suporte na virtualização.</span><span class="sxs-lookup"><span data-stu-id="004c9-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="004c9-105">Embora a virtualização seja suportada, há alguns pontos importantes a lembrar:</span><span class="sxs-lookup"><span data-stu-id="004c9-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="004c9-106">Mantenha uma proporção de 1:1 de CPU virtual para CPU física.</span><span class="sxs-lookup"><span data-stu-id="004c9-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="004c9-107">Não mova um servidor convidado enquanto ele estiver em operação.</span><span class="sxs-lookup"><span data-stu-id="004c9-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="004c9-108">A migração de um sistema ao vivo e a portabilidade de uma máquina virtual não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="004c9-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="004c9-109">Desabilite o hyper-threading em todos os hosts.</span><span class="sxs-lookup"><span data-stu-id="004c9-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="004c9-110">Não configure a memória dinâmica em servidores host.</span><span class="sxs-lookup"><span data-stu-id="004c9-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="004c9-111">Use discos fixos ou de passagem em vez de discos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="004c9-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="004c9-112">Permitir sobrecarga de 6 a 10% para hipervisores além do que o convidado virtual exige.</span><span class="sxs-lookup"><span data-stu-id="004c9-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="004c9-113">Hipervisores com suporte</span><span class="sxs-lookup"><span data-stu-id="004c9-113">Supported hypervisors</span></span>

<span data-ttu-id="004c9-114">O SfB Server 2019 tem suporte no Windows Server 2016 e no Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="004c9-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="004c9-115">Para hipervisores de terceiros, você precisa de um hipervisor que passou no teste do Programa de Validação de Virtualização do Servidor (SVVP) para o sistema operacional relevante.</span><span class="sxs-lookup"><span data-stu-id="004c9-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="004c9-116">Consulte as [versões do Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="004c9-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="004c9-117">Consulte as [versões do Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="004c9-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="004c9-118">Ferramenta de stress and performance</span><span class="sxs-lookup"><span data-stu-id="004c9-118">Stress and performance tool</span></span>

<span data-ttu-id="004c9-119">A Ferramenta de Stress and Performance do Skype for Business Server 2019 inclui ferramentas que simplificam o planejamento de capacidade do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="004c9-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="004c9-120">A Ferramenta de Stress and Performance do Skype for Business Server 2019 ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="004c9-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="004c9-121">Simplificar seu planejamento de hardware para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="004c9-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="004c9-122">Fornecer maior conhecimento e práticas recomendadas para ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="004c9-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="004c9-123">Medir o desempenho das implantações pretenddas do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="004c9-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="004c9-124">Você pode baixar a ferramenta [daqui.](https://www.microsoft.com/download/details.aspx?id=101447)</span><span class="sxs-lookup"><span data-stu-id="004c9-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
