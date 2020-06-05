---
title: 'Suporte de virtualização para o Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Saiba mais sobre o suporte de virtualização para o Skype for Business Server 2019.'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565950"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="db8bb-103">Suporte de virtualização para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="db8bb-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="db8bb-104">O Skype for Business Server 2019 é suportado na virtualização.</span><span class="sxs-lookup"><span data-stu-id="db8bb-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="db8bb-105">Embora haja suporte à virtualização, há alguns pontos importantes a serem lembrados:</span><span class="sxs-lookup"><span data-stu-id="db8bb-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="db8bb-106">Mantenha uma taxa de 1:1 de CPU virtual para a CPU física.</span><span class="sxs-lookup"><span data-stu-id="db8bb-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="db8bb-107">Não mova um servidor convidado enquanto ele está funcionando.</span><span class="sxs-lookup"><span data-stu-id="db8bb-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="db8bb-108">Não há suporte para a migração de um sistema ativo e portabilidade de uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="db8bb-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="db8bb-109">Desabilite o Hyper-Threading em todos os hosts.</span><span class="sxs-lookup"><span data-stu-id="db8bb-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="db8bb-110">Não configure a memória dinâmica nos servidores host.</span><span class="sxs-lookup"><span data-stu-id="db8bb-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="db8bb-111">Usar discos fixos ou de passagem em vez de discos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="db8bb-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="db8bb-112">Permitir a sobrecarga de 6-10% para os hipervisores além do que o convidado virtual exige.</span><span class="sxs-lookup"><span data-stu-id="db8bb-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="db8bb-113">Hipervisores suportados</span><span class="sxs-lookup"><span data-stu-id="db8bb-113">Supported hypervisors</span></span>

<span data-ttu-id="db8bb-114">O SfB Server 2019 é suportado no Windows Server 2016 e no Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="db8bb-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="db8bb-115">Para hipervisores de terceiros, você precisa de um hipervisor que passou no teste SVVP (Server Virtualization Validation Program) para o sistema operacional relevante.</span><span class="sxs-lookup"><span data-stu-id="db8bb-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="db8bb-116">Consulte as [versões do Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="db8bb-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="db8bb-117">Consulte as [versões do Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.</span><span class="sxs-lookup"><span data-stu-id="db8bb-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
