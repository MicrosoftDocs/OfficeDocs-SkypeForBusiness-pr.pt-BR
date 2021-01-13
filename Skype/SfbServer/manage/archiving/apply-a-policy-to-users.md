---
title: Aplicar uma política de arquivamento aos usuários no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumo: saiba como atribuir uma política de arquivamento aos usuários no Skype for Business Server.'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817761"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Aplicar uma política de arquivamento aos usuários no Skype for Business Server

**Resumo:** Saiba como atribuir uma política de arquivamento aos usuários no Skype for Business Server.
  
Se você tiver criado uma ou mais políticas de usuário para arquivamento de usuários no Skype for Business Server, poderá implementar o suporte de arquivamento para usuários específicos aplicando as políticas apropriadas a esses usuários ou grupos de usuários. Por exemplo, se você criar uma política para suportar o arquivamento de comunicações internas, poderá aplicá-la a pelo menos um usuário ou grupo de usuários para suportar o arquivamento das comunicações do Skype for Business Server do usuário.
  
> [!NOTE]
> Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas de Espera do Exchange In-Place controlarão se o arquivamento está habilitado para os usuários que estão no Exchange e têm suas caixas de correio colocadas em In-Place Espera. Para obter detalhes, [consulte Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Aplicar uma política de usuário usando o Painel de Controle

Para aplicar uma política de usuário usando o Painel de Controle:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar. 
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Usuário do Lync Server** em **Política** de Arquivamento, selecione a política de usuário de arquivamento que você deseja aplicar.
    
    > [!NOTE]
    > As **\<Automatic\>** configurações aplicam as configurações de instalação do servidor padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Aplicar uma política de usuário usando o Windows PowerShell

Você também pode aplicar uma política de usuário usando o cmdlet Windows PowerShell **Grant-CsArchivingPolicy.**
  
O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que possuem contas no pool de registradores atl-cs-001.contoso.com. Para obter detalhes sobre o parâmetro Filter usado neste comando, consulte a documentação do cmdlet [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

O comando a seguir remove qualquer política de arquivamento por usuário atribuída anteriormente a Ken Myer. Depois que a política por usuário for removida, Ken Myer será automaticamente gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem preferência sobre a política global.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Para obter detalhes, consulte a documentação do cmdlet [Grant-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)
  

