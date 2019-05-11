---
title: Alterar uma política no Skype de arquivamento para Business Server existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumo: Saiba como alterar as políticas de arquivamento para Skype para Business Server do usuário.'
ms.openlocfilehash: 7e8cc208802af324690ff61cad971023d3a20232
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884997"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Alterar uma política no Skype de arquivamento para Business Server existente
 
**Resumo:** Saiba como alterar as políticas de arquivamento para Skype para Business Server do usuário.
  
Quando você implanta Skype para Business Server, você configurar políticas de arquivamento iniciais que determinam como o arquivamento é implementado para os usuários em sua implantação. Este tópico descreve como gerenciar e alterar as políticas. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Alterar políticas de arquivamento usando o Painel de Controle

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
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
    > As configurações de uma política do usuário se aplicam somente a usuários específicos e grupos de usuários aos quais você aplica a política. Para obter detalhes, consulte [Aplicar uma política de arquivamento para usuários no Skype para Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Alterar políticas de arquivamento usando o Windows PowerShell

Você também pode alterar políticas de arquivamento usando o cmdlet **Set-CsArchivingPolicy** do Windows PowerShell.
  
### <a name="enable-archiving-policies"></a>Habilitar políticas de arquivamento

Para habilitar o arquivamento de sessões de comunicações internas, defina o valor do parâmetro ArchiveInternal como Verdadeiro ($True): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Para habilitar o arquivamento de sessões de comunicações externas, defina o valor do parâmetro ArchiveExternal como Verdadeiro ($True): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Para habilitar o arquivamento de sessões de comunicações internas e externas, defina o valor dos parâmetros de ArchiveInternal e ArchiveExternal como verdadeiro: 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Desabilitar políticas de arquivamento

Para desabilitar o arquivamento como um todo, defina os parâmetros ArchiveInternal e ArchiveExternal como Falso ($False): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
