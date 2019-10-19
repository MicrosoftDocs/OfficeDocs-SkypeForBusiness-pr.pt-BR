---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: O cmdlet Enter-CcUpdate prepara o servidor de host do Skype for Business Cloud Connector Edition para o processo de atualização, colocando-o no modo de manutenção. O aparelho interrompe imediatamente todos os serviços, encerrando todas as chamadas em andamento e recusando novas chamadas.
ms.openlocfilehash: 3ff4c1543e3e882a7ccbaf0b9a216ce902a77c5f
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "34740055"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="dc05a-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="dc05a-104">Enter-CcUpdate</span></span>

<span data-ttu-id="dc05a-105">O cmdlet Enter-CcUpdate prepara o servidor de host do Skype for Business Cloud Connector Edition para o processo de atualização, colocando-o no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="dc05a-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="dc05a-106">O aparelho interrompe imediatamente todos os serviços, encerrando todas as chamadas em andamento e recusando novas chamadas.</span><span class="sxs-lookup"><span data-stu-id="dc05a-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="dc05a-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dc05a-107">Parameters</span></span>

<span data-ttu-id="dc05a-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc05a-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="dc05a-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="dc05a-109">Examples</span></span>
<span data-ttu-id="dc05a-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="dc05a-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="dc05a-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="dc05a-111">Example 1</span></span>

<span data-ttu-id="dc05a-112">O exemplo seguinte prepara o dispositivo para o processo de atualização entrando no modo de manutenção:</span><span class="sxs-lookup"><span data-stu-id="dc05a-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="dc05a-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="dc05a-113">Detailed Description</span></span>
<span data-ttu-id="dc05a-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dc05a-114"></span></span>

<span data-ttu-id="dc05a-115">O cmdlet Enter-CcUpdate interromperá imediatamente todos os serviços que encerrarem as chamadas em andamento e o dispositivo rejeitará todas as novas chamadas, que serão transferidas para outros aplicativos de produção.</span><span class="sxs-lookup"><span data-stu-id="dc05a-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="dc05a-116">Você deve garantir que os dispositivos de produção restantes tenham capacidade suficiente para lidar com as chamadas do aparelho que você está preparando para atualizar.</span><span class="sxs-lookup"><span data-stu-id="dc05a-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="dc05a-p104">O modo de manutenção será útil se o seu dispositivo tiver a atualização automática habilitada, por exemplo, e a Microsoft lançar um hotfix crítico. O modo de manutenção também será útil se você decidir desativar as atualizações automáticas, mas executar atualizações manuais de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="dc05a-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="dc05a-119">Depois de instalar as atualizações, o aparelho pode ser retornado ao modo de produção executando o cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="dc05a-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc05a-120">Se você decidir atualizar manualmente um aparelho de conexão de nuvem, será necessário atualizá-lo dentro de 60 dias após a Microsoft liberar a próxima versão.</span><span class="sxs-lookup"><span data-stu-id="dc05a-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="dc05a-121">A Microsoft oferece suporte à versão lançada anteriormente do Cloud Connector para 60 dias após a liberação da nova versão</span><span class="sxs-lookup"><span data-stu-id="dc05a-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="dc05a-122">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="dc05a-122">Input Types</span></span>
<span data-ttu-id="dc05a-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc05a-123"></span></span>

<span data-ttu-id="dc05a-p106">Nenhum. O cmdlet Enter-CCUpdate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="dc05a-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="dc05a-126">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="dc05a-126">Return Types</span></span>
<span data-ttu-id="dc05a-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc05a-127"></span></span>

<span data-ttu-id="dc05a-128">Nenhum </span><span class="sxs-lookup"><span data-stu-id="dc05a-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dc05a-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc05a-129">See also</span></span>
<span data-ttu-id="dc05a-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc05a-130"></span></span>

[<span data-ttu-id="dc05a-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="dc05a-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

