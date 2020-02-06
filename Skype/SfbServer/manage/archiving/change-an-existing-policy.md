---
title: Alterar uma política de arquivamento existente no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumo: saiba como alterar as políticas de arquivamento do usuário do Skype for Business Server.'
ms.openlocfilehash: 010365b5805517db8f40aa7e3e839fdb15115c06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818983"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Alterar uma política de arquivamento existente no Skype for Business Server
 
**Resumo:** Saiba como alterar as políticas de arquivamento do usuário do Skype for Business Server.
  
Ao implantar o Skype for Business pela primeira vez, configure as políticas de arquivamento iniciais que determinam como o arquivamento é implementado para os usuários na sua implantação. Este tópico descreve como gerenciar e alterar as políticas. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Alterar políticas de arquivamento usando o Painel de Controle

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.
    
4. Na lista de políticas, faça um destes procedimentos: 
    
   - Para alterar a política da implantação inteira, clique em **Global** na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.
    
   - Para alterar a política de um único site, clique no nome do site na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.
    
   - Para alterar a política de um único usuário ou grupo de usuários, clique no nome do usuário ou do grupo de usuários na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.
    
5. Na página **Editar política de arquivamento**, faça o seguinte:
    
   - Para habilitar ou desabilitar o arquivamento interno da política, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para habilitar ou desabilitar o arquivamento externo da política, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
    > [!IMPORTANT]
    > As configurações de uma política do usuário se aplicam somente a usuários específicos e grupos de usuários aos quais você aplica a política. Para obter detalhes, consulte [aplicar uma política de arquivamento a usuários no Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Alterar políticas de arquivamento usando o Windows PowerShell

Você também pode alterar políticas de arquivamento usando o cmdlet **Set-CsArchivingPolicy** do Windows PowerShell.
  
### <a name="enable-archiving-policies"></a>Habilitar políticas de arquivamento

Para habilitar o arquivamento de sessões de comunicações internas, defina o valor do parâmetro ArchiveInternal como Verdadeiro ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Para habilitar o arquivamento de sessões de comunicações externas, defina o valor do parâmetro ArchiveExternal como Verdadeiro ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Para habilitar o arquivamento de sessões de comunicação internas e externas, defina o valor dos parâmetros ArchiveInternal e ArchiveExternal como true: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Desabilitar políticas de arquivamento

Para desabilitar o arquivamento como um todo, defina os parâmetros ArchiveInternal e ArchiveExternal como Falso ($False): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
