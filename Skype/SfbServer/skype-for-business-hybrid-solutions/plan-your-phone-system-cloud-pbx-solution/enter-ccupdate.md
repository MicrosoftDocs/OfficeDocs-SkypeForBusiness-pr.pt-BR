---
title: Insira-CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: O cmdlet Enter-CcUpdate prepara o servidor host do Skype for Business Cloud Connector Edition para o processo de atualização colocando-o no modo de manutenção. O aparelho isdrained — ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas.
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a><span data-ttu-id="53e11-104">Insira-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="53e11-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="53e11-105">O cmdlet Enter-CcUpdate prepara o servidor host do Skype for Business Cloud Connector Edition para o processo de atualização colocando-o no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="53e11-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="53e11-106">O aparelho é "drenagem" — ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="53e11-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="53e11-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="53e11-107">Parameters</span></span>

<span data-ttu-id="53e11-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="53e11-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="53e11-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="53e11-109">Examples</span></span>
<span data-ttu-id="53e11-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="53e11-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="53e11-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="53e11-111">Example 1</span></span>

<span data-ttu-id="53e11-112">O exemplo seguinte prepara o dispositivo para o processo de atualização entrando no modo de manutenção:</span><span class="sxs-lookup"><span data-stu-id="53e11-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="53e11-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="53e11-113">Detailed Description</span></span>
<span data-ttu-id="53e11-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="53e11-114"></span></span>

<span data-ttu-id="53e11-115">O cmdlet Enter-CcUpdate garantirá que todas as chamadas em execução em um aparelho de conector de nuvem concluirá, mas o aparelho rejeitará quaisquer novas chamadas são transferidas para outros aparelhos de produção.</span><span class="sxs-lookup"><span data-stu-id="53e11-115">The Enter-CcUpdate cmdlet will ensure that all running calls on a Cloud Connector appliance will complete, but the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="53e11-116">Esse cmdlet permite que você atualize um dispositivo sem afetar as chamadas dos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="53e11-116">This cmdlet enables you to update an appliance without affecting end users calls.</span></span> <span data-ttu-id="53e11-117">Você deve garantir que os dispositivos de produção remanescentes tenham capacidade suficiente para lidar com as chamadas do dispositivo que você está preparando para atualizar.</span><span class="sxs-lookup"><span data-stu-id="53e11-117">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="53e11-p104">O modo de manutenção será útil se o seu dispositivo tiver a atualização automática habilitada, por exemplo, e a Microsoft lançar um hotfix crítico. O modo de manutenção também será útil se você decidir desativar as atualizações automáticas, mas executar atualizações manuais de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="53e11-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="53e11-120">Depois de instalar as atualizações, o dispositivo pode ser colocado no modo de produção novamente com a execução do cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="53e11-120">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53e11-121">Se você decidir atualizar manualmente um aparelho de conector de nuvem, você precisa atualizá-la até 60 dias após a Microsoft lança a próxima versão.</span><span class="sxs-lookup"><span data-stu-id="53e11-121">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="53e11-122">A Microsoft oferece suporte para a versão lançada anteriormente do conector de nuvem por 60 dias após a nova versão é lançada</span><span class="sxs-lookup"><span data-stu-id="53e11-122">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="53e11-123">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="53e11-123">Input Types</span></span>
<span data-ttu-id="53e11-124"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53e11-124"></span></span>

<span data-ttu-id="53e11-p106">Nenhum. O cmdlet Enter-CCUpdate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="53e11-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="53e11-127">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="53e11-127">Return Types</span></span>
<span data-ttu-id="53e11-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53e11-128"></span></span>

<span data-ttu-id="53e11-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="53e11-129">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="53e11-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53e11-130">See also</span></span>
<span data-ttu-id="53e11-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53e11-131"></span></span>

[<span data-ttu-id="53e11-132">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="53e11-132">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

