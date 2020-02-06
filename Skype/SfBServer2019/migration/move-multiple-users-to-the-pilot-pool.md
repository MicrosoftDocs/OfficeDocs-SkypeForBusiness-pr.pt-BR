---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode mover vários usuários do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019.
ms.openlocfilehash: 62cf398a55be9c17526e8d607642db236ae57a3f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813269"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover vários usuários para o pool piloto

Você pode mover vários usuários do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019.

 **Neste artigo**
  
[Para mover vários usuários usando o painel de controle do Skype for Business Server 2019](#sectionSection0)
  
[Para mover vários usuários usando o Shell de gerenciamento do Skype for Business Server 2019](#sectionSection1)
  
[Para mover todos os usuários ao mesmo tempo usando o Shell de gerenciamento do Skype for Business Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover vários usuários usando o painel de controle do Skype for Business Server 2019
<a name="sectionSection0"> </a>

1. Abra o painel de controle do Skype for Business Server.
    
2. Clique em **usuários**, clique em **Pesquisar**e, em seguida, clique em **Localizar**.
    
3. Selecione dois usuários que você deseja mover para o pool do Skype for Business Server 2019. Neste exemplo, vamos mover os usuários Yang Yang e Claus Hansen.
    
     ![Mover usuários para um pool de registros específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. No menu **ação** , selecione **mover os usuários selecionados para o pool**.
    
5. Na lista suspensa, selecione o pool do Skype for Business Server 2019.
    
6. Clique em **ação**e, em seguida, clique em **mover os usuários selecionados para o pool**. Clique em **OK**.
    
     ![Caixa de diálogo mover usuários, pool de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Verifique se a coluna do **pool de registradores** dos usuários agora contém o pool do Skype for Business Server 2019, que indica que os usuários foram movidos com êxito. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover vários usuários usando o Shell de gerenciamento do Skype for Business Server 2019
<a name="sectionSection1"> </a>

1. Abra o Shell de gerenciamento do Skype for Business Server 2019. 
    
2. Na linha de comando, digite o seguinte e substitua **Usuário1** e **user2** por nomes de usuário específicos que você deseja mover e substitua **pool_FQDN** pelo nome do pool de destino. Neste exemplo, mudaremos os usuários de Hao Chen e Katie Jordânia. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemplo do cmdlet Get-CsUser do PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. A identidade do **pool do registrador** agora deve apontar para o pool especificado como **pool_FQDN** na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com êxito. Repita a etapa para verificar se **user2** foi movido. 
    
     ![Saída do cmdlet Get-UsUser-Identity do PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover todos os usuários ao mesmo tempo usando o Shell de gerenciamento do Skype for Business Server 2019
<a name="sectionSection2"> </a>

Neste exemplo, todos os usuários foram retornados ao pool herdado (pool01.contoso.net). Usando o Shell de gerenciamento do Skype for Business Server 2019, todos os usuários serão movidos ao mesmo tempo para o pool 2019 do Skype for Business Server (pool02.contoso.net).
  
1. Abra o Shell de gerenciamento do Skype for Business Server 2019.
    
2. Na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet do PowerShell e resulta no Shell de gerenciamento](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Execute **Get-CsUser** para um dos usuários piloto. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. A identidade do **pool de registradores** para cada usuário agora aponta para o pool especificado como **pool_FQDN** na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com êxito. 
    
5. Além disso, podemos Visualizar a lista de usuários no painel de controle do Skype for Business Server 2019 e verificar se o valor do pool do registrador agora aponta para o pool do Skype for Business Server 2019.
    
     ![Lista de usuários do painel de controle do Skype for Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

