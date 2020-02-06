---
title: Aplicar uma política de arquivamento aos usuários no Skype for Business Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumo: saiba como atribuir uma política de arquivamento aos usuários no Skype for Business Server.'
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819003"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Aplicar uma política de arquivamento aos usuários no Skype for Business Server

**Resumo:** Saiba como atribuir uma política de arquivamento aos usuários no Skype for Business Server.
  
Se você tiver criado uma ou mais políticas de usuário para arquivamento para usuários hospedados no Skype for Business Server, poderá implementar o suporte para arquivamento para usuários específicos aplicando as políticas apropriadas a esses usuários ou grupos de usuários. Por exemplo, se você criar uma política para dar suporte ao arquivamento de comunicações internas, poderá aplicá-la a pelo menos um usuário ou grupo de usuários para dar suporte ao arquivamento das comunicações do Skype for Business Server do usuário.
  
> [!NOTE]
> Se você tiver habilitado a integração do Microsoft Exchange para a implantação, as políticas de bloqueio do Exchange in loco controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange e que suas caixas de correio colocam no bloqueio in-loco. Para obter detalhes, consulte [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configurar a integração com o armazenamento do Exchange para o Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Aplicar uma política de usuário usando o Painel de Controle

Para aplicar uma política de usuário usando o Painel de Controle:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação à esquerda, clique em **Usuários** e procure a conta de usuário que deseja configurar. 
    
4. Na tabela que lista os resultados da pesquisa, clique em conta de usuário, em **Editar** e em **Mostrar detalhes**.
    
5. Em **Editar o usuário do Lync Server** na **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.
    
    > [!NOTE]
    > As ** \<configurações\> automáticas** aplicam as configurações de instalação do servidor padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Aplicar uma política de usuário usando o Windows PowerShell

Você também pode aplicar uma política de usuário usando o cmdlet **Grant-CsArchivingPolicy** do Windows PowerShell.
  
O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que possuem contas hospedadas no pool de registradores atl-cs-001.contoso.com. Para obter detalhes sobre o parâmetro de filtro usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

O comando a seguir remove a política de arquivamento por usuário anteriormente atribuída a Ken Myer. Depois que a política de voz por usuário é removida, Ken Myer será automaticamente gerenciado usando uma política global ou, se existir, a política do seu site local. A política de site tem precedência sobre a política global.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Para obter detalhes, consulte a documentação do cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

