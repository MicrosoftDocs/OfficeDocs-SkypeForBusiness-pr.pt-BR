---
title: Criar uma nova política de arquivamento no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Resumo: Saiba como criar uma nova política de arquivamento para Skype for Business Server.'
ms.openlocfilehash: 70c955d78e6c7b259732d50c47c53e8b3bedf97c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374406"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Criar uma nova política de arquivamento no Skype para Business Server

**Resumo:** Saiba como criar uma nova política de arquivamento para Skype for Business Server.
  
Você pode criar novas políticas de arquivamento usando o Painel de Controle ou cmdlets do Windows PowerShell.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Criar uma nova política de arquivamento usando o Painel de Controle

Para criar uma nova política de arquivamento usando o Painel de Controle:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.
    
4. Clique em **Novo** e execute uma das seguintes ações: 
    
   - Para criar uma política de arquivamento em nível de site, clique em **Política de site** e em **Selecionar um site**, clique no site ao qual a política deve ser aplicada.
    
   - Para criar uma política de arquivamento em nível do usuário, clique em **Política de usuário**.
    
5. Em **Nova Política de Arquivamento**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova política (por exemplo, externalContoso).
    
   - Em **Descrição**, forneça os detalhes sobre a política (por exemplo, a política de arquivamento de usuário externo da Contoso).
    
   - Para controlar o arquivamento das comunicações com usuários internos, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para controlar o arquivamento das comunicações com usuários externos, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
    > [!IMPORTANT]
    > As configurações de uma política do usuário se aplicam somente a usuários específicos e grupos de usuários aos quais você aplica a política. Para obter detalhes, consulte [Aplicar uma política de arquivamento para usuários no Skype para Business Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Criar uma nova política de arquivamento usando o Windows PowerShell

É possível criar novas políticas de arquivamento usando o cmdlet **New-CsArchivingPolicy** do Windows PowerShell. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Para criar uma nova política de arquivamento no nível de site

Este comando cria uma nova política de arquivamento para o site de Redmond:
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Para criar uma nova política de arquivamento no nível por-usuário

Para criar uma nova política de arquivamento no nível por usuário, basta especificar um Identity exclusivo ao criar a política:
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Para criar uma nova política de arquivamento que permita o arquivamento de sessões de comunicação interna

Como nenhum parâmetros foi especificado (além do parâmetro obrigatório Identity) nos comandos anteriores, as novas políticas utilizarão os valores padrão para todas as suas propriedades. Para criar políticas que utilizam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro apropriado. Por exemplo, o comando a seguir cria uma política de arquivamento que permite o arquivamento de sessões de mensagens instantâneas internas: 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Para criar uma nova política de arquivamento que permita o arquivamento de sessões de comunicação interna e externa

Vários valores de propriedade podem ser modificados, incluindo vários parâmetros. Por exemplo, esse comando configura a nova política para arquivar sessões de mensagens instantâneas internas e externas:
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```