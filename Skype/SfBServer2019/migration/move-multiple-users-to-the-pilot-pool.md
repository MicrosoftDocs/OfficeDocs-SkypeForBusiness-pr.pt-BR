---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode mover vários usuários do pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle Skype for Business Server 2019 ou o Shell de Gerenciamento Skype for Business Server 2019.
ms.openlocfilehash: 689886060f14a47e82865a2ed66bfc3ff495dfdc3b1f44e6c5674294b4d21eb9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300647"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover vários usuários para o pool piloto

Você pode mover vários usuários do pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle Skype for Business Server 2019 ou o Shell de Gerenciamento Skype for Business Server 2019.

 **Neste artigo**
  
[Para mover vários usuários usando o Painel de Controle Skype for Business Server 2019](#sectionSection0)
  
[Para mover vários usuários usando o Shell de Gerenciamento Skype for Business Server 2019](#sectionSection1)
  
[Para mover todos os usuários ao mesmo tempo usando o Shell de Gerenciamento Skype for Business Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover vários usuários usando o Painel de Controle Skype for Business Server 2019
<a name="sectionSection0"> </a>

1. Abra Skype for Business Server Painel de Controle.
    
2. Clique **em Usuários,** em **Pesquisar** e em **Encontrar**.
    
3. Selecione dois usuários que você deseja mover para o pool Skype for Business Server 2019. Neste exemplo, vamos mover os usuários Chen Yang e Claus Hansen.
    
     ![Mover usuários para pool de registro específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. No menu **Ação**, selecione **Mover usuários selecionados para o pool**.
    
5. Na lista lista listada, selecione o pool Skype for Business Server 2019.
    
6. Clique em **Ação** e em **Mover usuários selecionados para o pool**. Clique em **OK**.
    
     ![Mover Usuários, caixa de diálogo pool de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Verifique se a **coluna pool do Registrador** para os usuários agora contém o pool Skype for Business Server 2019, que indica que os usuários foram movidos com êxito. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover vários usuários usando o Shell de Gerenciamento Skype for Business Server 2019
<a name="sectionSection1"> </a>

1. Abra o shell de gerenciamento Skype for Business Server 2019. 
    
2. Na linha de comando, digite o seguinte e substitua **User1** e **User2** por nomes de usuário específicos que você deseja mover e substitua pool_FQDN pelo nome do pool de destino.  Neste exemplo, vamos mover os usuários Hao Chen e Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemplo de cmdlet Get-CsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. A identidade do **Pool de registradores** deve apontar agora para o pool especificado como **pool_FQDN** na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com sucesso. Repita a etapa para verificar **se User2** foi movido. 
    
     ![Saída do cmdlet Get-UsUser -Identity do PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover todos os usuários ao mesmo tempo usando o Shell de Gerenciamento Skype for Business Server 2019
<a name="sectionSection2"> </a>

Neste exemplo, todos os usuários foram retornados ao pool herddo (pool01.contoso.net). Usando o Shell de Gerenciamento Skype for Business Server 2019, moveremos todos os usuários ao mesmo tempo para o pool Skype for Business Server 2019 (pool02.contoso.net).
  
1. Abra o shell de gerenciamento Skype for Business Server 2019.
    
2. Na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet do PowerShell e resultados no Shell de Gerenciamento](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Execute **Get-CsUser** para um dos usuários piloto. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. A **identidade do Pool** de Registradores para cada usuário agora aponta para o pool especificado como pool_FQDN na etapa anterior.  A presença dessa identidade confirma que o usuário foi movido com sucesso. 
    
5. Além disso, podemos exibir a lista de usuários no Painel de Controle Skype for Business Server 2019 e verificar se o valor do Pool do Registrador agora aponta para o pool Skype for Business Server 2019.
    
     ![Skype for Business Server lista de usuários do Painel de Controle 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

