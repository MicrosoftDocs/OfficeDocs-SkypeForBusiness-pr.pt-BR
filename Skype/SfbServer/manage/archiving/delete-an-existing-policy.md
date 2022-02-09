---
title: Excluir uma política de arquivamento existente no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumo: saiba como excluir uma política de arquivamento para Skype for Business Server.'
ms.openlocfilehash: 834c7a0402fee9a796b4f00ce70339cbf6e9ffae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402045"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Excluir uma política de arquivamento existente no Skype for Business Server

**Resumo:** Saiba como excluir uma política de arquivamento para Skype for Business Server.
  
Você pode excluir uma política de usuário ou uma política de site, mas não a política global. Se você excluir a política global, Skype for Business Server redefinir automaticamente a política para os valores padrão.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Excluir uma política usando o Painel de Controle

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.
    
4. Na lista de políticas de arquivamento, clique na política de usuário ou site que deseja excluir, clique em **Editar** e em **Excluir**.
    
5. Clique em **Confirmar**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Excluir uma política usando Windows PowerShell

Você também pode excluir políticas de arquivamento usando o cmdlet **Remove-CsArchivingPolicy** .
  
Por exemplo, o comando a seguir exclui a política com Identity site:Redmond. Quando uma política configurada no nível do site é excluída, os usuários gerenciados anteriormente pela política de site serão automaticamente governados pela política de arquivamento global:
  
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

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .