---
title: Alterar uma política de arquivamento existente no Skype for Business Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumo: saiba como alterar as políticas de arquivamento do usuário para Skype for Business Server.'
ms.openlocfilehash: 494ed5ab3bd9e7bf4b64926533d3866e515fe34a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416614"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Alterar uma política de arquivamento existente no Skype for Business Server
 
**Resumo:** Saiba como alterar as políticas de arquivamento do usuário para Skype for Business Server.
  
Ao implantar o Skype for Business Server, você configura políticas iniciais de arquivamento que determinam como o arquivamento é implementado para os usuários em sua implantação. Este tópico descreve como gerenciar e corrigir políticas. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Alterar políticas de arquivamento usando o Painel de Controle

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.
    
4. Na lista de políticas, siga um destes procedimentos: 
    
   - Para alterar a política da implantação inteira, clique em **Global** na lista de políticas, clique em **Editar**, em **Mostrar detalhes**.
    
   - Para alterar a política de um único site, clique no nome do site na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.
    
   - Para alterar a política de um único usuário ou grupo de usuários, clique no nome do usuário ou do grupo de usuários na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.
    
5. Na página **Editar política de arquivamento**, faça o seguinte:
    
   - Para habilitar ou desabilitar o arquivamento interno da política, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para habilitar ou desabilitar o arquivamento externo da política, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
    > [!IMPORTANT]
    > As configurações de uma política de usuário somente se aplicam aos usuários e grupos de usuários específicos aos quais você aplicar a política. Para obter detalhes, [consulte Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Alterar políticas de arquivamento usando Windows PowerShell

Você também pode alterar as políticas de arquivamento usando o cmdlet **Set-CsArchivingPolicy Windows PowerShell Set-CsArchivingPolicy**.
  
### <a name="enable-archiving-policies"></a>Habilitar políticas de arquivamento

Para habilitar o arquivamento de sessões de comunicação interna, de definir o valor do parâmetro ArchiveInternal como True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Para habilitar o arquivamento de sessões de comunicação externa, de definir o valor do parâmetro ArchiveExternal como True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Para habilitar o arquivamento de sessões de comunicação internas e externas, de definir o valor dos parâmetros ArchiveInternal e ArchiveExternal como True: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Desabilitar políticas de arquivamento

Para desabilitar completamente o arquivamento, de definir o valor dos parâmetros ArchiveInternal e ArchiveExternal como False ($False): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
