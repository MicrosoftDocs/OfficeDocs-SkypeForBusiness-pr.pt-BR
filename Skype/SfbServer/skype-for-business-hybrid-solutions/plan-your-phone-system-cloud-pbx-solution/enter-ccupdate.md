---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: O cmdlet Enter-CcUpdate prepara o Skype para servidor de host de conector de nuvem Business Edition para o processo de atualização, colocando-o no modo de manutenção. O aparelho isdrained — ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas.
ms.openlocfilehash: 42c8f7fa668fa94040276e7749e93b5832d511cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929428"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate
 
O cmdlet Enter-CcUpdate prepara o Skype para servidor de host de conector de nuvem Business Edition para o processo de atualização, colocando-o no modo de manutenção. O aparelho é "drenagem" — ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas. 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte prepara o dispositivo para o processo de atualização entrando no modo de manutenção:
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Enter-CcUpdate imediatamente irá parar todos os serviços que terminem todas as chamadas em andamento e o aparelho rejeitará quaisquer novas chamadas são transferidas para outros aparelhos de produção. Certifique-se de que os dispositivos de produção restantes tem capacidade suficiente para lidar com as chamadas do aparelho de que você está preparando para atualizar.
  
O modo de manutenção será útil se o seu dispositivo tiver a atualização automática habilitada, por exemplo, e a Microsoft lançar um hotfix crítico. O modo de manutenção também será útil se você decidir desativar as atualizações automáticas, mas executar atualizações manuais de forma consistente.
  
Depois de instalar as atualizações, o aparelho pode ser colocado novamente para o modo de produção, executando o cmdlet sair-CcUpdate.
  
> [!NOTE]
> Se você decidir atualizar manualmente um aparelho de conector de nuvem, você precisa atualizá-la até 60 dias após a Microsoft lança a próxima versão. A Microsoft oferece suporte para a versão lançada anteriormente do conector de nuvem por 60 dias após a nova versão é lançada 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Enter-CCUpdate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum  
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

