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
description: O cmdlet Enter-CcUpdate prepara o servidor de host do Skype for Business Cloud Connector Edition para o processo de atualização, colocando-o no modo de manutenção. O aparelho não esgotado, ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas serão recusadas.
ms.openlocfilehash: be57261b35cf5b5e6e8118c2a751eee1c8b5f2a7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287437"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate
 
O cmdlet Enter-CcUpdate prepara o servidor de host do Skype for Business Cloud Connector Edition para o processo de atualização, colocando-o no modo de manutenção. O aparelho está "esgotado", ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas serão recusadas. 
  
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

O cmdlet Enter-CcUpdate interromperá imediatamente todos os serviços que encerrarem as chamadas em andamento e o dispositivo rejeitará todas as novas chamadas, que serão transferidas para outros aplicativos de produção. Você deve garantir que os dispositivos de produção restantes tenham capacidade suficiente para lidar com as chamadas do aparelho que você está preparando para atualizar.
  
O modo de manutenção será útil se o seu dispositivo tiver a atualização automática habilitada, por exemplo, e a Microsoft lançar um hotfix crítico. O modo de manutenção também será útil se você decidir desativar as atualizações automáticas, mas executar atualizações manuais de forma consistente.
  
Depois de instalar as atualizações, o aparelho pode ser retornado ao modo de produção executando o cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Se você decidir atualizar manualmente um aparelho de conexão de nuvem, será necessário atualizá-lo dentro de 60 dias após a Microsoft liberar a próxima versão. A Microsoft oferece suporte à versão lançada anteriormente do Cloud Connector para 60 dias após a liberação da nova versão 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Enter-CCUpdate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum  
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

