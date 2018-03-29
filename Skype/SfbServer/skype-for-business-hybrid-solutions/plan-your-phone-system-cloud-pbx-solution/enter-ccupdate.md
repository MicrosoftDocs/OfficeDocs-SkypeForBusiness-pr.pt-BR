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
# <a name="enter-ccupdate"></a>Insira-CcUpdate
 
O cmdlet Enter-CcUpdate prepara o servidor host do Skype for Business Cloud Connector Edition para o processo de atualização colocando-o no modo de manutenção. O aparelho é "drenagem" — ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas. 
  
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

O cmdlet Enter-CcUpdate garantirá que todas as chamadas em execução em um aparelho de conector de nuvem concluirá, mas o aparelho rejeitará quaisquer novas chamadas são transferidas para outros aparelhos de produção. Esse cmdlet permite que você atualize um dispositivo sem afetar as chamadas dos usuários finais. Você deve garantir que os dispositivos de produção remanescentes tenham capacidade suficiente para lidar com as chamadas do dispositivo que você está preparando para atualizar.
  
O modo de manutenção será útil se o seu dispositivo tiver a atualização automática habilitada, por exemplo, e a Microsoft lançar um hotfix crítico. O modo de manutenção também será útil se você decidir desativar as atualizações automáticas, mas executar atualizações manuais de forma consistente.
  
Depois de instalar as atualizações, o dispositivo pode ser colocado no modo de produção novamente com a execução do cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Se você decidir atualizar manualmente um aparelho de conector de nuvem, você precisa atualizá-la até 60 dias após a Microsoft lança a próxima versão. A Microsoft oferece suporte para a versão lançada anteriormente do conector de nuvem por 60 dias após a nova versão é lançada 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Enter-CCUpdate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

