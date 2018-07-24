---
title: Excluir uma política no Skype de arquivamento para Business Server existente
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumo: Saiba como excluir uma política de arquivamento para Skype para Business Server.'
ms.openlocfilehash: 0446999923b462311f941b6653157b41000b1f43
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973098"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Excluir uma política no Skype de arquivamento para Business Server existente

**Resumo:** Saiba como excluir uma política de arquivamento para Skype para Business Server.
  
Você pode excluir uma política de usuário ou uma política de site, mas não a política global. Se você excluir a política global, Skype para Business Server automaticamente redefine a política para os valores padrão.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Excluir uma política usando o Painel de Controle

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.
    
4. Na lista de políticas de arquivamento, clique na política de usuário ou site que deseja excluir, clique em **Editar** e em **Excluir**.
    
5. Clique em **Confirmar**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Excluir uma política usando o Windows PowerShell

Você também pode excluir políticas de arquivamento usando o cmdlet **Remove-CsArchivingPolicy**.
  
Por exemplo, o seguinte comando exclui a política com Identidade site:Redmond. Quando uma política configurada no nível do site é excluída, os usuários previamente gerenciados pela política de site passam a ser governados automaticamente pela política global de arquivamento:
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

Este comando remove todas as políticas de arquivamento aplicadas ao nível por usuário:
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Este comando remove todas as políticas de arquivamento onde o arquivamento interno foi desativado:
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .