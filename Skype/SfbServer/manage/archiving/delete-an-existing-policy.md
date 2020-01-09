---
title: Excluir uma política de arquivamento existente no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumo: saiba como excluir uma política de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: c08b76996b3d54e8be07e731faae87dce0470cc1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992358"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Excluir uma política de arquivamento existente no Skype for Business Server

**Resumo:** Saiba como excluir uma política de arquivamento para o Skype for Business Server.
  
Você pode excluir uma política de usuário ou uma política de site, mas não a política global. Se você excluir a política global, o Skype for Business Server redefinirá automaticamente a política para os valores padrão.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Excluir uma política usando o Painel de Controle

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.
    
4. Na lista de políticas de arquivamento, clique na política de usuário ou site que deseja excluir, clique em **Editar** e em **Excluir**.
    
5. Clique em **Confirmar**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Excluir uma política usando o Windows PowerShell

Você também pode excluir políticas de arquivamento usando o cmdlet **Remove-CsArchivingPolicy**.
  
Por exemplo, o seguinte comando exclui a política com Identidade site:Redmond. Quando uma política configurada no nível do site é excluída, os usuários previamente gerenciados pela política de site passam a ser governados automaticamente pela política global de arquivamento:
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Este comando remove todas as políticas de arquivamento aplicadas ao nível por usuário:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Este comando remove todas as políticas de arquivamento onde o arquivamento interno foi desativado:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
