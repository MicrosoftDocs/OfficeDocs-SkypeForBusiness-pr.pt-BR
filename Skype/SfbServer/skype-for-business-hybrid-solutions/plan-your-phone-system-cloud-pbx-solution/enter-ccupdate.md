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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: O Enter-CcUpdate cmdlet prepara o servidor host Skype for Business Cloud Connector Edition para o processo de atualização colocando-o no modo de manutenção. O dispositivo interrompe imediatamente todos os serviços, encerrando todas as chamadas em andamento e rejeitando quaisquer novas chamadas.
ms.openlocfilehash: 26f1874ca6c0b92836716d66031945adc864d0ff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620757"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

O Enter-CcUpdate cmdlet prepara o servidor host Skype for Business Cloud Connector Edition para o processo de atualização colocando-o no modo de manutenção. O dispositivo interrompe imediatamente todos os serviços, encerrando todas as chamadas em andamento e rejeitando quaisquer novas chamadas.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir prepara o dispositivo para o processo de atualização inserindo o modo de manutenção:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Enter-CcUpdate cmdlet interromperá imediatamente todos os serviços que encerram chamadas em andamento e o dispositivo rejeitará quaisquer novas chamadas, que são transferidas para outros dispositivos de produção. Você deve garantir que os dispositivos de produção restantes tenham capacidade suficiente para lidar com as chamadas do dispositivo que você está preparando para atualizar.
  
O modo de manutenção será útil se seu dispositivo tiver a atualização automática habilitada, por exemplo, e a Microsoft lançar um hotfix crítico. O modo de manutenção também será útil se você decidir desativar as atualizações automáticas, mas executar atualizações manuais de forma consistente.
  
Depois de instalar as atualizações, o dispositivo pode ser trazido de volta ao modo de produção executando o cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Se você decidir atualizar manualmente um dispositivo do Cloud Connector, precisará atualizá-lo dentro de 60 dias após a Microsoft lançar a próxima versão. A Microsoft dá suporte à versão lançada anteriormente do Cloud Connector por 60 dias após o lançamento da nova versão 
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Enter-CCUpdate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

