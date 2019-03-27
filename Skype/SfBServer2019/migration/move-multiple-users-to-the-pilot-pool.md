---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode mover vários usuários do seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell.
ms.openlocfilehash: c77598d531fa4640d64a61e22ace17e39d87b005
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888298"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover vários usuários para o pool piloto

Você pode mover vários usuários do seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell.

 **Neste artigo**
  
[Para mover vários usuários usando o Skype para o painel de controle do Business Server 2019](#sectionSection0)
  
[Para mover vários usuários usando o Skype para o Shell de gerenciamento do Business Server 2019](#sectionSection1)
  
[Para mover todos os usuários ao mesmo tempo usando o Skype para o Shell de gerenciamento do Business Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover vários usuários usando o Skype para o painel de controle do Business Server 2019
<a name="sectionSection0"> </a>

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Clique em **usuários**, clique em **Pesquisar**e clique em **Localizar**.
    
3. Selecione os dois usuários que você deseja mover para o Skype para Business Server 2019 pool. Neste exemplo, podemos moverá usuários Chen Yang e Claus Hansen.
    
     ![Mover usuários para o pool de registrador específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. No menu **ação** , selecione **mover usuários selecionados para o pool**.
    
5. Na lista suspensa, selecione o Skype para Business Server 2019 pool.
    
6. Clique em **ação**e, em seguida, clique em **mover usuários selecionados para o pool**. Clique em **OK**.
    
     ![Mover usuários, caixa de diálogo de pool de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Verifique se a coluna **pool de registrador** para os usuários agora contém o Skype para Business Server 2019 pool, que indica se os usuários foram movidos com êxito. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover vários usuários usando o Skype para o Shell de gerenciamento do Business Server 2019
<a name="sectionSection1"> </a>

1. Abra o Skype do Shell de gerenciamento do servidor 2019 de negócios. 
    
2. Na linha de comando, digite o seguinte e substitua **User1** e **User2** nomes de usuário específicos que você deseja mover e substitua **pool_FQDN** pelo nome do pool de destino. Neste exemplo, podemos moverá usuários Hao Chen e Katie Jordânia. 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemplo do cmdlet Get-CsUser do PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Na linha de comando, digite o seguinte: 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. A identidade do **Pool de registrador** agora deve apontar para o pool que você especificou como **pool_FQDN** na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com êxito. Repita as etapas para verificar se o **Usuário2** foram movidos. 
    
     ![Saída do PowerShell Get-UsUser-Identity cmdlet](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover todos os usuários ao mesmo tempo usando o Skype para o Shell de gerenciamento do Business Server 2019
<a name="sectionSection2"> </a>

Neste exemplo, todos os usuários foram retornados ao pool herdado (pool01. contoso.NET). Usando o Skype para o Shell de gerenciamento do Business Server 2019, podemos moverá todos os usuários ao mesmo tempo para o Skype para Business Server 2019 pool (pool02.contoso.net).
  
1. Abra o Skype do Shell de gerenciamento do servidor 2019 de negócios.
    
2. Na linha de comando, digite o seguinte: 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet do PowerShell e resultados no Shell de gerenciamento](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Execute **Get-CsUser** para um dos usuários piloto. 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. A identidade do **Pool de registrador** para cada usuário agora aponta para o pool que você especificou como **pool_FQDN** na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com êxito. 
    
5. Além disso, podemos exibir a lista de usuários no Skype para painel de controle do Business Server 2019 e verificar que o valor de Pool de registradores aponta agora para o Skype para Business Server 2019 pool.
    
     ![Skype para a lista de usuários do painel de controle do Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

