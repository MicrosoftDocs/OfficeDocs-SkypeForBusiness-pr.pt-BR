---
title: Criar uma nova política de arquivamento no Skype for Business Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Resumo: saiba como criar uma nova política de arquivamento para Skype for Business Server.'
ms.openlocfilehash: ffa2821ca4871a0e05d0afe2f162512a60df3897
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392633"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Criar uma nova política de arquivamento no Skype for Business Server

**Resumo:** Saiba como criar uma nova política de arquivamento para Skype for Business Server.
  
Você pode criar novas políticas de arquivamento usando o Painel de Controle ou usando Windows PowerShell cmdlets.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Criar uma nova política de arquivamento usando o Painel de Controle

Para criar uma nova política de arquivamento usando o Painel de Controle:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.
    
4. Clique em **Nova** e execute um dos seguintes procedimentos: 
    
   - Para criar uma política de arquivamento no nível do site, clique em **Política de site** e, em **Selecionar um site**, clique no site ao qual a política deve ser aplicada.
    
   - Para criar uma política de arquivamento em nível do usuário, clique em **Política de usuário**.
    
5. Em **Nova Política de Arquivamento**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova política (por exemplo, externalContoso).
    
   - Em **Descrição**, forneça os detalhes sobre a política (por exemplo, a política de arquivamento de usuário externo da Contoso).
    
   - Para controlar o arquivamento das comunicações com usuários internos, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para controlar o arquivamento das comunicações com usuários externos, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
    > [!IMPORTANT]
    > As configurações de uma política de usuário somente se aplicam aos usuários e grupos de usuários específicos aos quais você aplicar a política. Para obter detalhes, [consulte Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Criar uma nova política de arquivamento usando Windows PowerShell

Você também pode criar novas políticas de arquivamento usando o cmdlet **Windows PowerShell New-CsArchivingPolicy**. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Para criar uma nova política de arquivamento no nível do site

Este comando cria uma nova política de arquivamento para o site de Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Para criar uma nova política de arquivamento no nível por usuário

Para criar uma nova política de arquivamento no nível por usuário, basta especificar uma Identidade exclusiva ao criar a política:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Para criar uma nova política de arquivamento que habilita o arquivamento de sessões de comunicação internas

Como nenhum parâmetros foi especificado (além do parâmetro obrigatório Identity) nos comandos anteriores, as novas políticas utilizarão os valores padrão para todas as suas propriedades. Para criar políticas que utilizam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro apropriado. Por exemplo, o comando a seguir cria uma política de arquivamento que permite o arquivamento de sessões internas de mensagens instantâneas: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Para criar uma nova política de arquivamento que habilita o arquivamento de sessões de comunicação internas e externas

Vários valores de propriedade podem ser modificados, incluindo vários parâmetros. Por exemplo, esse comando configura a nova política para arquivar sessões internas e externas de mensagens instantâneas:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```