---
title: Aplicar uma política de arquivamento aos usuários no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumo: Saiba como atribuir uma política de arquivamento para usuários no Skype para Business Server 2015.'
ms.openlocfilehash: 0a9b19f6b02daae09f71b1f9933c90bfc86c5e23
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569383"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a>Aplicar uma política de arquivamento aos usuários no Skype for Business Server 2015

**Resumo:** Saiba como atribuir uma política de arquivamento para usuários no Skype para Business Server 2015.
  
Se você criou um ou mais políticas de usuário para arquivamento para usuários hospedagem no Skype para Business Server 2015, você pode implementar o suporte ao arquivamento para usuários específicos, aplicando as políticas adequadas a esses usuários ou grupos de usuários. Por exemplo, se você criar uma política para suportar o arquivamento das comunicações internas, você pode aplicá-lo a pelo menos um usuário ou grupo de usuário para suportar o arquivamento do Skype do usuário para comunicações comerciais Server 2015.
  
> [!NOTE]
> Se você ativou a integração do Microsoft Exchange para sua implantação, o controle de políticas de retenção de In-loco do Exchange se o arquivamento estiver habilitado para os usuários hospedados no Exchange e tem colocado de suas caixas de correio em bloqueio In-loco. Para obter detalhes, consulte [Planejar o arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) e [Configure integração com Exchange storage para Skype para Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Aplicar uma política de usuário usando o Painel de Controle

Para aplicar uma política de usuário usando o Painel de Controle:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação à esquerda, clique em **Usuários** e procure a conta de usuário que deseja configurar. 
    
4. Na tabela que lista os resultados da pesquisa, clique em conta de usuário, em **Editar** e em **Mostrar detalhes**.
    
5. Em **Editar usuário do Lync Server** , em **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.
    
    > [!NOTE]
    > O ** \<automática\> ** configurações se aplicam as configurações de instalação de servidor padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Aplicar uma política de usuário usando o Windows PowerShell

Você também pode aplicar uma política de usuário usando o cmdlet do Windows PowerShell **Grant-CsArchivingPolicy** .
  
O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que possuem contas hospedadas no pool de registradores atl-cs-001.contoso.com. Para obter detalhes sobre o parâmetro de filtro usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

O comando a seguir remove a política de arquivamento por usuário anteriormente atribuída a Ken Myer. Depois que a política de voz por usuário é removida, Ken Myer será automaticamente gerenciado usando uma política global ou, se existir, a política do seu site local. A política de site tem precedência sobre a política global.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Para obter detalhes, consulte a documentação do cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

