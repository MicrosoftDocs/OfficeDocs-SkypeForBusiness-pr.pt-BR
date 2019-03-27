---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: O cmdlet Enter-CcUpdate prepara o Skype para servidor de host de conector de nuvem Business Edition para o processo de atualização, colocando-o no modo de manutenção. O aparelho isdrained — ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas.
ms.openlocfilehash: 45972058cd9263330b6a4c0a68a5a1b800a85d9d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882576"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="60b92-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="60b92-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="60b92-105">O cmdlet Enter-CcUpdate prepara o Skype para servidor de host de conector de nuvem Business Edition para o processo de atualização, colocando-o no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="60b92-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="60b92-106">O aparelho é "drenagem" — ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="60b92-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="60b92-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="60b92-107">Parameters</span></span>

<span data-ttu-id="60b92-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="60b92-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="60b92-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="60b92-109">Examples</span></span>
<span data-ttu-id="60b92-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="60b92-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="60b92-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="60b92-111">Example 1</span></span>

<span data-ttu-id="60b92-112">O exemplo seguinte prepara o dispositivo para o processo de atualização entrando no modo de manutenção:</span><span class="sxs-lookup"><span data-stu-id="60b92-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="60b92-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="60b92-113">Detailed Description</span></span>
<span data-ttu-id="60b92-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="60b92-114"></span></span>

<span data-ttu-id="60b92-115">O cmdlet Enter-CcUpdate imediatamente irá parar todos os serviços que terminem todas as chamadas em andamento e o aparelho rejeitará quaisquer novas chamadas são transferidas para outros aparelhos de produção.</span><span class="sxs-lookup"><span data-stu-id="60b92-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="60b92-116">Certifique-se de que os dispositivos de produção restantes tem capacidade suficiente para lidar com as chamadas do aparelho de que você está preparando para atualizar.</span><span class="sxs-lookup"><span data-stu-id="60b92-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="60b92-p104">O modo de manutenção será útil se o seu dispositivo tiver a atualização automática habilitada, por exemplo, e a Microsoft lançar um hotfix crítico. O modo de manutenção também será útil se você decidir desativar as atualizações automáticas, mas executar atualizações manuais de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="60b92-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="60b92-119">Depois de instalar as atualizações, o aparelho pode ser colocado novamente para o modo de produção, executando o cmdlet sair-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="60b92-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60b92-120">Se você decidir atualizar manualmente um aparelho de conector de nuvem, você precisa atualizá-la até 60 dias após a Microsoft lança a próxima versão.</span><span class="sxs-lookup"><span data-stu-id="60b92-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="60b92-121">A Microsoft oferece suporte para a versão lançada anteriormente do conector de nuvem por 60 dias após a nova versão é lançada</span><span class="sxs-lookup"><span data-stu-id="60b92-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="60b92-122">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="60b92-122">Input Types</span></span>
<span data-ttu-id="60b92-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="60b92-123"></span></span>

<span data-ttu-id="60b92-p106">Nenhum. O cmdlet Enter-CCUpdate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="60b92-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="60b92-126">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="60b92-126">Return Types</span></span>
<span data-ttu-id="60b92-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="60b92-127"></span></span>

<span data-ttu-id="60b92-128">Nenhum </span><span class="sxs-lookup"><span data-stu-id="60b92-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="60b92-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60b92-129">See also</span></span>
<span data-ttu-id="60b92-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="60b92-130"></span></span>

[<span data-ttu-id="60b92-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="60b92-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

