---
title: 'Suporte de virtualização para o Skype for Business Server 2019 '
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
description: 'Resumo: Saiba mais sobre o suporte de virtualização para o Skype for Business Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509028"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="692d9-103">Suporte de virtualização para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="692d9-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="692d9-104">O Skype for Business Server 2019 é suportado na virtualização.</span><span class="sxs-lookup"><span data-stu-id="692d9-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="692d9-105">Embora haja suporte à virtualização, há alguns pontos importantes a serem lembrados:</span><span class="sxs-lookup"><span data-stu-id="692d9-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="692d9-106">Mantenha uma taxa de 1:1 de CPU virtual para a CPU física.</span><span class="sxs-lookup"><span data-stu-id="692d9-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="692d9-107">Não mova um servidor convidado enquanto ele está funcionando.</span><span class="sxs-lookup"><span data-stu-id="692d9-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="692d9-108">Não há suporte para a migração de um sistema ativo e portabilidade de uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="692d9-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="692d9-109">Desabilite o Hyper-Threading em todos os hosts.</span><span class="sxs-lookup"><span data-stu-id="692d9-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="692d9-110">Não configure a memória dinâmica nos servidores host.</span><span class="sxs-lookup"><span data-stu-id="692d9-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="692d9-111">Usar discos fixos ou de passagem em vez de discos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="692d9-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="692d9-112">Permitir a sobrecarga de 6-10% para os hipervisores além do que o convidado virtual exige.</span><span class="sxs-lookup"><span data-stu-id="692d9-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="692d9-113">Hipervisores suportados</span><span class="sxs-lookup"><span data-stu-id="692d9-113">Supported hypervisors</span></span>

<span data-ttu-id="692d9-114">O SfB Server 2019 é suportado no Windows Server 2016 e no Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="692d9-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="692d9-115">Para hipervisores de terceiros, você precisa de um hipervisor que passou no teste SVVP (Server Virtualization Validation Program) para o sistema operacional relevante.</span><span class="sxs-lookup"><span data-stu-id="692d9-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="692d9-116">Consulte as [versões do Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="692d9-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="692d9-117">Consulte as [versões do Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="692d9-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="692d9-118">Ferramenta de estresse e desempenho</span><span class="sxs-lookup"><span data-stu-id="692d9-118">Stress and performance tool</span></span>

<span data-ttu-id="692d9-119">A ferramenta de estresse e desempenho do Skype for Business Server 2019 inclui ferramentas que simplificam o planejamento de capacidade para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="692d9-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="692d9-120">A ferramenta de desempenho e stress do Skype for Business Server 2019 ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="692d9-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="692d9-121">Simplificar o planejamento de hardware para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="692d9-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="692d9-122">Fornecer mais conhecimento e práticas recomendadas para ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="692d9-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="692d9-123">Meça o desempenho de suas implantações pretendidas do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="692d9-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="692d9-124">Você pode baixar a ferramenta [aqui](https://www.microsoft.com/download/details.aspx?id=101447).</span><span class="sxs-lookup"><span data-stu-id="692d9-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
